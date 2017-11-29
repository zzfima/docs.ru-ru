---
title: "Асинхронное взаимодействие"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1b9435342d73fc5cb292ee72781362146604ce9c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="asynchronous-communication"></a><span data-ttu-id="e2aaa-102">Асинхронное взаимодействие</span><span class="sxs-lookup"><span data-stu-id="e2aaa-102">Asynchronous Communication</span></span>
<span data-ttu-id="e2aaa-103">В этом образце показано взаимодействие между двумя разными службами [!INCLUDE[wf](../../../../includes/wf-md.md)], проходящее по умолчанию в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="e2aaa-103">This sample demonstrates how the communication between two different [!INCLUDE[wf](../../../../includes/wf-md.md)] services is done asynchronously by default.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="e2aaa-104">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="e2aaa-104">Demonstrates</span></span>  
 <span data-ttu-id="e2aaa-105">Асинхронное взаимодействие между службами [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2aaa-105">Asynchronous communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] services.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="e2aaa-106">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="e2aaa-106">Discussion</span></span>  
 <span data-ttu-id="e2aaa-107">В этом образце показано асинхронное взаимодействие между приложениями [!INCLUDE[wf1](../../../../includes/wf1-md.md)] с помощью действий отправки и получения сообщений, предоставляемых .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e2aaa-107">This sample shows how the communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] applications is done asynchronously by using the messaging activities provided by .NET Framework.</span></span>  
  
 <span data-ttu-id="e2aaa-108">Данный образец состоит из следующих трех проектов.</span><span class="sxs-lookup"><span data-stu-id="e2aaa-108">This sample consists of the following three projects.</span></span>  
  
 <span data-ttu-id="e2aaa-109">CreditCheckService</span><span class="sxs-lookup"><span data-stu-id="e2aaa-109">CreditCheckService</span></span>  
 <span data-ttu-id="e2aaa-110">Эта служба получает кредитную историю определенного лица или стоимость приобретаемого товара и принимает решение, следует ли предоставить этому лицу кредит.</span><span class="sxs-lookup"><span data-stu-id="e2aaa-110">This service receives the credit score of a particular person or the value of the item to acquire, and then decides whether the credit is given to the person.</span></span>  
  
 <span data-ttu-id="e2aaa-111">RentalApprovalService</span><span class="sxs-lookup"><span data-stu-id="e2aaa-111">RentalApprovalService</span></span>  
 <span data-ttu-id="e2aaa-112">Эта служба получает заявление от лица, которому требуется кредит.</span><span class="sxs-lookup"><span data-stu-id="e2aaa-112">This service receives an application from a person who is in need of some credit.</span></span> <span data-ttu-id="e2aaa-113">Эта служба взаимодействует в асинхронном режиме со службой `CreditCheckService` для принятия решения об одобрении заявки на кредит.</span><span class="sxs-lookup"><span data-stu-id="e2aaa-113">This service communicates asynchronously with the `CreditCheckService` to decide whether the credit application is valid.</span></span>  
  
 <span data-ttu-id="e2aaa-114">Клиент</span><span class="sxs-lookup"><span data-stu-id="e2aaa-114">Client</span></span>  
 <span data-ttu-id="e2aaa-115">Клиент связывается в синхронном режиме со службой `RentalApprovalService`, чтобы узнать, одобрено ли заявление на получение кредита.</span><span class="sxs-lookup"><span data-stu-id="e2aaa-115">The client communicates synchronously with the `RentalApprovalService` to know whether the credit is approved.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e2aaa-116">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="e2aaa-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="e2aaa-117">Щелкните правой кнопкой мыши **AsynchronousCommunication** решение, выберите команду **свойства**.</span><span class="sxs-lookup"><span data-stu-id="e2aaa-117">Right-click the **AsynchronousCommunication** solution and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="e2aaa-118">В **общие свойства**выберите **запускаемый проект**и выберите **несколько запускаемых проектов**.</span><span class="sxs-lookup"><span data-stu-id="e2aaa-118">In **Common Properties**, select **Startup Project**, and select **Multiple Startup Projects**.</span></span>  
  
3.  <span data-ttu-id="e2aaa-119">Переместить **RentalApprovalService** в первую позицию в списке, за которым следует **CreditCheckService**, за которым следует **клиента**.</span><span class="sxs-lookup"><span data-stu-id="e2aaa-119">Move **RentalApprovalService** to the first position in the list, followed by **CreditCheckService**, followed by **Client**.</span></span> <span data-ttu-id="e2aaa-120">Задать **запустить** действие для всех трех проектов.</span><span class="sxs-lookup"><span data-stu-id="e2aaa-120">Set the **Start** action on all three projects.</span></span>  
  
4.  <span data-ttu-id="e2aaa-121">Нажмите кнопку **ОК**, и нажмите клавишу F5 для запуска примера.</span><span class="sxs-lookup"><span data-stu-id="e2aaa-121">Click **OK**, and press F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e2aaa-122">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e2aaa-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e2aaa-123">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e2aaa-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e2aaa-124">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e2aaa-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e2aaa-125">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="e2aaa-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
