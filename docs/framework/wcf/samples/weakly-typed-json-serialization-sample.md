---
title: Пример сериализации слабо типизированных данных JSON
ms.date: 03/30/2017
ms.assetid: 0b30e501-4ef5-474d-9fad-a9d559cf9c52
ms.openlocfilehash: bdeaffe31ba9bced28eebcfe294fc9944e5d05d0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143594"
---
# <a name="weakly-typed-json-serialization-sample"></a>Пример сериализации слабо типизированных данных JSON
При сериализации пользовательского типа в заданный формат передачи или при десериализации формата передачи в пользовательский тип заданный пользовательский тип должен быть доступен как службе, так и клиенту. Обычно для этого к пользовательским типам применяется атрибут <xref:System.Runtime.Serialization.DataContractAttribute> , а к их членам применяется атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> . Этот механизм также применим при работе с объектами JSON, как описано в разделе [How to: Serialize and Deserialize JSON Data](../../../../docs/framework/wcf/feature-details/how-to-serialize-and-deserialize-json-data.md).  
  
 В некоторых сценариях служба или клиент Фонда связи Windows (WCF) должен получить доступ к объектам JSON, генерируемым службой или клиентом, неподконтрольным разработчику. Поскольку все больше веб-служб публично разоблачают AI JSON, разработчику WCF может стать нецелесообразным создавать локальные типы, определяемые пользователями, для десериализации произвольных объектов JSON. Этот пример обеспечивает механизм, который позволяет разработчикам WCF работать с десериализованными, произвольными объектами JSON, не создавая пользовательские типы. Он называется *слабо типизированной сериализацией* объектов JSON, поскольку тип, в который десериализуется объект JSON, во время компиляции неизвестен.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Например, API общедоступной веб-службы возвращает следующий объект JSON, который содержит определенные сведения о пользователе службы.  
  
```json  
{"personal": {"name": "Paul", "age": 23, "height": 1.7, "isSingle": true, "luckyNumbers": [5,17,21]}, "favoriteBands": ["Band ABC", "Band XYZ"]}  
```  
  
 Для десеризаниза этого объекта клиент WCF должен реализовать следующие типы, определяемые пользователем.  
  
```csharp  
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
  
 Тип `JsonObject` в этом образце является слабо типизированным представлением объекта JSON. `JsonObject`опирается на естественное отображение между объектами JSON и словарями .NET Framework, а также на картирование между массивами JSON и массивами .NET Framework. В следующем примере кода демонстрируется тип `JsonObject` .  
  
```csharp  
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
> Класс `JsonObject` предоставлен исключительно в качестве примера. Он не был тщательно протестирован, и его не следует использовать в рабочей среде. Очевидным недостатком слабо типизированной сериализации JSON является плохая типобезопасность при работе с `JsonObject`.  
  
 Чтобы использовать тип `JsonObject` , контракт операции клиента должен использовать в качестве возвращаемого типа <xref:System.ServiceModel.Channels.Message> .  
  
```csharp  
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
  
```csharp  
// Code to instantiate IClientSideProfileService channel omitted…  
  
// Make a request to the service and obtain the Json response  
XmlDictionaryReader reader = channel.GetMemberProfile().GetReaderAtBodyContents();  
  
// Go through the Json as though it is a dictionary. There is no need to map it to a .NET CLR type.  
JsonObject json = new JsonObject(reader);  
```  
  
 Конструктор `JsonObject` принимает объект <xref:System.Xml.XmlDictionaryReader>, который получается через метод <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> . Модуль чтения содержит XML-представление сообщения JSON, полученного клиентом. Для получения дополнительной информации смотрите тему [Картирование между JSON и XML](../../../../docs/framework/wcf/feature-details/mapping-between-json-and-xml.md).  
  
 Программа выдает следующие результаты.  
  
```console  
Service listening at http://localhost:8000/.  
To view the JSON output from the sample, navigate to http://localhost:8000/GetMemberProfile  
This is Paul's page. I am 23 years old and I am 1.7 meters tall.  
I am single.  
My lucky numbers are 5, 17, and 21.  
My favorite bands are Band ABC and Band XYZ.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)  
  
2. Создайте решение WeaklyTypedJson.sln, следуя инструкциям из раздела [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Запустите решение.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\Ajax\WeaklyTypedJson`  
