---
title: Транспорт и кодировка пользовательской привязки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c0b353d-79ee-4e61-b348-be49ad0e9a16
ms.openlocfilehash: 1bb7b227c3b46133616ff7cb3f59e2005c0fa340
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715489"
---
# <a name="custom-binding-transport-and-encoding"></a><span data-ttu-id="c9e61-102">Транспорт и кодировка пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="c9e61-102">Custom Binding Transport and Encoding</span></span>
<span data-ttu-id="c9e61-103">Пользовательская привязка определяется упорядоченным списком отдельных элементов привязки.</span><span class="sxs-lookup"><span data-stu-id="c9e61-103">A custom binding is defined by an ordered list of discrete binding elements.</span></span> <span data-ttu-id="c9e61-104">Этот образец демонстрирует, как настроить пользовательскую привязку с различными элементами транспорта и кодирования сообщений.</span><span class="sxs-lookup"><span data-stu-id="c9e61-104">This sample demonstrates how to configure a custom binding with various transport and message encoding elements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c9e61-105">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="c9e61-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="c9e61-106">Этот пример основан на [собственном узле](../../../../docs/framework/wcf/samples/self-host.md)и был изменен для настройки трех конечных точек для поддержки транспортов HTTP, TCP и помощью канала NamedPipe с пользовательскими привязками.</span><span class="sxs-lookup"><span data-stu-id="c9e61-106">This sample is based on the [Self-Host](../../../../docs/framework/wcf/samples/self-host.md), and has been modified to configure three endpoints to support HTTP, TCP, and NamedPipe transports with custom bindings.</span></span> <span data-ttu-id="c9e61-107">Конфигурация клиента была изменена аналогичным образом, а код клиента изменен для взаимодействия с каждой из этих трех конечных точек.</span><span class="sxs-lookup"><span data-stu-id="c9e61-107">The client configuration was similarly modified, and the client code changed to communicate with each of the three endpoints.</span></span>  
  
 <span data-ttu-id="c9e61-108">Этот образец демонстрирует, как настроить пользовательскую привязку, поддерживающую определенные транспорт и кодирование сообщений.</span><span class="sxs-lookup"><span data-stu-id="c9e61-108">The sample demonstrates a how to configure a custom binding that supports a particular transport and message encoding.</span></span> <span data-ttu-id="c9e61-109">Это достигается путем настройки транспорта и кодирования сообщений для элемента `binding`.</span><span class="sxs-lookup"><span data-stu-id="c9e61-109">This is accomplished by configuring a transport and a message encoding for the `binding` element.</span></span> <span data-ttu-id="c9e61-110">Порядок элементов привязки важен для определения пользовательской привязки, так как каждый из них представляет слой в стеке каналов (см. раздел [пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md)).</span><span class="sxs-lookup"><span data-stu-id="c9e61-110">The ordering of binding elements is important in defining a custom binding, because each represents a layer in the channel stack (see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md)).</span></span> <span data-ttu-id="c9e61-111">В этом образце настраиваются три пользовательские привязки: транспорт HTTP с текстовым кодированием, транспорт TCP с текстовым кодированием и транспорт NamedPipe с двоичным кодированием.</span><span class="sxs-lookup"><span data-stu-id="c9e61-111">This sample configures three custom bindings: an HTTP transport with text encoding, a TCP transport with text encoding, and a NamedPipe transport with a binary encoding.</span></span>  
  
 <span data-ttu-id="c9e61-112">Конфигурация службы определяет пользовательскую привязку следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c9e61-112">The service configuration defines the custom bindings as follows:</span></span>  
  
```xml  
<bindings>  
    <customBinding>  
        <binding name="HttpBinding" >  
            <textMessageEncoding   
                messageVersion="Soap12Addressing10"/>  
            <httpTransport />  
        </binding>  
        <binding name="TcpBinding" >  
            <textMessageEncoding />  
            <tcpTransport />  
        </binding>  
        <binding name="NamedPipeBinding" >  
            <binaryMessageEncoding />  
            <namedPipeTransport />  
        </binding>  
    </customBinding>  
</bindings>  
```  
  
 <span data-ttu-id="c9e61-113">При выполнении образца запросы и ответы операций отображаются в окнах консоли как службы, так и клиента.</span><span class="sxs-lookup"><span data-stu-id="c9e61-113">When you run the sample, the operation requests and responses are displayed in both the service and client console window.</span></span> <span data-ttu-id="c9e61-114">Клиент взаимодействует с каждой из трех конечных точек, обращаясь сначала к HTTP, затем к TCP и, наконец, к NamedPipe.</span><span class="sxs-lookup"><span data-stu-id="c9e61-114">The client communicates with each of the three endpoints, accessing first HTTP, then TCP, and finally NamedPipe.</span></span> <span data-ttu-id="c9e61-115">Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.</span><span class="sxs-lookup"><span data-stu-id="c9e61-115">Press ENTER in each console window to shut down the service and client.</span></span>  
  
 <span data-ttu-id="c9e61-116">Привязка `namedPipeTransport` не поддерживает операции между компьютерами.</span><span class="sxs-lookup"><span data-stu-id="c9e61-116">The `namedPipeTransport` binding does not support machine-to-machine operations.</span></span> <span data-ttu-id="c9e61-117">Она служит только для связи на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c9e61-117">It is used only for communication on the same machine.</span></span> <span data-ttu-id="c9e61-118">Поэтому при выполнении этого образца на нескольких компьютерах закомментируйте следующие строки в файле кода клиента:</span><span class="sxs-lookup"><span data-stu-id="c9e61-118">Therefore, when running the sample in a cross-machine scenario, comment out the following lines in the client code file:</span></span>  
  
```csharp  
CalculatorClient client = new CalculatorClient("default");  
Console.WriteLine("Communicate with named pipe endpoint.");  
// Call operations.  
DoCalculations(client);  
//Closing the client gracefully closes the connection and cleans up resources  
client.Close();  
```  
  
```vb  
Dim client As New CalculatorClient("default")  
Console.WriteLine("Communicate with named pipe endpoint.")  
' call operations  
DoCalculations(client)  
'Closing the client gracefully closes the connection and cleans up resources  
client.Close()  
```  
  
> [!NOTE]
> <span data-ttu-id="c9e61-119">Если для восстановления конфигурации этого образца используется программа Svcutil.exe, измените имя конечной точки в конфигурации клиента, чтобы оно соответствовало клиентскому коду.</span><span class="sxs-lookup"><span data-stu-id="c9e61-119">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c9e61-120">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="c9e61-120">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="c9e61-121">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c9e61-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="c9e61-122">Чтобы создать выпуск C#решения C++, или Visual Basic .NET, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c9e61-122">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="c9e61-123">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c9e61-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c9e61-124">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c9e61-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c9e61-125">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="c9e61-125">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="c9e61-126">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="c9e61-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c9e61-127">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="c9e61-127">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\Transport`  
