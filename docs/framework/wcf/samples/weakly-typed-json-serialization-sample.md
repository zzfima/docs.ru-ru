---
title: Пример сериализации слабо типизированных данных JSON
ms.date: 03/30/2017
ms.assetid: 0b30e501-4ef5-474d-9fad-a9d559cf9c52
ms.openlocfilehash: 370030671a6a8c6709567bf070411543722ab8d8
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842672"
---
# <a name="weakly-typed-json-serialization-sample"></a>Пример сериализации слабо типизированных данных JSON
При сериализации пользовательского типа в заданный формат передачи или при десериализации формата передачи в пользовательский тип заданный пользовательский тип должен быть доступен как службе, так и клиенту. Обычно для этого к пользовательским типам применяется атрибут <xref:System.Runtime.Serialization.DataContractAttribute> , а к их членам применяется атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> . Этот механизм также применим при работе с объектами JavaScript Object Notation (JSON), как описано в разделе [как: Сериализация и десериализация данных JSON](../../../../docs/framework/wcf/feature-details/how-to-serialize-and-deserialize-json-data.md).  
  
 В некоторых случаях службы Windows Communication Foundation (WCF) или клиента доступ к объектам JSON, созданным с помощью службы или клиента, который находится вне зоны контроля разработчика. Как дополнительные веб-служб публично предоставляют API-интерфейсы JSON, тем менее практично для разработчика WCF для создания локального определяемых пользователем типов, в которые будут десериализовываться произвольные объекты JSON. Этот образец предоставляет механизм, позволяющий разработчикам WCF для работы с десериализованные произвольными объектами JSON, не создавая определяемые пользователем типы. Он называется *слабо типизированной сериализацией* объектов JSON, поскольку тип, в который десериализуется объект JSON, во время компиляции неизвестен.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Например, API общедоступной веб-службы возвращает следующий объект JSON, который содержит определенные сведения о пользователе службы.  
  
```json  
{"personal": {"name": "Paul", "age": 23, "height": 1.7, "isSingle": true, "luckyNumbers": [5,17,21]}, "favoriteBands": ["Band ABC", "Band XYZ"]}  
```  
  
 Чтобы десериализовать этот объект, клиент WCF необходимо реализовать следующие пользовательские типы.  
  
```  
[DataContract]  
 public class MemberProfile  
 {  
     [DataMember]  
     public PersonalInfo personal;  
  
     [DataMember]  
     public string[] favoriteBands;  
 }  
  
 [DataContract]  
 public class PersonalInfo  
 {  
     [DataMember]  
     public string name;  
  
     [DataMember]  
     public int age;  
  
     [DataMember]  
     public double height;  
  
     [DataMember]  
     public bool isSingle;  
  
     [DataMember]  
     public int[] luckyNumbers;  
 }  
```  
  
 Эта задача может быть громоздкой, особенно если клиент должен обрабатывать более одного типа объектов JSON.  
  
 Тип `JsonObject` в этом образце является слабо типизированным представлением объекта JSON. `JsonObject` использует естественное сопоставление между объектами JSON и словарями [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] и сопоставление между массивами JSON и массивами [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] . В следующем примере кода демонстрируется тип `JsonObject` .  
  
```  
// Instantiation of JsonObject json omitted  
  
string name = json["root"]["personal"]["name"];  
int age = json["root"]["personal"]["age"];  
double height = json["root"]["personal"]["height"];  
bool isSingle = json["root"]["personal"]["isSingle"];  
int[] luckyNumbers = {  
                                     json["root"]["personal"]["luckyNumbers"][0],  
                                     json["root"]["personal"]["luckyNumbers"][1],  
                                     json["root"]["personal"]["luckyNumbers"][2]   
                                 };  
string[] favoriteBands = {  
                                        json["root"]["favoriteBands"][0],  
                                        json["root"]["favoriteBands"][1]  
                                    };  
```  
  
 Обратите внимание что объекты и массивы JSON можно просматривать без необходимости объявлять их тип во время компиляции. Описание требования к объекту верхнего уровня `["root"]` см. в разделе [Mapping Between JSON and XML](../../../../docs/framework/wcf/feature-details/mapping-between-json-and-xml.md).  
  
> [!NOTE]
>  Класс `JsonObject` предоставлен исключительно в качестве примера. Он не был тщательно протестирован, и его не следует использовать в рабочей среде. Очевидным недостатком слабо типизированной сериализации JSON является плохая типобезопасность при работе с `JsonObject`.  
  
 Чтобы использовать тип `JsonObject` , контракт операции клиента должен использовать в качестве возвращаемого типа <xref:System.ServiceModel.Channels.Message> .  
  
```  
[ServiceContract]  
    interface IClientSideProfileService  
    {  
        // There is no need to write a DataContract for the complex type returned by the service.  
        // The client will use a JsonObject to browse the JSON in the received message.  
  
        [OperationContract]  
        [WebGet(ResponseFormat = WebMessageFormat.Json)]  
        Message GetMemberProfile();  
    }  
```  
  
 Объект `JsonObject` создается, как показано в следующем коде.  
  
```  
// Code to instantiate IClientSideProfileService channel omitted…  
  
// Make a request to the service and obtain the Json response  
XmlDictionaryReader reader = channel.GetMemberProfile().GetReaderAtBodyContents();  
  
// Go through the Json as though it is a dictionary. There is no need to map it to a .NET CLR type.  
JsonObject json = new JsonObject(reader);  
```  
  
 Конструктор `JsonObject` принимает объект <xref:System.Xml.XmlDictionaryReader>, который получается через метод <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> . Модуль чтения содержит XML-представление сообщения JSON, полученного клиентом. Дополнительные сведения см. в разделе [Mapping Between JSON and XML](../../../../docs/framework/wcf/feature-details/mapping-between-json-and-xml.md).  
  
 Программа выдает следующие результаты.  
  
```  
Service listening at http://localhost:8000/.  
To view the JSON output from the sample, navigate to http://localhost:8000/GetMemberProfile  
This is Paul's page. I am 23 years old and I am 1.7 meters tall.  
I am single.  
My lucky numbers are 5, 17, and 21.  
My favorite bands are Band ABC and Band XYZ.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Создайте решение WeaklyTypedJson.sln, следуя инструкциям из раздела [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Запустите решение.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\Ajax\WeaklyTypedJson`  
  
