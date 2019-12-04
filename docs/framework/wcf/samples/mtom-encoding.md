---
title: Кодирование MTOM
ms.date: 03/30/2017
ms.assetid: 820e316f-4ee1-4eb5-ae38-b6a536e8a14f
ms.openlocfilehash: 4156ebed22dc775aa69cf473dc89a26d7e2070d7
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714759"
---
# <a name="mtom-encoding"></a>Кодирование MTOM
В данном образце демонстрируется использование кодирования сообщений с помощью механизма оптимизации передачи сообщений (MTOM) с WSHttpBinding. MTOM — это механизм передачи больших вложений в двоичном формате с сообщениями SOAP как необработанных байтов, допустимых для меньших сообщений.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\MTOM`  
  
 По умолчанию WSHttpBinding отправляет и принимает сообщения как нормальный XML-текст. Для включения отправки и получения MTOM-сообщений задайте атрибут `messageEncoding` в конфигурации привязки (как в следующем примере кода) или непосредственно в привязке с помощью свойства `MessageEncoding`. Теперь служба или клиент могут отправлять или получать MTOM-сообщения.  
  
```xml  
<wsHttpBinding>  
  <binding name="WSHttpBinding_IUpload" messageEncoding="Mtom" />  
</wsHttpBinding>  
```  
  
 Кодировщик MTOM может оптимизировать массивы байтов и потоки. В данном образце операция использует параметр `Stream` и, следовательно, может быть оптимизирована.  

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
  public interface IUpload  
  {  
      [OperationContract]  
      int Upload(Stream data);  
  }  
```
  
 Контракт, выбранный для данного образца, передает двоичные данные службе и в качестве возвращаемого значения получает число загруженных байтов. Если служба установлена и запущен клиент, он выводит на печать число 1000, указывающее, что было получено 1000 байт. В напоминании вывода приводятся списки размеров оптимизированных и неоптимизированных сообщений для различных нагрузок.  
  
```console
Output:  
1000  
  
Text encoding with a 100 byte payload: 433  
MTOM encoding with a 100 byte payload: 912  
  
Text encoding with a 1000 byte payload: 1633  
MTOM encoding with a 1000 byte payload: 2080  
  
Text encoding with a 10000 byte payload: 13633  
MTOM encoding with a 10000 byte payload: 11080  
  
Text encoding with a 100000 byte payload: 133633  
MTOM encoding with a 100000 byte payload: 101080  
  
Text encoding with a 1000000 byte payload: 1333633  
MTOM encoding with a 1000000 byte payload: 1001080  
  
Press <ENTER> to terminate client.  
```  
  
 Цель использования MTOM - оптимизация передачи больших двоичных нагрузок. Отправка SOAP-сообщения с помощью MTOM имеет значительные издержки для небольших двоичных нагрузок, но позволяет значительно сэкономить, когда нагрузка превышает несколько тысяч байт. Причина заключается в том, что нормальный XML-текст кодирует двоичные данные с помощью Base64, который требует четыре символа на каждые три байта и увеличивает размер данных на одну треть. Механизм MTOM способен передавать двоичные данные в виде необработанных байтов, позволяя тем самым сэкономить время на кодирование/декодирование и способствуя уменьшению размера сообщений. Порог в несколько тысяч байт мал по сравнению с размером современных деловых документов и цифровых фотографий.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Установите ASP.NET 4,0 с помощью следующей команды.  
  
    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
