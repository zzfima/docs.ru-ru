---
title: "Управление автозапуском узла службы WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dc89ed3ae41471af49fc92f31834f0ae268309dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="a48e6-102">Управление автозапуском узла службы WCF</span><span class="sxs-lookup"><span data-stu-id="a48e6-102">Controlling Auto-launching of WCF Service Host</span></span>
<span data-ttu-id="a48e6-103">Можно управлять возможностью автозапуска узла службы [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] (WcfSvcHost.exe) для проекта библиотеки службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] при отладке другого проекта в одном решении [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], которое содержит несколько проектов.</span><span class="sxs-lookup"><span data-stu-id="a48e6-103">You can control the auto-launching capability of [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] Service Host (WcfSvcHost.exe) for a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Library project, when you debug another project in the same [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="a48e6-104">Чтобы сделать это, щелкните правой кнопкой мыши [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] проект службы в **обозревателе решений**, выберите **свойства**и нажмите кнопку **параметры WCF** вкладки. **Запуск узла службы WCF при отладке другого проекта того же решения** флажок установлен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a48e6-104">To do so, right-click the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="a48e6-105">Можно снять этот флажок, чтобы узел службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] не запускался для заданного проекта при отладке другого проекта в одном решении.</span><span class="sxs-lookup"><span data-stu-id="a48e6-105">You can clear the box so that [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="a48e6-106">Это поведение не оказывает влияние на отладку по клавише F5 или на функциональные возможности добавления ссылки на службу для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="a48e6-106">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="a48e6-107">Эта возможность доступна в следующих проектах.</span><span class="sxs-lookup"><span data-stu-id="a48e6-107">This option is available to the following projects:</span></span>  
  
-   <span data-ttu-id="a48e6-108">Проект библиотеки служб [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a48e6-108">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Library Project.</span></span>  
  
-   <span data-ttu-id="a48e6-109">Проект библиотеки службы последовательного рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a48e6-109">Sequential Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="a48e6-110">Проект библиотеки рабочего процесса конечного автомата.</span><span class="sxs-lookup"><span data-stu-id="a48e6-110">State Machine Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="a48e6-111">Проект библиотеки служб синдикации.</span><span class="sxs-lookup"><span data-stu-id="a48e6-111">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a48e6-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a48e6-112">See Also</span></span>  
 [<span data-ttu-id="a48e6-113">Узел службы WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="a48e6-113">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
