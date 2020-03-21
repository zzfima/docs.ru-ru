---
title: Асинхронное взаимодействие
ms.date: 03/30/2017
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
ms.openlocfilehash: e1bc63b5d3178b8e98350dedd8eb0791e0e35589
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142880"
---
# <a name="asynchronous-communication"></a><span data-ttu-id="1ebea-102">Асинхронное взаимодействие</span><span class="sxs-lookup"><span data-stu-id="1ebea-102">Asynchronous Communication</span></span>
<span data-ttu-id="1ebea-103">Этот пример показывает, как связь между двумя различными службами Windows Workflow Flowflow Foundation (WF) осуществляется асинхронно по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1ebea-103">This sample demonstrates how the communication between two different Windows Workflow Foundation (WF) services is done asynchronously by default.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="1ebea-104">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="1ebea-104">Demonstrates</span></span>  
 <span data-ttu-id="1ebea-105">Асинхронное взаимодействие между службами [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ebea-105">Asynchronous communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] services.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="1ebea-106">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="1ebea-106">Discussion</span></span>  
 <span data-ttu-id="1ebea-107">В этом образце показано асинхронное взаимодействие между приложениями [!INCLUDE[wf1](../../../../includes/wf1-md.md)] с помощью действий отправки и получения сообщений, предоставляемых .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1ebea-107">This sample shows how the communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] applications is done asynchronously by using the messaging activities provided by .NET Framework.</span></span>  
  
 <span data-ttu-id="1ebea-108">Данный образец состоит из следующих трех проектов.</span><span class="sxs-lookup"><span data-stu-id="1ebea-108">This sample consists of the following three projects.</span></span>  
  
 <span data-ttu-id="1ebea-109">CreditCheckService</span><span class="sxs-lookup"><span data-stu-id="1ebea-109">CreditCheckService</span></span>  
 <span data-ttu-id="1ebea-110">Эта служба получает кредитную историю определенного лица или стоимость приобретаемого товара и принимает решение, следует ли предоставить этому лицу кредит.</span><span class="sxs-lookup"><span data-stu-id="1ebea-110">This service receives the credit score of a particular person or the value of the item to acquire, and then decides whether the credit is given to the person.</span></span>  
  
 <span data-ttu-id="1ebea-111">RentalApprovalService</span><span class="sxs-lookup"><span data-stu-id="1ebea-111">RentalApprovalService</span></span>  
 <span data-ttu-id="1ebea-112">Эта служба получает заявление от лица, которому требуется кредит.</span><span class="sxs-lookup"><span data-stu-id="1ebea-112">This service receives an application from a person who is in need of some credit.</span></span> <span data-ttu-id="1ebea-113">Эта служба взаимодействует в асинхронном режиме со службой `CreditCheckService` для принятия решения об одобрении заявки на кредит.</span><span class="sxs-lookup"><span data-stu-id="1ebea-113">This service communicates asynchronously with the `CreditCheckService` to decide whether the credit application is valid.</span></span>  
  
 <span data-ttu-id="1ebea-114">клиент</span><span class="sxs-lookup"><span data-stu-id="1ebea-114">Client</span></span>  
 <span data-ttu-id="1ebea-115">Клиент связывается в синхронном режиме со службой `RentalApprovalService`, чтобы узнать, одобрено ли заявление на получение кредита.</span><span class="sxs-lookup"><span data-stu-id="1ebea-115">The client communicates synchronously with the `RentalApprovalService` to know whether the credit is approved.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1ebea-116">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="1ebea-116">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="1ebea-117">Нажмите правой кнопкой мыши на решение **AsynchronousCommunication** и выберите **Свойства.**</span><span class="sxs-lookup"><span data-stu-id="1ebea-117">Right-click the **AsynchronousCommunication** solution and select **Properties**.</span></span>  
  
2. <span data-ttu-id="1ebea-118">В **общих свойствах**выберите **Startup Project**и выберите **несколько проектов запуска.**</span><span class="sxs-lookup"><span data-stu-id="1ebea-118">In **Common Properties**, select **Startup Project**, and select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="1ebea-119">Переместить **RentalApprovalService** на первую позицию в списке, а затем **CreditCheckService**, а затем **клиент**.</span><span class="sxs-lookup"><span data-stu-id="1ebea-119">Move **RentalApprovalService** to the first position in the list, followed by **CreditCheckService**, followed by **Client**.</span></span> <span data-ttu-id="1ebea-120">Установите действие **«Пуск»** по всем трем проектам.</span><span class="sxs-lookup"><span data-stu-id="1ebea-120">Set the **Start** action on all three projects.</span></span>  
  
4. <span data-ttu-id="1ebea-121">Нажмите **OK**, и нажмите F5 для запуска образца.</span><span class="sxs-lookup"><span data-stu-id="1ebea-121">Click **OK**, and press F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1ebea-122">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1ebea-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1ebea-123">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="1ebea-123">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="1ebea-124">Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы.</span><span class="sxs-lookup"><span data-stu-id="1ebea-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1ebea-125">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="1ebea-125">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
