---
title: Управление автозапуском узла службы WCF
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: 63c3ca00c0cdc0b28de0fe245b616acd04ca50fe
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="352ee-102">Управление автозапуском узла службы WCF</span><span class="sxs-lookup"><span data-stu-id="352ee-102">Controlling Auto-launching of WCF Service Host</span></span>
<span data-ttu-id="352ee-103">Можно управлять возможностью автозапуска узла службы Windows Communication Foundation (WCF) (WcfSvcHost.exe) для проекта библиотеки службы WCF при отладке другого проекта того же решения Visual Studio содержит несколько проектов.</span><span class="sxs-lookup"><span data-stu-id="352ee-103">You can control the auto-launching capability of Windows Communication Foundation (WCF) Service Host (WcfSvcHost.exe) for a WCF Service Library project, when you debug another project in the same Visual Studio solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="352ee-104">Чтобы сделать это, щелкните правой кнопкой мыши проект службы WCF в **обозревателе решений**, выберите **свойства**и нажмите кнопку **параметры WCF** вкладки. **Запуск узла службы WCF при отладке другого проекта того же решения** флажок установлен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="352ee-104">To do so, right-click the WCF Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="352ee-105">Можно снять этот флажок, чтобы не запускается узел службы WCF для заданного проекта при отладке другого проекта в одном решении.</span><span class="sxs-lookup"><span data-stu-id="352ee-105">You can clear the box so that WCF Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="352ee-106">Это поведение не оказывает влияние на отладку по клавише F5 или на функциональные возможности добавления ссылки на службу для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="352ee-106">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="352ee-107">Эта возможность доступна в следующих проектах.</span><span class="sxs-lookup"><span data-stu-id="352ee-107">This option is available to the following projects:</span></span>  
  
-   <span data-ttu-id="352ee-108">Проект библиотеки службы WCF.</span><span class="sxs-lookup"><span data-stu-id="352ee-108">WCF Service Library Project.</span></span>  
  
-   <span data-ttu-id="352ee-109">Проект библиотеки службы последовательного рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="352ee-109">Sequential Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="352ee-110">Проект библиотеки рабочего процесса конечного автомата.</span><span class="sxs-lookup"><span data-stu-id="352ee-110">State Machine Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="352ee-111">Проект библиотеки служб синдикации.</span><span class="sxs-lookup"><span data-stu-id="352ee-111">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="352ee-112">См. также</span><span class="sxs-lookup"><span data-stu-id="352ee-112">See Also</span></span>  
 [<span data-ttu-id="352ee-113">Узел службы WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="352ee-113">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
