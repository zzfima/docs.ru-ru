---
title: Сообщения без оболочки
ms.date: 03/30/2017
ms.assetid: 019657bd-1f9b-4315-ad74-eaa4e7551ff6
ms.openlocfilehash: 81592910d8530cea2df5ec1fd8a8b1145350ef78
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143737"
---
# <a name="unwrapped-messages"></a><span data-ttu-id="b55de-102">Сообщения без оболочки</span><span class="sxs-lookup"><span data-stu-id="b55de-102">Unwrapped Messages</span></span>
<span data-ttu-id="b55de-103">В этом образце показаны сообщения без оболочки.</span><span class="sxs-lookup"><span data-stu-id="b55de-103">This sample demonstrates unwrapped messages.</span></span> <span data-ttu-id="b55de-104">По умолчанию текст сообщения форматируется так, чтобы параметры, которые передаются операциям службы, находились в оболочке.</span><span class="sxs-lookup"><span data-stu-id="b55de-104">By default, the message body is formatted such that the parameters to a service operation are wrapped.</span></span> <span data-ttu-id="b55de-105">В следующем образце показано заключенное в оболочку сообщение запроса `Add` для службы `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="b55de-105">The following sample shows an `Add` request message to the `ICalculator` service in wrapped mode.</span></span>  
  
```xml  
<s:Envelope
    xmlns:s="http://www.w3.org/2003/05/soap-envelope"  
    xmlns:a="http://schemas.xmlsoap.org/ws/2005/08/addressing">  
    <s:Header>  
        …  
    </s:Header>  
    <s:Body>  
      <Add xmlns="http://Microsoft.ServiceModel.Samples">  
        <n1>100</n1>  
        <n2>15.99</n2>  
      </Add>  
    </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="b55de-106">Элемент `<Add>` в теле сообщения выступает в роли оболочки для параметров `n1` и `n2`.</span><span class="sxs-lookup"><span data-stu-id="b55de-106">The `<Add>` element in the message body wraps the `n1` and `n2` parameters.</span></span> <span data-ttu-id="b55de-107">В следующем образце показано эквивалентное сообщение без оболочки.</span><span class="sxs-lookup"><span data-stu-id="b55de-107">In contrast, the following sample shows the equivalent message in the unwrapped mode.</span></span>  
  
```xml  
<s:Envelope
    xmlns:s="http://www.w3.org/2003/05/soap-envelope"
    xmlns:a="http://schemas.xmlsoap.org/ws/2005/08/addressing">  
    <s:Header>  
        ….  
    </s:Header>  
    <s:Body>  
      <n1 xmlns="http://Microsoft.ServiceModel.Samples">100</n1>  
      <n2 xmlns="http://Microsoft.ServiceModel.Samples">15.99</n2>  
    </s:Body>  
  </s:Envelope>  
</MessageLogTraceRecord>  
```  
  
 <span data-ttu-id="b55de-108">В этом сообщении параметры `n1` и `n2` не помещены в элемент-оболочку, а являются непосредственными дочерними элементами элемента soap body.</span><span class="sxs-lookup"><span data-stu-id="b55de-108">The unwrapped message does not wrap the `n1` and `n2` parameters in a containing element, they are direct children of the soap body element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b55de-109">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="b55de-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="b55de-110">В этом образце сообщение без оболочки создается путем применения атрибута <xref:System.ServiceModel.MessageContractAttribute> к типу параметра и типу возвращаемого значения операции службы, как показано в следующем образце кода.</span><span class="sxs-lookup"><span data-stu-id="b55de-110">In this sample, an unwrapped message is created by applying the <xref:System.ServiceModel.MessageContractAttribute> to the service operation parameter type and return value type as shown in the following sample code.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    ResponseMessage Add(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Subtract(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Multiply(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Divide(RequestMessage request);  
}  
  
//setting IsWrapped to false means the n1 and n2  
//members will be direct children of the soap body element  
[MessageContract(IsWrapped = false)]  
public class RequestMessage  
{  
    [MessageBodyMember]  
    private double n1;  
    [MessageBodyMember]  
    private double n2;  
    //…  
}  
  
//setting IsWrapped to false means the result  
//member will be a direct child of the soap body element  
[MessageContract(IsWrapped = false)]  
public class ResponseMessage  
{  
    [MessageBodyMember]  
    private double result;  
    //…  
}  
```  
  
 <span data-ttu-id="b55de-111">Для просмотра всех отправляемых и получаемых сообщений в этом образце используется трассировка.</span><span class="sxs-lookup"><span data-stu-id="b55de-111">To allow you to see the messages being sent and received, this sample uses tracing.</span></span> <span data-ttu-id="b55de-112">Кроме того, для привязки <xref:System.ServiceModel.WSHttpBinding> не были настроены параметры безопасности, чтобы сократить число заносимых в журнал сообщений.</span><span class="sxs-lookup"><span data-stu-id="b55de-112">In addition, the <xref:System.ServiceModel.WSHttpBinding> has been configured without security, to reduce the number of messages it logs.</span></span>  
  
 <span data-ttu-id="b55de-113">Полученный журнал трасс (c: 'журналы -Message.log) можно просмотреть с помощью [инструмента просмотра служебного следа (SvcTraceViewer.exe).](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)</span><span class="sxs-lookup"><span data-stu-id="b55de-113">The resulting trace log (c:\logs\Message.log) can be viewed by using the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="b55de-114">Для просмотра содержимого сообщений выберите **Сообщения** как в левом, так и в правом стекол инструмента Service Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="b55de-114">To view message contents, select **Messages** in both the left and the right panes of the Service Trace Viewer tool.</span></span> <span data-ttu-id="b55de-115">Этот образец настроен таким образом, чтобы журналы трассировки сохранялись в папке C:\LOGS.</span><span class="sxs-lookup"><span data-stu-id="b55de-115">Trace logs in this sample are configured to be generated into the C:\LOGS folder.</span></span> <span data-ttu-id="b55de-116">Создайте эту папку перед выполнением образца и предоставьте сетевой службе пользователя разрешение на запись в эту папку.</span><span class="sxs-lookup"><span data-stu-id="b55de-116">Create this folder before running the sample and give the user Network Service write permissions for this directory.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b55de-117">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="b55de-117">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="b55de-118">Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)</span><span class="sxs-lookup"><span data-stu-id="b55de-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="b55de-119">Создайте каталог C:\LOGS для регистрации сообщений.</span><span class="sxs-lookup"><span data-stu-id="b55de-119">Create a C:\LOGS directory for logging messages.</span></span> <span data-ttu-id="b55de-120">Предоставьте сетевой службе пользователя разрешение на запись в этот каталог.</span><span class="sxs-lookup"><span data-stu-id="b55de-120">Give the user Network Service write permissions for this directory.</span></span>  
  
3. <span data-ttu-id="b55de-121">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b55de-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="b55de-122">Чтобы запустить образец в одно- или кросс-машинной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="b55de-122">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b55de-123">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b55de-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b55de-124">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b55de-124">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="b55de-125">Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы.</span><span class="sxs-lookup"><span data-stu-id="b55de-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b55de-126">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="b55de-126">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Unwrapped`  
