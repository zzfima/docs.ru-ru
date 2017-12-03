---
title: "Установка свойств Use и Style"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c09a0600-116f-41cf-900a-1b7e4ea4e300
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f6a8e4b990c7ae9815c8792c0be456463b10660b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="setting-the-use-and-style-properties"></a><span data-ttu-id="ac801-102">Установка свойств Use и Style</span><span class="sxs-lookup"><span data-stu-id="ac801-102">Setting the Use and Style Properties</span></span>
<span data-ttu-id="ac801-103">В этом образце кода показано, как использовать свойства Use и Style классов <xref:System.ServiceModel.XmlSerializerFormatAttribute> и <xref:System.ServiceModel.DataContractFormatAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ac801-103">This sample demonstrates how to use the Use and Style properties on the <xref:System.ServiceModel.XmlSerializerFormatAttribute> and the <xref:System.ServiceModel.DataContractFormatAttribute>.</span></span> <span data-ttu-id="ac801-104">Эти свойства влияют на форматирование сообщений.</span><span class="sxs-lookup"><span data-stu-id="ac801-104">These properties affect how messages are formatted.</span></span> <span data-ttu-id="ac801-105">По умолчанию тело сообщения форматируется с использованием стиля <xref:System.ServiceModel.OperationFormatStyle.Document>.</span><span class="sxs-lookup"><span data-stu-id="ac801-105">By default, the message body is formatted with the style set to <xref:System.ServiceModel.OperationFormatStyle.Document>.</span></span> <span data-ttu-id="ac801-106">Эти параметры можно задать либо на уровне контракта службы, либо на уровне контракта операции.</span><span class="sxs-lookup"><span data-stu-id="ac801-106">These settings can be specified at either the service contract level or the operation contract level.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac801-107">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="ac801-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ac801-108">Свойство <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> определяет форматирование метаданных WSDL службы.</span><span class="sxs-lookup"><span data-stu-id="ac801-108">The <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> style property determines how the WSDL metadata for the service is formatted.</span></span> <span data-ttu-id="ac801-109">Допустимые значения: <xref:System.ServiceModel.OperationFormatStyle.Document> и <xref:System.ServiceModel.OperationFormatStyle.Rpc>.</span><span class="sxs-lookup"><span data-stu-id="ac801-109">Possible values are <xref:System.ServiceModel.OperationFormatStyle.Document>, and <xref:System.ServiceModel.OperationFormatStyle.Rpc>.</span></span> <span data-ttu-id="ac801-110">Стиль RPC означает, что WSDL-представление сообщений, которыми осуществляется обмен в ходе операции, содержит такие же параметры, как при удаленном вызове процедур.</span><span class="sxs-lookup"><span data-stu-id="ac801-110">RPC means that the WSDL representation of messages exchanged for an operation contains parameters as if it were a remote procedure call.</span></span> <span data-ttu-id="ac801-111">Пример.</span><span class="sxs-lookup"><span data-stu-id="ac801-111">The following is an example.</span></span>  
  
```xml  
<wsdl:message name="IUseAndStyleCalculator_Add_InputMessage">  
  <wsdl:part name="n1" type="xsd:double"/>  
  <wsdl:part name="n2" type="xsd:double"/>  
</wsdl:message>  
```  
  
 <span data-ttu-id="ac801-112">При задании для стиля значения <xref:System.ServiceModel.OperationFormatStyle.Document> WSDL-представление будет содержать единственный элемент, представляющий документ, которым осуществляется обмен в ходе операции, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ac801-112">Setting the style to <xref:System.ServiceModel.OperationFormatStyle.Document> means that the WSDL representation contains a single element that represents the document that is exchanged for an operation as shown in the following example.</span></span>  
  
