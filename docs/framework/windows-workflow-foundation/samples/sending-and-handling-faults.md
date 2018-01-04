---
title: "Сбои при отправке и обработке"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98e8e04d-2ac9-4a33-ae08-462f757a7a14
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc91b431123ff8776910550151a7783b2690d383
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="sending-and-handling-faults"></a><span data-ttu-id="98f26-102">Сбои при отправке и обработке</span><span class="sxs-lookup"><span data-stu-id="98f26-102">Sending and Handling Faults</span></span>
<span data-ttu-id="98f26-103">В этом образце демонстрируется использование действий обмена сообщениями <xref:System.ServiceModel.Activities.SendReply> и <xref:System.ServiceModel.Activities.ReceiveReply> для отправки и получения сообщений об ожидаемых и непредвиденных ошибках.</span><span class="sxs-lookup"><span data-stu-id="98f26-103">This sample demonstrates how to use the <xref:System.ServiceModel.Activities.SendReply> and <xref:System.ServiceModel.Activities.ReceiveReply> messaging activities to send and receive expected and unexpected faults.</span></span> <span data-ttu-id="98f26-104">В этом сценарии первый запрос клиента дает в результате ожидаемую ошибку, которая была включена в коллекцию <xref:System.ServiceModel.Activities.Send.KnownTypes%2A>.</span><span class="sxs-lookup"><span data-stu-id="98f26-104">In this scenario, the first client request results in an expected fault that has been included in its <xref:System.ServiceModel.Activities.Send.KnownTypes%2A> collection.</span></span> <span data-ttu-id="98f26-105">Следующие несколько запросов клиентов приводят к получению непредвиденных ошибок, после чего последний запрос дает положительный результат.</span><span class="sxs-lookup"><span data-stu-id="98f26-105">The next few client requests result in receiving unexpected faults, before the final request succeeds.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="98f26-106">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="98f26-106">To use this sample</span></span>  
  
1.  <span data-ttu-id="98f26-107">Откройте [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] с повышенными разрешениями, щелкнув правой кнопкой мыши [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] значок и выбрав **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="98f26-107">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="98f26-108">Откройте файл решения Faults.sln.</span><span class="sxs-lookup"><span data-stu-id="98f26-108">Open the Faults.sln solution file.</span></span>  
  
3.  <span data-ttu-id="98f26-109">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="98f26-109">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="98f26-110">Запустите проект службы.</span><span class="sxs-lookup"><span data-stu-id="98f26-110">Run the service project.</span></span>  
  
    1.  <span data-ttu-id="98f26-111">В **обозревателе решений**, щелкните правой кнопкой мыши `FaultService` проект и выберите **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="98f26-111">In **Solution Explorer**, right-click the `FaultService` project and select **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="98f26-112">Нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="98f26-112">Press CTRL+F5.</span></span>  
  
5.  <span data-ttu-id="98f26-113">Откройте другую копию [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] с повышенными разрешениями, щелкнув правой кнопкой мыши [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] значок и выбрав **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="98f26-113">Open another copy of [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
6.  <span data-ttu-id="98f26-114">Откройте файл решения Faults.sln.</span><span class="sxs-lookup"><span data-stu-id="98f26-114">Open the Faults.sln solution file.</span></span>  
  
7.  <span data-ttu-id="98f26-115">Запустите клиентский проект.</span><span class="sxs-lookup"><span data-stu-id="98f26-115">Run the client project.</span></span>  
  
    1.  <span data-ttu-id="98f26-116">В **обозревателе решений**, щелкните правой кнопкой мыши `FaultClient` проект и выберите **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="98f26-116">In **Solution Explorer**, right-click the `FaultClient` project and select **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="98f26-117">Нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="98f26-117">Press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="98f26-118">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="98f26-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="98f26-119">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="98f26-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="98f26-120">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98f26-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="98f26-121">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="98f26-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Faults`