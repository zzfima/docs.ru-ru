---
title: "Образец обнаружения службы с уникальным URI прослушивания"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a6d35b2-0469-43c8-a0c9-63623e3d2733
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 48b49def3f8f009eeb4ffa0204e9c616b5acfec7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="discover-a-service-with-unique-listen-uri-mode-sample"></a><span data-ttu-id="dc612-102">Образец обнаружения службы с уникальным URI прослушивания</span><span class="sxs-lookup"><span data-stu-id="dc612-102">Discover a Service with Unique Listen Uri Mode Sample</span></span>
<span data-ttu-id="dc612-103">В этом образце показано обнаружение службы, свойство <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> которой имеет значение <xref:System.ServiceModel.Description.ListenUriMode.Unique>.</span><span class="sxs-lookup"><span data-stu-id="dc612-103">This sample demonstrates how to discover a service that has the <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property set to <xref:System.ServiceModel.Description.ListenUriMode.Unique>.</span></span> <span data-ttu-id="dc612-104">Если свойство <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> имеет значение <xref:System.ServiceModel.Description.ListenUriMode.Unique>, то гарантируется уникальность ListenUri. Для этого задается уникальный порт либо к пути добавляется идентификатор GUID, чтобы сделать его уникальным.</span><span class="sxs-lookup"><span data-stu-id="dc612-104">When the <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property is set to <xref:System.ServiceModel.Description.ListenUriMode.Unique>, the ListenUri is ensured to be unique by either setting the port to be unique or for the path to be unique by appending a GUID.</span></span>  
  
### <a name="features-on-the-service"></a><span data-ttu-id="dc612-105">Функции на стороне службы</span><span class="sxs-lookup"><span data-stu-id="dc612-105">Features on the Service</span></span>  
 <span data-ttu-id="dc612-106">Свойство <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> устанавливается в значение <xref:System.ServiceModel.Description.ListenUriMode.Unique> для конечной точки TCP.</span><span class="sxs-lookup"><span data-stu-id="dc612-106">The <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property is set to <xref:System.ServiceModel.Description.ListenUriMode.Unique> for the TCP endpoint.</span></span> <span data-ttu-id="dc612-107">Затем для службы разрешается обнаружение через конечную точку <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="dc612-107">The service is then made discoverable over a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> endpoint.</span></span>  
  
### <a name="features-on-the-client"></a><span data-ttu-id="dc612-108">Функции на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="dc612-108">Features on the Client</span></span>  
 <span data-ttu-id="dc612-109">Этот клиент подключается к службе с использованием правильного `Via.Uri` или с помощью метода <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>.</span><span class="sxs-lookup"><span data-stu-id="dc612-109">This client connects to the service using the correct `Via.Uri` by using the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method.</span></span> <span data-ttu-id="dc612-110">Затем возвращенный методом объект <xref:System.ServiceModel.Discovery.FindResponse> запрашивается, чтобы определить, содержит ли он допустимый <xref:System.ServiceModel.Endpoint.ListenUri%2A> и отличается ли этот URI от `Address.Uri`.</span><span class="sxs-lookup"><span data-stu-id="dc612-110">The <xref:System.ServiceModel.Discovery.FindResponse> that is returned from the method is then queried for whether it contains a valid <xref:System.ServiceModel.Endpoint.ListenUri%2A> and whether it is different than `Address.Uri`.</span></span> <span data-ttu-id="dc612-111">Затем нужные сведения передаются в метод `InvokeCalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="dc612-111">The appropriate information is then passed to the `InvokeCalculatorService` method.</span></span> <span data-ttu-id="dc612-112">В методе `InvokeCalculatorService` свойство <xref:System.ServiceModel.Endpoint.ListenUri%2A> передается вызывающим объектом, а затем в конечную точку клиента добавляется `ClientViaBehavior` с правильным `Via.Uri`.</span><span class="sxs-lookup"><span data-stu-id="dc612-112">In the `InvokeCalculatorService` method, the <xref:System.ServiceModel.Endpoint.ListenUri%2A> was passed in by the caller, then a `ClientViaBehavior` with the correct `Via.Uri` is added to the client’s endpoint.</span></span>  
  
##### <a name="to-use-this-sample"></a><span data-ttu-id="dc612-113">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="dc612-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="dc612-114">Откройте файл UniqueListenUriMode.sln в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc612-114">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open UniqueListenUriMode.sln.</span></span>  
  
2.  <span data-ttu-id="dc612-115">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="dc612-115">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="dc612-116">Запустите приложение службы, созданное в папке [основной каталог решения]\service\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="dc612-116">Run the service application, which is generated in the [solution base directory]\service\bin\debug folder.</span></span>  
  
4.  <span data-ttu-id="dc612-117">Запустите клиентское приложение, созданное в папке [основной каталог решения]\Client\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="dc612-117">Run the client application, which is generated in the [solution base directory]\Client\bin\debug folder.</span></span>  
  
     <span data-ttu-id="dc612-118">Клиент определяет запущенную службу и записывает на консоль метаданные, опубликованные конечной точкой службы.</span><span class="sxs-lookup"><span data-stu-id="dc612-118">The client locates the running service and writes to the console the metadata published by the service’s endpoint.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dc612-119">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="dc612-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="dc612-120">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="dc612-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dc612-121">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dc612-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dc612-122">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="dc612-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\UniqueListenUriMode`  
  
## <a name="see-also"></a><span data-ttu-id="dc612-123">См. также</span><span class="sxs-lookup"><span data-stu-id="dc612-123">See Also</span></span>
