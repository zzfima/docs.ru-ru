---
title: Взаимодействие с веб-службами ASMX
ms.date: 03/30/2017
ms.assetid: a7c11f0a-9e68-4f03-a6b1-39cf478d1a89
ms.openlocfilehash: b5af8f15d38f730d2243c642d4623c0bc6e1343c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183587"
---
# <a name="interoperating-with-asmx-web-services"></a>Взаимодействие с веб-службами ASMX
В этом примере показано, как интегрировать клиентское приложение Windows Communication Foundation (WCF) с существующим веб-сервисом ASMX.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Этот образец содержит консольную программу клиента (EXE) и библиотеку службы (DLL), размещаемую в службах IIS. Служба является веб-службой ASMX, реализующей контракт, который определяет шаблон взаимодействия "запрос-ответ". Службы предоставляет математические операции (`Add`, `Subtract`, `Multiply` и `Divide`). Клиент выполняет синхронные запросы математической операции, а служба отправляет в ответ результат. Действия клиента отображаются в окне консоли.  
  
 Реализация веб-службы ASMX, представленная в следующем образце кода, вычисляет и возвращает соответствующий результат.  
  
```csharp  
[WebService(Namespace="http://Microsoft.ServiceModel.Samples")]  
public class CalculatorService : System.Web.Services.WebService  
    {  
        [WebMethod]  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
        [WebMethod]  
        public double Subtract(double n1, double n2)  
        {  
            return n1 - n2;  
        }  
        [WebMethod]  
        public double Multiply(double n1, double n2)  
        {  
            return n1 * n2;  
        }  
        [WebMethod]  
        public double Divide(double n1, double n2)  
        {  
            return n1 / n2;  
        }  
    }  
```  
  
 В настройке к службе может `http://localhost/servicemodelsamples/service.asmx` быть доступна клиент на одной машине. Чтобы к службе могли получить доступ клиенты на удаленных компьютерах, вместо имени localhost необходимо указать полное имя домена.  
  
 Связь осуществляется через клиента, созданного [Сервис-Модель Метадата Утилита инструмент (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Клиент содержится в файле generatedClient.cs. Служба ASMX должна быть доступна для создания кода прокси, поскольку он используется для извлечения обновленных метаданных. Чтобы создать типизированную учетную запись-посредник, выполните следующую команду из командной строки в каталоге клиента.  
  
```console  
svcutil.exe /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost/servicemodelsamples/service.svc?wsdl /out:generatedClient.cs  
```  
  
 С помощью созданного клиента можно получить доступ к конечной точке службы, настроив соответствующий адрес и привязку. Как и служба, клиент использует файл конфигурации (App.config), чтобы задать конечную точку для взаимодействия. Конфигурация конечной точки клиента состоит из абсолютного адреса конечной точки службы, привязки и контракта, как показано в следующем образце конфигурации.  
  
```xml  
<client>  
   <endpoint
      address="http://localhost/ServiceModelSamples/service.asmx"
      binding="basicHttpBinding"
      contract="Microsoft.ServiceModel.Samples.CalculatorServiceSoap" />  
</client>  
```  
  
 Реализация клиента создает экземпляр созданного клиента. После этого созданный клиент можно использовать для взаимодействия со службой.  
  
```csharp  
// Create a client.  
CalculatorServiceSoapClient client = new CalculatorServiceSoapClient();  
  
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = client.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
// Call the Subtract service operation.  
value1 = 145.00D;  
value2 = 76.54D;  
result = client.Subtract(value1, value2);  
Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
// Call the Multiply service operation.  
value1 = 9.00D;  
value2 = 81.25D;  
result = client.Multiply(value1, value2);  
Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
// Call the Divide service operation.  
value1 = 22.00D;  
value2 = 7.00D;  
result = client.Divide(value1, value2);  
Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
  
Console.WriteLine();  
Console.WriteLine("Press <ENTER> to terminate client.");  
Console.ReadLine();  
```  
  
 При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```console
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить образец в одно- или кросс-машинной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\Interop\ASMX`  
