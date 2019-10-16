---
title: Управление автозапуском узла службы WCF
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: 7f21cd7ea600277461146387b962a89ea0a8472b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320627"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="1e5d4-102">Управление автозапуском узла службы WCF</span><span class="sxs-lookup"><span data-stu-id="1e5d4-102">Controlling Auto-launching of WCF Service Host</span></span>
<span data-ttu-id="1e5d4-103">Вы можете управлять возможностью автоматического запуска узла службы Windows Communication Foundation (WCF) (WcfSvcHost. exe) для проекта библиотеки служб WCF при отладке другого проекта в том же решении Visual Studio, которое содержит несколько проектов.</span><span class="sxs-lookup"><span data-stu-id="1e5d4-103">You can control the auto-launching capability of Windows Communication Foundation (WCF) Service Host (WcfSvcHost.exe) for a WCF Service Library project, when you debug another project in the same Visual Studio solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="1e5d4-104">Для этого щелкните правой кнопкой мыши проект службы WCF в **Обозреватель решений**, выберите пункт **Свойства**и щелкните вкладку **параметры WCF** . Флажок **запустить узел службы WCF при отладке другого проекта в том же решении** включен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1e5d4-104">To do so, right-click the WCF Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="1e5d4-105">Можно снять флажок, чтобы узел службы WCF для этого конкретного проекта не запускался при отладке другого проекта в том же решении.</span><span class="sxs-lookup"><span data-stu-id="1e5d4-105">You can clear the box so that WCF Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="1e5d4-106">Это поведение не оказывает влияние на отладку по клавише F5 или на функциональные возможности добавления ссылки на службу для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="1e5d4-106">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="1e5d4-107">Эта возможность доступна в следующих проектах.</span><span class="sxs-lookup"><span data-stu-id="1e5d4-107">This option is available to the following projects:</span></span>  
  
- <span data-ttu-id="1e5d4-108">Проект библиотеки службы WCF.</span><span class="sxs-lookup"><span data-stu-id="1e5d4-108">WCF Service Library Project.</span></span>  
  
- <span data-ttu-id="1e5d4-109">Проект библиотеки службы последовательного рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1e5d4-109">Sequential Workflow Service Library Project.</span></span>  
  
- <span data-ttu-id="1e5d4-110">Проект библиотеки рабочего процесса конечного автомата.</span><span class="sxs-lookup"><span data-stu-id="1e5d4-110">State Machine Workflow Service Library Project.</span></span>  
  
- <span data-ttu-id="1e5d4-111">Проект библиотеки служб синдикации.</span><span class="sxs-lookup"><span data-stu-id="1e5d4-111">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e5d4-112">См. также</span><span class="sxs-lookup"><span data-stu-id="1e5d4-112">See also</span></span>

- [<span data-ttu-id="1e5d4-113">Узел службы WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="1e5d4-113">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)
