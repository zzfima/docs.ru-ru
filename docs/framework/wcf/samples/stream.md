---
title: Stream
ms.date: 03/30/2017
ms.assetid: 58a3db81-20ab-4627-bf31-39d30b70b4fe
ms.openlocfilehash: d4166ac0258001b3e4eb0b8ece0f5163863359a4
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716656"
---
# <a name="stream"></a>Stream
Образец потока демонстрирует использование взаимодействия в режиме потоковой передачи. Служба предоставляет несколько операций, которые отправляют и принимают потоки. Этот образец размещается резидентно. Как клиент, так и служба являются консольными программами.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Windows Communication Foundation (WCF) может взаимодействовать в двух режимах передачи — с буферизацией или потоковой передачей. По умолчанию используется режим буферизованной передачи, в случае которого сообщение должно быть доставлено полностью, прежде чем получатель сможет его прочитать. При использовании режима потоковой передачи получатель может начать обработку сообщения до того, как оно будет доставлено полностью. Режим потоковой передачи полезно использовать при большой длине передаваемых данных, которые могут обрабатываться последовательно. Режим потоковой передачи также может быть полезен, когда размер сообщения слишком велик для выполнения полной буферизации.  
  
## <a name="streaming-and-service-contracts"></a>Потоковая передача и контракты службы  
 При разработке контракта службы следует рассмотреть возможность потоковой передачи. Если операция принимает или возвращает большой объем данных, необходимо рассмотреть возможность потоковой передачи этих данных во избежание выделения большого объема памяти для буферизации входных и выходных сообщений. Для потоковой передачи данных параметр, в котором содержатся эти данные, должен быть единственным параметром в сообщении. Например, если требуется выполнить потоковую передачу входного сообщения, операция должна иметь точно один входной параметр. Аналогично, если требуется выполнить потоковую передачу выходного сообщения, операция должна иметь точно один выходной параметр или возвращать значение. В обоих случаях параметр или тип возвращаемого значения должны являться объектами `Stream`, `Message` или `IXmlSerializable`. Ниже приведен контракт службы, использованный в данном образце потоковой передачи.  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IStreamingSample  
{  
    [OperationContract]  
    Stream GetStream(string data);  
    [OperationContract]  
    bool UploadStream(Stream stream);  
    [OperationContract]  
    Stream EchoStream(Stream stream);  
    [OperationContract]  
    Stream GetReversedStream();  
  
}  
```  
  
 Операция `GetStream` получает некоторые буферизуемые входные данные в качестве строки и возвращает объект `Stream`, который является потоковым. И наоборот, `UploadStream` принимает объект `Stream` (потоковый) и возвращает объект `bool` (буферизованный). `EchoStream` принимает и возвращает объект `Stream` и является примером операции, в которой как входное, так и выходное сообщения являются потоковыми. Наконец, `GetReversedStream` не принимает никакие данные и возвращает объект `Stream` (потоковый).  
  
## <a name="enabling-streamed-transfers"></a>Включение потоковой передачи  
 Такое определение контрактов операций, какое описано выше, обеспечивает потоковую передачу на уровне модели программирования. Если этим ограничиться, транспорт все равно выполняет буферизацию всего содержимого сообщения. Чтобы обеспечить потоковую передачу на уровне транспорта, выберите режим передачи в элементе привязки транспорта. Свойству `TransferMode` элемента привязки можно присвоить значение `Buffered`, `Streamed`, `StreamedRequest` или `StreamedResponse`. Если режиму передачи присвоено значение `Streamed`, потоковая передача будет выполняться в обоих направлениях. Если режиму передачи присвоено значение `StreamedRequest` или `StreamedResponse`, потоковая передача будет выполняться только в направлении запроса или ответа, соответственно.  
  
 Привязка `basicHttpBinding` предоставляет свойство `TransferMode` в привязке, как и привязки `NetTcpBinding` и `NetNamedPipeBinding`. Для других транспортов необходимо создать пользовательскую привязку для задания режима передачи.  
  
 В следующем коде конфигурации из образца показано задание для свойства `TransferMode` значения потоковой передачи в привязке `basicHttpBinding` и пользовательской привязке HTTP:  
  
```xml  
<!-- An example basicHttpBinding using streaming. -->  
<basicHttpBinding>  
  <binding name="HttpStreaming" maxReceivedMessageSize="67108864"  
           transferMode="Streamed"/>  
</basicHttpBinding>  
<!-- An example customBinding using HTTP and streaming.-->  
<customBinding>  
  <binding name="Soap12">  
    <textMessageEncoding messageVersion="Soap12WSAddressing10" />  
    <httpTransport transferMode="Streamed"  
                   maxReceivedMessageSize="67108864"/>  
  </binding>  
