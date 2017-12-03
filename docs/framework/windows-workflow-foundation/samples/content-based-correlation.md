---
title: "Корреляция по содержимому"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8638b5d6-1d59-456d-8acd-179a5b39b260
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b5fea83ff6ac73fc26c419d9f7d5e8c5fe571135
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="content-based-correlation"></a><span data-ttu-id="6a50f-102">Корреляция по содержимому</span><span class="sxs-lookup"><span data-stu-id="6a50f-102">Content-Based Correlation</span></span>
<span data-ttu-id="6a50f-103">В этом образце демонстрируется, как действия по обмену сообщениями (<xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, и <xref:System.ServiceModel.Activities.ReceiveReply>) могут использоваться с несколькими корреляциями на основе содержимого, и одной корреляцией на основе содержимого.</span><span class="sxs-lookup"><span data-stu-id="6a50f-103">This sample demonstrates how the messaging activities (<xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply>) can be used with multiple content-based correlations.and content-based correlation.</span></span> <span data-ttu-id="6a50f-104">В этом сценарии корреляция сначала запускается на основе идентификатора заказа на покупку, затем создается другая корреляция на основе идентификатора клиента.</span><span class="sxs-lookup"><span data-stu-id="6a50f-104">In this scenario, a correlation is first initialized based on a purchase order ID, and then another correlation is created later based on the customer ID.</span></span> <span data-ttu-id="6a50f-105">Это показывает, как действие <xref:System.ServiceModel.Activities.Receive> может как следовать существующей корреляции, так и запускать новую корреляцию на основе одного и того же входящего сообщения.</span><span class="sxs-lookup"><span data-stu-id="6a50f-105">This shows how a <xref:System.ServiceModel.Activities.Receive> activity can both follow an existing correlation and initialize a new correlation based on the same incoming message.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="6a50f-106">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="6a50f-106">Demonstrates</span></span>  
 <span data-ttu-id="6a50f-107">Действия обмена сообщениями и корреляция на основе содержимого.</span><span class="sxs-lookup"><span data-stu-id="6a50f-107">Messaging activities and content-based correlation</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="6a50f-108">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="6a50f-108">Discussion</span></span>  
 <span data-ttu-id="6a50f-109">В этом образце показано использование нескольких корреляции на основе содержимого.</span><span class="sxs-lookup"><span data-stu-id="6a50f-109">This sample shows how to use multiple content-based correlations.</span></span>  <span data-ttu-id="6a50f-110">В этом сценарии корреляция сначала запускается на основе идентификатора заказа на покупку, затем создается другая корреляция на основе идентификатора клиента.</span><span class="sxs-lookup"><span data-stu-id="6a50f-110">In this scenario, a correlation is first initialized based on a purchase order ID, and then another correlation is created later based on the customer ID.</span></span>  <span data-ttu-id="6a50f-111">Корреляции каскадно выводятся действием <xref:System.ServiceModel.Activities.Receive>, которое как следует существующей корреляции (идентификатора заказа на покупку), так и запускает новую корреляцию (идентификатор клиента) на основе одного и того же входящего сообщения.</span><span class="sxs-lookup"><span data-stu-id="6a50f-111">The correlations are cascaded using a <xref:System.ServiceModel.Activities.Receive> activity that both follows an existing correlation (PurchaseOrderId) and initializes a new correlation (CustomerId) based on the same incoming message.</span></span>  <span data-ttu-id="6a50f-112">Для осуществления этого действие <xref:System.ServiceModel.Activities.Receive> использует свойства <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>, <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> и <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>.</span><span class="sxs-lookup"><span data-stu-id="6a50f-112">To accomplish this, the <xref:System.ServiceModel.Activities.Receive> activity uses the <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>, <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> and <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> properties.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="6a50f-113">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="6a50f-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="6a50f-114">Откройте [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] с повышенными разрешениями, щелкнув правой кнопкой мыши [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] значок и выбрав **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="6a50f-114">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="6a50f-115">Используя [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], откройте файл решения CascadingCorrelation.sln.</span><span class="sxs-lookup"><span data-stu-id="6a50f-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the CascadingCorrelation.sln solution file.</span></span>  
  
3.  <span data-ttu-id="6a50f-116">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="6a50f-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="6a50f-117">Для запуска сервера нажмите F5.</span><span class="sxs-lookup"><span data-stu-id="6a50f-117">To run the server, press F5.</span></span>  
  
5.  <span data-ttu-id="6a50f-118">После того как служба готова к прослушиванию сообщений, щелкните правой кнопкой мыши проект «Клиент» в обозревателе решений и запустите его.</span><span class="sxs-lookup"><span data-stu-id="6a50f-118">Once the service is ready and listening for messages, in Solution Explorer, right-click the Client project and run it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6a50f-119">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="6a50f-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6a50f-120">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="6a50f-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6a50f-121">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6a50f-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6a50f-122">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="6a50f-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\ContentBasedCorrelation`