```xml  
<wsdl:message name="IUseAndStyleCalculator_Add_InputMessage">  
  <wsdl:part name="parameters" element="tns:Add"/>  
</wsdl:message>  
```  
  
 <span data-ttu-id="ac801-113">Свойство <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> определяет формат сообщения.</span><span class="sxs-lookup"><span data-stu-id="ac801-113">The <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> property determines the format of the message.</span></span> <span data-ttu-id="ac801-114">Возможные значения: <xref:System.ServiceModel.OperationFormatUse.Literal> и <xref:System.ServiceModel.OperationFormatUse.Encoded>. Значение по умолчанию: <xref:System.ServiceModel.OperationFormatUse.Literal>.</span><span class="sxs-lookup"><span data-stu-id="ac801-114">Possible values are <xref:System.ServiceModel.OperationFormatUse.Literal> and <xref:System.ServiceModel.OperationFormatUse.Encoded>; the default value is <xref:System.ServiceModel.OperationFormatUse.Literal>.</span></span> <span data-ttu-id="ac801-115">Значение Literal означает, что сообщение представляет собой литеральный экземпляр схемы в WSDL, как показано в следующем примере стиля Document/Literal.</span><span class="sxs-lookup"><span data-stu-id="ac801-115">Literal means that the message is a literal instance of the schema in the WSDL as shown in the following Document/ Literal example.</span></span>  
  
```xml  
<Add xmlns="http://Microsoft.ServiceModel.Samples">  
  <n1>100</n1>  
  <n2>15.99</n2>  
</Add>  
```  
  
 <span data-ttu-id="ac801-116">«Encoded» (закодировано) означает, что схемы в WSDL являются абстрактными спецификациями, которые кодируются в соответствии с правилами в разделе 5 спецификации SOAP 1.1.</span><span class="sxs-lookup"><span data-stu-id="ac801-116">Encoded means that the schemas in the WSDL are abstract specifications that are encoded according to the rules found in SOAP 1.1 section 5.</span></span> <span data-ttu-id="ac801-117">Далее приведен пример RPC/Encoded.</span><span class="sxs-lookup"><span data-stu-id="ac801-117">The following is an RPC/Encoded example.</span></span>  
  