</customBinding>  
```  
  
 Помимо задания для свойства `transferMode` значения `Streamed`, предыдущий код конфигурации задает для свойства `maxReceivedMessageSize` значение 64 МБ. В качестве защитного механизма свойство `maxReceivedMessageSize` определяет допустимый максимальный размер принимаемых сообщений. По умолчанию для свойства `maxReceivedMessageSize` задано значение 64 КБ, которое обычно слишком мало для сценариев потоковой передачи.  
  
## <a name="processing-data-as-it-is-streamed"></a>Обработка данных во время потоковой передачи  
 Операции `GetStream`, `UploadStream` и `EchoStream` выполняют передачу данных непосредственно из файла или сохранение полученных данных непосредственно в файл. Однако в некоторых случаях требуется отправлять или принимать большие объемы данных и выполнять обработку этих данных по частям во время передачи или приема. Одним из способов решения этой задачи является создание пользовательского потока (класса, наследующего от класса <xref:System.IO.Stream>), обрабатывающего данные по мере их чтения или записи. Операция `GetReversedStream` и класс `ReverseStream` являются примерами такого подхода.  
  
 Метод `GetReversedStream` создает и возвращает новый экземпляр класса `ReverseStream`. Фактическая обработка происходит, когда система считывает данные из объекта `ReverseStream`. Реализация метода `ReverseStream.Read` считывает фрагмент байтов из исходного файла, обращает их, а затем возвращает обращенные байты. Этот метод не обращает все содержимое файла; он обращает один фрагмент байтов за раз. В этом примере показано, как можно выполнить потоковую обработку во время чтения или записи содержимого потока.  
  
```csharp
class ReverseStream : Stream  
{  
  
    FileStream inStream;  
    internal ReverseStream(string filePath)  
    {  
        //Opens the file and places a StreamReader around it.  
        inStream = File.OpenRead(filePath);  
    }  
  
    // Other methods removed for brevity.  
  
    public override int Read(byte[] buffer, int offset, int count)  
    {  
        int countRead=inStream.Read(buffer, offset,count);  
        ReverseBuffer(buffer, offset, countRead);  
        return countRead;  
    }  
  
    public override void Close()  
    {  
        inStream.Close();  
        base.Close();  
    }  
    protected override void Dispose(bool disposing)  
    {  
        inStream.Dispose();  
        base.Dispose(disposing);  
    }  
    void ReverseBuffer(byte[] buffer, int offset, int count)  
    {  
        int i, j;  
        for (i = offset, j = offset + count - 1; i < j; i++, j--)  
        {  
            byte currenti = buffer[i];  
            buffer[i] = buffer[j];  
            buffer[j] = currenti;  
        }  
  
    }  
}  
```  
  
## <a name="running-the-sample"></a>Запуск примера  
 Для выполнении этого образца сначала постройте службу и клиент в соответствии с указаниями, приведенными в конце данного документа. Затем запустите службу и клиент в двух разных окнах консоли. После запуска клиента он ожидает, когда при готовности службы будет нажата клавиша ВВОД. Затем клиент вызывает методы `GetStream()`, `UploadStream()` и `GetReversedStream()` сначала по HTTP, а затем по TCP. Ниже приведен пример вывода службы, а затем пример вывода клиента:  
  
 Вывод службы:  
  
```console  
The streaming service is ready.  
Press <ENTER> to terminate service.  
  
Saving to file D:\...\uploadedfile  
......................  
File D:\...\uploadedfile saved  
Saving to file D:\...\uploadedfile  
...............  
File D:\...\uploadedfile saved  
```  
  
 Вывод клиента:  
  
```console  
Press <ENTER> when service is ready  
------ Using HTTP ------   
Calling GetStream()  
Saving to file D:\...\clientfile  
......................  
Wrote 33405 bytes to stream  
  
File D:\...\clientfile saved  
Calling UploadStream()  
Calling GetReversedStream()  
Saving to file D:\...\clientfile  
......................  
Wrote 33405 bytes to stream  
  
File D:\...\clientfile saved  
------ Using Custom HTTP ------  
Calling GetStream()  
Saving to file D:\...\clientfile  
...............  
Wrote 33405 bytes to stream  
  
File D:\...\clientfile saved  
Calling UploadStream()  
Calling GetReversedStream()  
Saving to file D:\...\clientfile  
...............  
Wrote 33405 bytes to stream  
  
File D:\...\clientfile saved  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!NOTE]
> Если для восстановления конфигурации этого образца используется программа Svcutil.exe, измените имя конечной точки в конфигурации клиента, чтобы оно соответствовало клиентскому коду.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Stream`  
