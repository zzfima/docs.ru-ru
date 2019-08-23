---
title: Практическое руководство. Создание рабочего процесса
ms.date: 03/30/2017
ms.assetid: 87234108-8e21-4cb3-9340-4a1a13f3f98c
ms.openlocfilehash: 7f0bef673ff14ded13306a1fc26e09695601799d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962299"
---
# <a name="how-to-create-a-workflow"></a><span data-ttu-id="85ea5-102">Практическое руководство. Создание рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="85ea5-102">How to: Create a Workflow</span></span>
<span data-ttu-id="85ea5-103">Рабочие процессы могут создаваться как из встроенных, так и из пользовательских действий.</span><span class="sxs-lookup"><span data-stu-id="85ea5-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="85ea5-104">В подразделах этого раздела описывается создание рабочего процесса, который использует как встроенные действия, такие как <xref:System.Activities.Statements.Flowchart> действие, так и пользовательские действия из предыдущего [практического руководства. Создание раздела действия](how-to-create-an-activity.md) .</span><span class="sxs-lookup"><span data-stu-id="85ea5-104">The topics in this section step through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="85ea5-105">Рабочий процесс моделирует игру по угадыванию числа.</span><span class="sxs-lookup"><span data-stu-id="85ea5-105">The workflow models a number guessing game.</span></span> <span data-ttu-id="85ea5-106">Для завершения учебника требуется только один из подразделов в этом разделе. Необходимо выбрать стиль, который вас интересует, и выполнить шаг.</span><span class="sxs-lookup"><span data-stu-id="85ea5-106">Only one of the topics in this section is required to complete the tutorial; you should pick the style that interests you and follow that step.</span></span> <span data-ttu-id="85ea5-107">Однако при необходимости можно завершить все подразделы.</span><span class="sxs-lookup"><span data-stu-id="85ea5-107">However, you may complete all of the topics if desired.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="85ea5-108">Каждый раздел в учебнике «Приступая к работе» построен на основе предыдущих разделов.</span><span class="sxs-lookup"><span data-stu-id="85ea5-108">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="85ea5-109">Для выполнения этой статьи сначала необходимо выполнить [следующие действия: Создайте действие](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="85ea5-109">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="85ea5-110">Чтобы скачать завершенную версию учебника, см. раздел [Windows Workflow Foundation (WF45), учебник "Приступая к работе"](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="85ea5-110">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="85ea5-111">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="85ea5-111">In This Section</span></span>  
 [<span data-ttu-id="85ea5-112">Практическое руководство. Создание последовательного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="85ea5-112">How to: Create a Sequential Workflow</span></span>](how-to-create-a-sequential-workflow.md)  
 <span data-ttu-id="85ea5-113">Описывает, как создать последовательный рабочий процесс с помощью действия <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="85ea5-113">Describes how to create a sequential workflow using the <xref:System.Activities.Statements.Sequence> activity.</span></span>  
  
 [<span data-ttu-id="85ea5-114">Практическое руководство. Создание рабочего процесса блок-схемы</span><span class="sxs-lookup"><span data-stu-id="85ea5-114">How to: Create a Flowchart Workflow</span></span>](how-to-create-a-flowchart-workflow.md)  
 <span data-ttu-id="85ea5-115">Описывает, как создать рабочий процесс блок-схемы с помощью действия <xref:System.Activities.Statements.Flowchart>.</span><span class="sxs-lookup"><span data-stu-id="85ea5-115">Describes how to create a flowchart workflow using the <xref:System.Activities.Statements.Flowchart> activity.</span></span>  
  
 [<span data-ttu-id="85ea5-116">Практическое руководство. Создание рабочего процесса конечного автомата</span><span class="sxs-lookup"><span data-stu-id="85ea5-116">How to: Create a State Machine Workflow</span></span>](how-to-create-a-state-machine-workflow.md)  
 <span data-ttu-id="85ea5-117">Описывает способы создания рабочего процесса конечного автомата с помощью действия <xref:System.Activities.Statements.StateMachine>.</span><span class="sxs-lookup"><span data-stu-id="85ea5-117">Describes how to create a state machine workflow using the <xref:System.Activities.Statements.StateMachine> activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85ea5-118">См. также</span><span class="sxs-lookup"><span data-stu-id="85ea5-118">See also</span></span>

- [<span data-ttu-id="85ea5-119">Программирование в Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="85ea5-119">Windows Workflow Foundation Programming</span></span>](programming.md)
