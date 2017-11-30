---
title: 'How to: Create a Workflow'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87234108-8e21-4cb3-9340-4a1a13f3f98c
caps.latest.revision: "34"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7f16df123837b2233efd156bf35975e3adbe7279
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-workflow"></a><span data-ttu-id="cee15-102">How to: Create a Workflow</span><span class="sxs-lookup"><span data-stu-id="cee15-102">How to: Create a Workflow</span></span>
<span data-ttu-id="cee15-103">Рабочие процессы могут создаваться как из встроенных, так и из пользовательских действий.</span><span class="sxs-lookup"><span data-stu-id="cee15-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="cee15-104">Приведенные здесь статьи в этом шаге раздела по созданию рабочего процесса, который использует оба встроенных действий, такие как <xref:System.Activities.Statements.Flowchart> действия и пользовательских действий из предыдущего [как: создается действие](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="cee15-104">This topics in this section step through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="cee15-105">Рабочий процесс моделирует игру по угадыванию числа.</span><span class="sxs-lookup"><span data-stu-id="cee15-105">The workflow models a number guessing game.</span></span> <span data-ttu-id="cee15-106">Для завершения учебника требуется только один из подразделов в этом разделе. Необходимо выбрать стиль, который вас интересует, и выполнить шаг.</span><span class="sxs-lookup"><span data-stu-id="cee15-106">Only one of the topics in this section is required to complete the tutorial; you should pick the style that interests you and follow that step.</span></span> <span data-ttu-id="cee15-107">Однако при необходимости можно завершить все подразделы.</span><span class="sxs-lookup"><span data-stu-id="cee15-107">However, you may complete all of the topics if desired.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cee15-108">Каждый раздел в учебнике «Приступая к работе» построен на основе предыдущих разделов.</span><span class="sxs-lookup"><span data-stu-id="cee15-108">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="cee15-109">Для изучения этого раздела, необходимо сначала выполнить [как: создается действие](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="cee15-109">To complete this topic, you must first complete [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cee15-110">Чтобы скачать завершенную версию учебника, см. раздел [Windows Workflow Foundation (WF45), учебник "Приступая к работе"](http://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="cee15-110">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cee15-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="cee15-111">In This Section</span></span>  
 [<span data-ttu-id="cee15-112">Практическое руководство. Создание последовательного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="cee15-112">How to: Create a Sequential Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-sequential-workflow.md)  
 <span data-ttu-id="cee15-113">Описывает, как создать последовательный рабочий процесс с помощью действия <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="cee15-113">Describes how to create a sequential workflow using the <xref:System.Activities.Statements.Sequence> activity.</span></span>  
  
 [<span data-ttu-id="cee15-114">Практическое руководство. Создание рабочего процесса c блок-схемой</span><span class="sxs-lookup"><span data-stu-id="cee15-114">How to: Create a Flowchart Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-flowchart-workflow.md)  
 <span data-ttu-id="cee15-115">Описывает, как создать рабочий процесс блок-схемы с помощью действия <xref:System.Activities.Statements.Flowchart>.</span><span class="sxs-lookup"><span data-stu-id="cee15-115">Describes how to create a flowchart workflow using the <xref:System.Activities.Statements.Flowchart> activity.</span></span>  
  
 [<span data-ttu-id="cee15-116">Практическое руководство. Создание рабочего процесса конечного автомата</span><span class="sxs-lookup"><span data-stu-id="cee15-116">How to: Create a State Machine Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-state-machine-workflow.md)  
 <span data-ttu-id="cee15-117">Описывает способы создания рабочего процесса конечного автомата с помощью действия <xref:System.Activities.Statements.StateMachine>.</span><span class="sxs-lookup"><span data-stu-id="cee15-117">Describes how to create a state machine workflow using the <xref:System.Activities.Statements.StateMachine> activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cee15-118">См. также</span><span class="sxs-lookup"><span data-stu-id="cee15-118">See Also</span></span>  
 [<span data-ttu-id="cee15-119">Программирование в Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="cee15-119">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)
