---
title: OperationContextScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11c11108-8eb4-4d49-95a0-83285a812262
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6f636fe5bc79c18634f2239bc403c5189531737b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="operationcontextscope"></a><span data-ttu-id="13c59-102">OperationContextScope</span><span class="sxs-lookup"><span data-stu-id="13c59-102">OperationContextScope</span></span>
<span data-ttu-id="13c59-103">В образце OperationContextScope показано, как при вызовах [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] передавать с помощью заголовков дополнительную информацию.</span><span class="sxs-lookup"><span data-stu-id="13c59-103">The OperationContextScope sample demonstrates how to send extra information on a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] call using headers.</span></span> <span data-ttu-id="13c59-104">В этом образце сервер и клиент являются консольными приложениями.</span><span class="sxs-lookup"><span data-stu-id="13c59-104">In this sample, both the server and client are console applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13c59-105">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="13c59-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="13c59-106">В образце показано, как клиент может отправлять дополнительную информацию в виде <xref:System.ServiceModel.Channels.MessageHeader>, используя для этого <xref:System.ServiceModel.OperationContextScope>.</span><span class="sxs-lookup"><span data-stu-id="13c59-106">The sample demonstrates how a client can send additional information as a <xref:System.ServiceModel.Channels.MessageHeader> using <xref:System.ServiceModel.OperationContextScope>.</span></span> <span data-ttu-id="13c59-107">Создается объект <xref:System.ServiceModel.OperationContextScope> с областью, соответствующей каналу.</span><span class="sxs-lookup"><span data-stu-id="13c59-107">An <xref:System.ServiceModel.OperationContextScope> object is created by scoping it to a channel.</span></span> <span data-ttu-id="13c59-108">В коллекцию <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> можно добавлять заголовки, которые нужно передать удаленной службе.</span><span class="sxs-lookup"><span data-stu-id="13c59-108">Headers that must be translated to the remote service can be added to the <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> collection.</span></span> <span data-ttu-id="13c59-109">Добавляемые в эту коллекцию заголовки можно извлекать на стороне службы через свойство <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>.</span><span class="sxs-lookup"><span data-stu-id="13c59-109">Headers added to this collection can be retrieved on the service by accessing <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>.</span></span> <span data-ttu-id="13c59-110">Вызовы осуществляются через различные каналы, но добавляемые к клиенту заголовки применяются только к каналу, с помощью которого был создан объект <xref:System.ServiceModel.OperationContextScope>.</span><span class="sxs-lookup"><span data-stu-id="13c59-110">Its calls are made on multiple channels and then the headers added to the client only apply to the channel that was used to create the <xref:System.ServiceModel.OperationContextScope>.</span></span>  
  
## <a name="messageheaderreader"></a><span data-ttu-id="13c59-111">MessageHeaderReader</span><span class="sxs-lookup"><span data-stu-id="13c59-111">MessageHeaderReader</span></span>  
 <span data-ttu-id="13c59-112">Это образец службы, которая получает сообщения от клиента и пытается найти заголовки в коллекции <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>.</span><span class="sxs-lookup"><span data-stu-id="13c59-112">This is the sample service that receives a message from the client and tries to look up the header in the <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A> collection.</span></span> <span data-ttu-id="13c59-113">Клиент передает идентификатор GUID, отправленный в заголовке, а служба извлекает пользовательский заголовок и, если имеется, сравнивает его с GUID, переданным клиентом в виде аргумента.</span><span class="sxs-lookup"><span data-stu-id="13c59-113">The client passes the GUID that it sent in the header and the service retrieves the custom header and, if present, compares it with the GUID passed as the argument by the client.</span></span>  
  
```  
public bool RetrieveHeader(string guid)  
{  
     MessageHeaders messageHeaderCollection =   
             OperationContext.Current.IncomingMessageHeaders;  
     String guidHeader = null;  
  
     Console.WriteLine("Trying to check if IncomingMessageHeader " +  
               " collection contains header with value {0}", guid);  
     if (messageHeaderCollection.FindHeader(  
                       CustomHeader.HeaderName,   
                       CustomHeader.HeaderNamespace) != -1)  
     {  
          guidHeader = messageHeaderCollection.GetHeader<String>(  
           CustomHeader.HeaderName, CustomHeader.HeaderNamespace);  
     }  
     else  
     {  
          Console.WriteLine("No header was found");  
     }  
     if (guidHeader != null)  
     {  
          Console.WriteLine("Found header with value {0}. "+   
         "Does it match with GUID sent as parameter: {1}",   
          guidHeader, guidHeader.Equals(guid));  
      }  
  
      Console.WriteLine();  
      //Return true if header is present and equals the guid sent by  
      // client as argument  
      return (guidHeader != null && guidHeader.Equals(guid));  
}  
```  
  
