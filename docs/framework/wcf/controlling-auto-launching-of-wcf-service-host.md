---
title: Управление автозапуском узла службы WCF
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: 806d85df2a7fff63704db755400b81cc2dc5c37b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64652090"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="1613a-102">Управление автозапуском узла службы WCF</span><span class="sxs-lookup"><span data-stu-id="1613a-102">Controlling Auto-launching of WCF Service Host</span></span>
<span data-ttu-id="1613a-103">Вы можете управлять возможностью автозапуска узла службы Windows Communication Foundation (WCF) (WcfSvcHost.exe) для проекта библиотеки служб WCF при отладке другого проекта в том же решении Visual Studio, содержащего несколько проектов.</span><span class="sxs-lookup"><span data-stu-id="1613a-103">You can control the auto-launching capability of Windows Communication Foundation (WCF) Service Host (WcfSvcHost.exe) for a WCF Service Library project, when you debug another project in the same Visual Studio solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="1613a-104">Чтобы сделать это, щелкните правой кнопкой мыши проект службы WCF в **обозревателе решений**, выберите **свойства**и нажмите кнопку **параметры WCF** вкладки. **Запуск узла службы WCF при отладке другого проекта в одном решении** флажок установлен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1613a-104">To do so, right-click the WCF Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="1613a-105">Можно снять этот флажок, чтобы узел службы WCF для заданного проекта не запускается при отладке другого проекта в одном решении.</span><span class="sxs-lookup"><span data-stu-id="1613a-105">You can clear the box so that WCF Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="1613a-106">Это поведение не оказывает влияние на отладку по клавише F5 или на функциональные возможности добавления ссылки на службу для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="1613a-106">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="1613a-107">Эта возможность доступна в следующих проектах.</span><span class="sxs-lookup"><span data-stu-id="1613a-107">This option is available to the following projects:</span></span>  
  
- <span data-ttu-id="1613a-108">Проект библиотеки службы WCF.</span><span class="sxs-lookup"><span data-stu-id="1613a-108">WCF Service Library Project.</span></span>  
  
- <span data-ttu-id="1613a-109">Проект библиотеки службы последовательного рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1613a-109">Sequential Workflow Service Library Project.</span></span>  
  
- <span data-ttu-id="1613a-110">Проект библиотеки рабочего процесса конечного автомата.</span><span class="sxs-lookup"><span data-stu-id="1613a-110">State Machine Workflow Service Library Project.</span></span>  
  
- <span data-ttu-id="1613a-111">Проект библиотеки служб синдикации.</span><span class="sxs-lookup"><span data-stu-id="1613a-111">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1613a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="1613a-112">See also</span></span>

- [<span data-ttu-id="1613a-113">Узел службы WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="1613a-113">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