```xml  
<q1:Add xmlns:q1="http://Microsoft.ServiceModel.Samples">  
  <n1 xsi:type="xsd:double" xmlns="">100</n1>  
  <n2 xsi:type="xsd:double" xmlns="">15.99</n2>  
</q1:Add>  
```  
  
 <span data-ttu-id="ac801-118">Профиль WS-I Basic Profile 1.0 запрещает использование стиля <xref:System.ServiceModel.OperationFormatUse.Encoded>, поэтому его следует использовать, только когда того требуют службы, созданные по устаревшим стандартам.</span><span class="sxs-lookup"><span data-stu-id="ac801-118">The WS-I Basic Profile 1.0 prohibits the use of <xref:System.ServiceModel.OperationFormatUse.Encoded> and you should only use it when required by legacy services.</span></span> <span data-ttu-id="ac801-119">Формат сообщений `Encoded` доступен только при использовании сериализатора XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="ac801-119">The `Encoded` message format is only available when using the XmlSerializer.</span></span>  
  
 <span data-ttu-id="ac801-120">Чтобы вы могли увидеть сообщения к отправке и получению этот пример построен на [трассировка и ведение журнала сообщений](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span><span class="sxs-lookup"><span data-stu-id="ac801-120">To allow you to see the messages being sent and received, this sample is based on the [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span></span> <span data-ttu-id="ac801-121">В конфигурацию службы и исходный код внесены изменения, позволяющие использовать трассировку и журнал сообщений.</span><span class="sxs-lookup"><span data-stu-id="ac801-121">The service configuration and source code have been modified to enable and utilize tracing and message logging.</span></span> <span data-ttu-id="ac801-122">Кроме того <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> настроена без безопасности, поэтому можно просмотреть сообщения в журнале в незашифрованном виде.</span><span class="sxs-lookup"><span data-stu-id="ac801-122">In addition, the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> has been configured without security, so the logged messages can be viewed in an unencrypted format.</span></span> <span data-ttu-id="ac801-123">В этих журналах трассировки (System.ServiceModel.e2e и Message.log) следует просмотреть при помощи [программы Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="ac801-123">The resulting trace logs (System.ServiceModel.e2e and Message.log) should be viewed by using the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="ac801-124">В конфигурации задана следующая папка для создания трассировок: C:\LOGS.</span><span class="sxs-lookup"><span data-stu-id="ac801-124">The traces are configured to be created in the C:\LOGS folder.</span></span> <span data-ttu-id="ac801-125">Создайте эту папку, прежде чем выполнять код из этого образца.</span><span class="sxs-lookup"><span data-stu-id="ac801-125">Create the folder before running the sample.</span></span> <span data-ttu-id="ac801-126">Чтобы просмотреть содержимое сообщения в средство просмотра трассировки, выберите **сообщения** в левой и правой области средства.</span><span class="sxs-lookup"><span data-stu-id="ac801-126">To view message contents in the Trace Viewer tool, select **Messages** in both the left and the right panes of the tool.</span></span>  
  
 <span data-ttu-id="ac801-127">В следующем примере кода приведен контракт службы, в котором свойству <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> задано значение <xref:System.ServiceModel.OperationFormatUse>, и вместо формата тела сообщения по умолчанию (<xref:System.ServiceModel.OperationFormatStyle>) задан формат <xref:System.ServiceModel.OperationFormatStyle.Document>.</span><span class="sxs-lookup"><span data-stu-id="ac801-127">The following code shows the service contract with the <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> property set to <xref:System.ServiceModel.OperationFormatUse> and the format of the message body changed from the default <xref:System.ServiceModel.OperationFormatStyle> to <xref:System.ServiceModel.OperationFormatStyle.Document>.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"),  
XmlSerializerFormat(Style = OperationFormatStyle.Rpc,   
                                 Use = OperationFormatUse.Encoded)]  
public interface IUseAndStyleCalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="ac801-128">Чтобы проверить различия между параметрами <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> и <xref:System.ServiceModel.XmlSerializerFormatAttribute.Style%2A>, измените их для службы, заново создайте клиент, выполните пример и просмотрите файл c:\logs\message.logs с помощью средства Service Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="ac801-128">To see the difference between the different <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> and <xref:System.ServiceModel.XmlSerializerFormatAttribute.Style%2A> settings, modify them in the service, regenerate the client, run the sample, and examine the c:\logs\message.logs file with the Service Trace Viewer tool.</span></span> <span data-ttu-id="ac801-129">Также проверьте влияние на метаданные, просмотрев страницу http://localhost/ServiceModelSamples/service.svc?wsdl.</span><span class="sxs-lookup"><span data-stu-id="ac801-129">Also observe the impact on the metadata by viewing http://localhost/ServiceModelSamples/service.svc?wsdl.</span></span> <span data-ttu-id="ac801-130">Метаданные служб обычно подразделяются на несколько страниц.</span><span class="sxs-lookup"><span data-stu-id="ac801-130">The metadata for services is typically broken up into multiple pages.</span></span> <span data-ttu-id="ac801-131">Основная страница с WSDL-кодом содержит привязки WSDL, но рекомендуется просмотреть страницу http://localhost/ServiceModelSamples/service.svc?wsdl=wsdl0 и проверить определения сообщений.</span><span class="sxs-lookup"><span data-stu-id="ac801-131">The main wsdl page contains the WSDL bindings, but view http://localhost/ServiceModelSamples/service.svc?wsdl=wsdl0 to observe the message definitions.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ac801-132">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="ac801-132">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ac801-133">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ac801-133">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="ac801-134">Создайте каталог C:\LOGS для регистрации сообщений.</span><span class="sxs-lookup"><span data-stu-id="ac801-134">Create a C:\LOGS directory for logging messages.</span></span> <span data-ttu-id="ac801-135">Предоставьте сетевой службе пользователя разрешение на запись в этот каталог.</span><span class="sxs-lookup"><span data-stu-id="ac801-135">Give the user Network Service write permissions for this directory.</span></span>  
  
3.  <span data-ttu-id="ac801-136">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ac801-136">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="ac801-137">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ac801-137">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ac801-138">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ac801-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ac801-139">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ac801-139">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ac801-140">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac801-140">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ac801-141">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="ac801-141">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\UseAndStyle`  
  
## <a name="see-also"></a><span data-ttu-id="ac801-142">См. также</span><span class="sxs-lookup"><span data-stu-id="ac801-142">See Also</span></span>