## <a name="messageheaderclient"></a><span data-ttu-id="13c59-114">MessageHeaderClient</span><span class="sxs-lookup"><span data-stu-id="13c59-114">MessageHeaderClient</span></span>  
 <span data-ttu-id="13c59-115">Это реализация клиента, использующего учетную запись-посредник, созданные [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для взаимодействия с удаленной службой.</span><span class="sxs-lookup"><span data-stu-id="13c59-115">This is the client implementation that uses the proxy generated by [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to communicate with the remote service.</span></span> <span data-ttu-id="13c59-116">Сначала создается два прокси-объекта `MessageHeaderReaderClient`.</span><span class="sxs-lookup"><span data-stu-id="13c59-116">It first creates two proxy objects of `MessageHeaderReaderClient`.</span></span>  
  
```  
//Create two clients to the remote service.  
MessageHeaderReaderClient client1 = new MessageHeaderReaderClient();  
MessageHeaderReaderClient client2 = new MessageHeaderReaderClient();  
```  
  
 <span data-ttu-id="13c59-117">Затем клиент создает область OperationContextScope, связанную с `client1`.</span><span class="sxs-lookup"><span data-stu-id="13c59-117">Client then creates an OperationContextScope and scopes it to `client1`.</span></span> <span data-ttu-id="13c59-118">Он добавляет заголовок <xref:System.ServiceModel.Channels.MessageHeader> в свойство <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> и осуществляет вызов на обоих клиентах.</span><span class="sxs-lookup"><span data-stu-id="13c59-118">It adds a <xref:System.ServiceModel.Channels.MessageHeader> to <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> and invokes one call on both clients.</span></span> <span data-ttu-id="13c59-119">Это гарантирует, что заголовок передается только в `client1` и не в `client2` , проверьте значение, возвращаемое `RetrieveHeader` вызова.</span><span class="sxs-lookup"><span data-stu-id="13c59-119">It ensures that the header is sent only on `client1` and not on `client2` by checking the return value from the `RetrieveHeader` call.</span></span>  
  
```  
using (new OperationContextScope(client1.InnerChannel))  
{  
    //Create a new GUID that is sent as the header.  
    String guid = Guid.NewGuid().ToString();  
  
    //Create a MessageHeader for the GUID we just created.  
    MessageHeader customHeader = MessageHeader.CreateHeader(CustomHeader.HeaderName, CustomHeader.HeaderNamespace, guid);  
  
    //Add the header to the OutgoingMessageHeader collection.  
    OperationContext.Current.OutgoingMessageHeaders.Add(customHeader);  
  
    //Now call RetreieveHeader on both the proxies. Since the OperationContextScope is tied to   
    //client1's InnerChannel, the header should only be added to calls made on that client.  
    //Calls made on client2 should not be sending the header across even though the call  
    //is made in the same OperationContextScope.  
    Console.WriteLine("Using client1 to send message");  
    Console.WriteLine("Did server retrieve the header? : Actual: {0}, Expected: True", client1.RetrieveHeader(guid));  
  
    Console.WriteLine();  
    Console.WriteLine("Using client2 to send message");  
    Console.WriteLine("Did server retrieve the header? : Actual: {0}, Expected: False", client2.RetrieveHeader(guid));  
}  
```  
  
 <span data-ttu-id="13c59-120">Этот образец размещается резидентно.</span><span class="sxs-lookup"><span data-stu-id="13c59-120">This sample is self-hosted.</span></span> <span data-ttu-id="13c59-121">Ниже показан образец результатов выполнения образца.</span><span class="sxs-lookup"><span data-stu-id="13c59-121">The following sample output from running the sample is provided:</span></span>  
  
```  
Prompt> Service.exe  
The service is ready.  
Press <ENTER> to terminate service.  
  
Trying to check if IncomingMessageHeader collection contains header with value 2239da67-546f-42d4-89dc-8eb3c06215d8  
Found header with value 2239da67-546f-42d4-89dc-8eb3c06215d8. Does it match with GUID sent as parameter: True  
  
Trying to check if IncomingMessageHeader collection contains header with value 2239da67-546f-42d4-89dc-8eb3c06215d8  
No header was found  
  
Prompt>Client.exe  
Using client1 to send message  
Did server retrieve the header? : Actual: True, Expected: True  
  
Using client2 to send message  
Did server retrieve the header? : Actual: False, Expected: False  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="13c59-122">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="13c59-122">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="13c59-123">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="13c59-123">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="13c59-124">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="13c59-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="13c59-125">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="13c59-125">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="13c59-126">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="13c59-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="13c59-127">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="13c59-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="13c59-128">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="13c59-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="13c59-129">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="13c59-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\OperationContextScope`  
  
## <a name="see-also"></a><span data-ttu-id="13c59-130">См. также</span><span class="sxs-lookup"><span data-stu-id="13c59-130">See Also</span></span>
