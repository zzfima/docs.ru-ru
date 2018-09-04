---
title: Образец настраиваемой компенсации
ms.date: 03/30/2017
ms.assetid: 385920da-9284-44bf-9fe9-0d87c7478ec5
ms.openlocfilehash: ac141a48f87f5b14f6b528f7b3ceb7fdddeaf2d2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43503723"
---
# <a name="custom-compensation-sample"></a><span data-ttu-id="f5fd0-102">Образец настраиваемой компенсации</span><span class="sxs-lookup"><span data-stu-id="f5fd0-102">Custom Compensation Sample</span></span>
<span data-ttu-id="f5fd0-103">В этом образце показано, как использовать действие <xref:System.Activities.Statements.CompensableActivity> и его обработчик компенсации для определения пользовательской логики компенсации.</span><span class="sxs-lookup"><span data-stu-id="f5fd0-103">This sample shows how to use <xref:System.Activities.Statements.CompensableActivity> and its compensation handler to define custom compensation logic.</span></span> <span data-ttu-id="f5fd0-104">В этом образце моделируется «Агентство по аренде грузовиков».</span><span class="sxs-lookup"><span data-stu-id="f5fd0-104">The scenario modeled in this sample is a Truck Rental Agency.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="f5fd0-105">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="f5fd0-105">Sample Details</span></span>  
 <span data-ttu-id="f5fd0-106">Выполняется моделирование следующих шагов.</span><span class="sxs-lookup"><span data-stu-id="f5fd0-106">The steps simulated are:</span></span>  
  
1.  <span data-ttu-id="f5fd0-107">Пользователь запрашивает тарифы на аренду грузовика на заданную дату.</span><span class="sxs-lookup"><span data-stu-id="f5fd0-107">The user requests truck rental quotes for a given date.</span></span>  
  
2.  <span data-ttu-id="f5fd0-108">Агентство связывается с тремя компаниями, предоставляющими грузовики, и предлагает три тарифа.</span><span class="sxs-lookup"><span data-stu-id="f5fd0-108">Three truck companies are contacted and the three quotes are provided.</span></span>  
  
3.  <span data-ttu-id="f5fd0-109">Пользователь выбирает один из тарифов на аренду грузовика и переходит к оформлению заказа и оплате с помощью кредитной карты.</span><span class="sxs-lookup"><span data-stu-id="f5fd0-109">The user selects one truck quote and proceeds to order by credit card.</span></span>  
  
4.  <span data-ttu-id="f5fd0-110">Приложение отменяет два других заказа.</span><span class="sxs-lookup"><span data-stu-id="f5fd0-110">The application cancels the other two truck quotes.</span></span>  
  
5.  <span data-ttu-id="f5fd0-111">Приложение взимает оплату за обслуживание, которая не возмещается для учетных записей, не относящихся к классу PREMIUM, если отмена происходит за 10 дней или менее до дня бронирования.</span><span class="sxs-lookup"><span data-stu-id="f5fd0-111">The application charges a service fee that is non-refundable for non-premium accounts if cancelation happens 10 days or less prior to the reservation date.</span></span>  
  
6.  <span data-ttu-id="f5fd0-112">Приложение взимает стоимость аренды грузовика.</span><span class="sxs-lookup"><span data-stu-id="f5fd0-112">The application charges the truck rental fee.</span></span>  
  
7.  <span data-ttu-id="f5fd0-113">Приложение ждет наступления даты бронирования или отмены бронирования заказчиком, в зависимости от того, какое из событий наступит первым.</span><span class="sxs-lookup"><span data-stu-id="f5fd0-113">The application waits until the reservation date or until the customer decided to cancel the reservation, whichever comes first.</span></span>  
  
8.  <span data-ttu-id="f5fd0-114">Если заказчик отменяет бронирование, выполняется пользовательская логика компенсации <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>, которая построена следующим образом.</span><span class="sxs-lookup"><span data-stu-id="f5fd0-114">If the customer cancels the reservation, the <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> custom compensation logic runs according to the following logic:</span></span>  
  
    1.  <span data-ttu-id="f5fd0-115">Если у заказчика нет учетной записи PREMIUM-класса, и до дня бронирования остается 10 дней или меньше, то с него взимается стоимость обслуживания, в противном случае приложение возмещает стоимость обслуживания.</span><span class="sxs-lookup"><span data-stu-id="f5fd0-115">If the customer has a non-premium account and it is less than 10 days prior to the reservation date, then the service fee is still charged; otherwise, the application refunds the service fee.</span></span>  
  
    2.  <span data-ttu-id="f5fd0-116">Оставшиеся компенсируемые действия (заказ грузовика + оплата заказа) выполняются в соответствии с логикой компенсации по умолчанию, которая заключается в компенсации в порядке, обратном порядку выполнения.</span><span class="sxs-lookup"><span data-stu-id="f5fd0-116">The rest of the compensable activities (truck order + truck order fee) are run according to the default compensation logic, which is to compensate in reverse order of execution.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f5fd0-117">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="f5fd0-117">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="f5fd0-118">Откройте решение CustomCompensation.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5fd0-118">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the CustomCompensation.sln solution.</span></span> <span data-ttu-id="f5fd0-119">Файл с решением находится в папке \WF\Basic\Compensation\CustomCompensation.</span><span class="sxs-lookup"><span data-stu-id="f5fd0-119">It is located in the \WF\Basic\Compensation\CustomCompensation directory.</span></span>  
  
2.  <span data-ttu-id="f5fd0-120">Чтобы построить решение, нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="f5fd0-120">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="f5fd0-121">Нажмите CTRL + F5, чтобы запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="f5fd0-121">Press CTRL + F5 to run the application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f5fd0-122">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f5fd0-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f5fd0-123">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="f5fd0-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f5fd0-124">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="f5fd0-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f5fd0-125">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="f5fd0-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CustomCompensation`