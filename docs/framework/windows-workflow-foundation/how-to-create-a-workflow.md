---
title: Как выполнить создать рабочий процесс
ms.date: 03/30/2017
ms.assetid: 87234108-8e21-4cb3-9340-4a1a13f3f98c
ms.openlocfilehash: 75af0e1dae43cb424dcd13f9f2540d65fbdca126
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559002"
---
# <a name="how-to-create-a-workflow"></a><span data-ttu-id="d4173-102">Как выполнить создать рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="d4173-102">How to: Create a Workflow</span></span>
<span data-ttu-id="d4173-103">Рабочие процессы могут создаваться как из встроенных, так и из пользовательских действий.</span><span class="sxs-lookup"><span data-stu-id="d4173-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="d4173-104">В подразделах этого раздела шаг по созданию рабочего процесса, который использует как встроенные действия, например <xref:System.Activities.Statements.Flowchart> действия и пользовательские действия из предыдущего [как: Создание действия](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="d4173-104">The topics in this section step through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="d4173-105">Рабочий процесс моделирует игру по угадыванию числа.</span><span class="sxs-lookup"><span data-stu-id="d4173-105">The workflow models a number guessing game.</span></span> <span data-ttu-id="d4173-106">Для завершения учебника требуется только один из подразделов в этом разделе. Необходимо выбрать стиль, который вас интересует, и выполнить шаг.</span><span class="sxs-lookup"><span data-stu-id="d4173-106">Only one of the topics in this section is required to complete the tutorial; you should pick the style that interests you and follow that step.</span></span> <span data-ttu-id="d4173-107">Однако при необходимости можно завершить все подразделы.</span><span class="sxs-lookup"><span data-stu-id="d4173-107">However, you may complete all of the topics if desired.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4173-108">Каждый раздел в учебнике «Приступая к работе» построен на основе предыдущих разделов.</span><span class="sxs-lookup"><span data-stu-id="d4173-108">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="d4173-109">Для изучения этого раздела, необходимо сначала выполнить [как: Создание действия](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="d4173-109">To complete this topic, you must first complete [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4173-110">Чтобы скачать завершенную версию учебника, см. раздел [Windows Workflow Foundation (WF45), учебник "Приступая к работе"](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="d4173-110">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d4173-111">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="d4173-111">In This Section</span></span>  
 [<span data-ttu-id="d4173-112">Практическое руководство. Создание последовательного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="d4173-112">How to: Create a Sequential Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-sequential-workflow.md)  
 <span data-ttu-id="d4173-113">Описывает, как создать последовательный рабочий процесс с помощью действия <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="d4173-113">Describes how to create a sequential workflow using the <xref:System.Activities.Statements.Sequence> activity.</span></span>  
  
 [<span data-ttu-id="d4173-114">Практическое руководство. Создать рабочий процесс блок-схема</span><span class="sxs-lookup"><span data-stu-id="d4173-114">How to: Create a Flowchart Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-flowchart-workflow.md)  
 <span data-ttu-id="d4173-115">Описывает, как создать рабочий процесс блок-схемы с помощью действия <xref:System.Activities.Statements.Flowchart>.</span><span class="sxs-lookup"><span data-stu-id="d4173-115">Describes how to create a flowchart workflow using the <xref:System.Activities.Statements.Flowchart> activity.</span></span>  
  
 [<span data-ttu-id="d4173-116">Практическое руководство. Создание рабочего процесса конечного автомата</span><span class="sxs-lookup"><span data-stu-id="d4173-116">How to: Create a State Machine Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-state-machine-workflow.md)  
 <span data-ttu-id="d4173-117">Описывает способы создания рабочего процесса конечного автомата с помощью действия <xref:System.Activities.Statements.StateMachine>.</span><span class="sxs-lookup"><span data-stu-id="d4173-117">Describes how to create a state machine workflow using the <xref:System.Activities.Statements.StateMachine> activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4173-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d4173-118">See also</span></span>
- [<span data-ttu-id="d4173-119">Программирование в Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="d4173-119">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)
