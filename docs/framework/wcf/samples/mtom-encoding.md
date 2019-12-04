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
# <a name="mtom-encoding"></a><span data-ttu-id="4eb52-102">Кодирование MTOM</span><span class="sxs-lookup"><span data-stu-id="4eb52-102">MTOM Encoding</span></span>
<span data-ttu-id="4eb52-103">В данном образце демонстрируется использование кодирования сообщений с помощью механизма оптимизации передачи сообщений (MTOM) с WSHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="4eb52-103">This sample demonstrates the use of the Message Transmission Optimization Mechanism (MTOM) message encoding with a WSHttpBinding.</span></span> <span data-ttu-id="4eb52-104">MTOM — это механизм передачи больших вложений в двоичном формате с сообщениями SOAP как необработанных байтов, допустимых для меньших сообщений.</span><span class="sxs-lookup"><span data-stu-id="4eb52-104">MTOM is a mechanism for transmitting large binary attachments with SOAP messages as raw bytes, allowing for smaller messages.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4eb52-105">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4eb52-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4eb52-106">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="4eb52-106">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="4eb52-107">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="4eb52-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4eb52-108">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4eb52-108">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\MTOM`  
  
 <span data-ttu-id="4eb52-109">По умолчанию WSHttpBinding отправляет и принимает сообщения как нормальный XML-текст.</span><span class="sxs-lookup"><span data-stu-id="4eb52-109">By default, the WSHttpBinding sends and received messages as normal text XML.</span></span> <span data-ttu-id="4eb52-110">Для включения отправки и получения MTOM-сообщений задайте атрибут `messageEncoding` в конфигурации привязки (как в следующем примере кода) или непосредственно в привязке с помощью свойства `MessageEncoding`.</span><span class="sxs-lookup"><span data-stu-id="4eb52-110">To enable sending and receiving MTOM messages, set the `messageEncoding` attribute on the binding's configuration (as in the following example code), or directly on the binding using the `MessageEncoding` property.</span></span> <span data-ttu-id="4eb52-111">Теперь служба или клиент могут отправлять или получать MTOM-сообщения.</span><span class="sxs-lookup"><span data-stu-id="4eb52-111">The service or client can now send and receive MTOM messages.</span></span>  
  
```xml  
<wsHttpBinding>  
  <binding name="WSHttpBinding_IUpload" messageEncoding="Mtom" />  
</wsHttpBinding>  
```  
  
 <span data-ttu-id="4eb52-112">Кодировщик MTOM может оптимизировать массивы байтов и потоки.</span><span class="sxs-lookup"><span data-stu-id="4eb52-112">The MTOM encoder can optimize arrays of bytes and streams.</span></span> <span data-ttu-id="4eb52-113">В данном образце операция использует параметр `Stream` и, следовательно, может быть оптимизирована.</span><span class="sxs-lookup"><span data-stu-id="4eb52-113">In this sample, the operation uses a `Stream` parameter and can therefore be optimized.</span></span>  

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
  public interface IUpload  
  {  
      [OperationContract]  
      int Upload(Stream data);  
  }  
```
  
 <span data-ttu-id="4eb52-114">Контракт, выбранный для данного образца, передает двоичные данные службе и в качестве возвращаемого значения получает число загруженных байтов.</span><span class="sxs-lookup"><span data-stu-id="4eb52-114">The contract chosen for this sample transmits binary data to the service and receives the number of bytes uploaded as the return value.</span></span> <span data-ttu-id="4eb52-115">Если служба установлена и запущен клиент, он выводит на печать число 1000, указывающее, что было получено 1000 байт.</span><span class="sxs-lookup"><span data-stu-id="4eb52-115">When the service is installed and the client is run, it prints out the number 1000, which indicates that all 1000 bytes were received.</span></span> <span data-ttu-id="4eb52-116">В напоминании вывода приводятся списки размеров оптимизированных и неоптимизированных сообщений для различных нагрузок.</span><span class="sxs-lookup"><span data-stu-id="4eb52-116">The remainder of the output lists optimized and non-optimized message sizes for various payloads.</span></span>  
  
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
  
 <span data-ttu-id="4eb52-117">Цель использования MTOM - оптимизация передачи больших двоичных нагрузок.</span><span class="sxs-lookup"><span data-stu-id="4eb52-117">The purpose for using MTOM is to optimize the transmission of large binary payloads.</span></span> <span data-ttu-id="4eb52-118">Отправка SOAP-сообщения с помощью MTOM имеет значительные издержки для небольших двоичных нагрузок, но позволяет значительно сэкономить, когда нагрузка превышает несколько тысяч байт.</span><span class="sxs-lookup"><span data-stu-id="4eb52-118">Sending a SOAP message using MTOM has a noticeable overhead for small binary payloads, but becomes a great savings when they grow over a few thousand bytes.</span></span> <span data-ttu-id="4eb52-119">Причина заключается в том, что нормальный XML-текст кодирует двоичные данные с помощью Base64, который требует четыре символа на каждые три байта и увеличивает размер данных на одну треть.</span><span class="sxs-lookup"><span data-stu-id="4eb52-119">The reason for this is that normal text XML encodes binary data using Base64, which requires four characters for every three bytes, and increases the size of the data by one third.</span></span> <span data-ttu-id="4eb52-120">Механизм MTOM способен передавать двоичные данные в виде необработанных байтов, позволяя тем самым сэкономить время на кодирование/декодирование и способствуя уменьшению размера сообщений.</span><span class="sxs-lookup"><span data-stu-id="4eb52-120">MTOM is able to transmit binary data as raw bytes, saving the encoding/decoding time and resulting is smaller messages.</span></span> <span data-ttu-id="4eb52-121">Порог в несколько тысяч байт мал по сравнению с размером современных деловых документов и цифровых фотографий.</span><span class="sxs-lookup"><span data-stu-id="4eb52-121">The threshold of a few thousand bytes is small when compared to today's business documents and digital photographs.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4eb52-122">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="4eb52-122">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="4eb52-123">Установите ASP.NET 4,0 с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="4eb52-123">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="4eb52-124">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4eb52-124">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="4eb52-125">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4eb52-125">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="4eb52-126">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4eb52-126">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
