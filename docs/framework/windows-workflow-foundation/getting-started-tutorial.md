---
title: Приступая к работе Tutorial2
ms.date: 03/30/2017
helpviewer_keywords:
- WF [WF], getting started
- Windows Workflow Foundation [WF], getting started
ms.assetid: c2d3585f-6b1a-4d4f-9865-bd7cd31c5d42
ms.openlocfilehash: 540765c09dceef583798ceaf1abf9f191f444697
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217436"
---
# <a name="getting-started-tutorial"></a><span data-ttu-id="fce00-102">Учебник по началу работы</span><span class="sxs-lookup"><span data-stu-id="fce00-102">Getting Started Tutorial</span></span>
<span data-ttu-id="fce00-103">Этот раздел содержит набор руководства, в которых рассматриваются программирования приложений Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="fce00-103">This section contains a set of walkthrough topics that introduce you to programming Windows Workflow Foundation (WF) applications.</span></span> <span data-ttu-id="fce00-104">Следуя инструкциям, приведенным в данных разделах, вы сможете построить приложение, реализующее игру по угадыванию числа.</span><span class="sxs-lookup"><span data-stu-id="fce00-104">By following the procedures in these topics, you will build an application that is a number guessing game.</span></span> <span data-ttu-id="fce00-105">В первом разделе учебника описаны шаги по созданию пользовательских действий, необходимых для рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="fce00-105">The first topic in the tutorial leads you through the steps to create the custom activities required for the workflow.</span></span> <span data-ttu-id="fce00-106">Во втором разделе выполняется сборка этих действий вместе со встроенными действиями рабочих процессов в рабочий процесс блок-схемы.</span><span class="sxs-lookup"><span data-stu-id="fce00-106">In the second topic, these activities are assembled along with built-in workflow activities into a flowchart workflow.</span></span> <span data-ttu-id="fce00-107">В третьем разделе выполняется настройка ведущего приложения для выполнения рабочего процесса, а в последнем разделе описывается сохраняемость.</span><span class="sxs-lookup"><span data-stu-id="fce00-107">In the third topic, the host application is configured to run the workflow, and in the final topic persistence is introduced.</span></span> <span data-ttu-id="fce00-108">Каждый шаг этого процесса зависит от предыдущих, поэтому рекомендуется выполнять их по порядку.</span><span class="sxs-lookup"><span data-stu-id="fce00-108">Each step in this process depends on the previous steps, so we recommend that you complete them in order.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fce00-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="fce00-109">In This Section</span></span>  
 [<span data-ttu-id="fce00-110">Практическое руководство. Создание действия</span><span class="sxs-lookup"><span data-stu-id="fce00-110">How to: Create an Activity</span></span>](how-to-create-an-activity.md)  
 <span data-ttu-id="fce00-111">Описывает способ создания настраиваемого действия, которое является производным от <xref:System.Activities.NativeActivity%601>, и способы формирования составного действия из этого и встроенного действия с помощью конструктора действий.</span><span class="sxs-lookup"><span data-stu-id="fce00-111">Describes how to create a custom activity that derives from <xref:System.Activities.NativeActivity%601>, and how to compose this activity along with a built-in activity into a composite activity using the activity designer.</span></span>  
  
 [<span data-ttu-id="fce00-112">Практическое руководство. Создание рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="fce00-112">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)  
 <span data-ttu-id="fce00-113">Описывает создание рабочих процессов блок-схем, последовательностей и конечных автоматов с помощью встроенных действий и пользовательских действий из предыдущего учебника.</span><span class="sxs-lookup"><span data-stu-id="fce00-113">Describes how to create flowchart, sequential, and state machine workflows by using built-in activities and the custom activities from the preceding tutorial.</span></span>  
  
 [<span data-ttu-id="fce00-114">Практическое руководство. Запуск рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="fce00-114">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)  
 <span data-ttu-id="fce00-115">Описывает вызов рабочего процесса из среды узла и из рабочего процесса, а также возобновление закладок.</span><span class="sxs-lookup"><span data-stu-id="fce00-115">Describes how to invoke a workflow from a host environment, pass data into and out of a workflow, and how to resume bookmarks.</span></span>  
  
 [<span data-ttu-id="fce00-116">Практическое руководство. Создание и запуск длительно выполнении рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="fce00-116">How to: Create and Run a Long Running Workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md)  
 <span data-ttu-id="fce00-117">Описывает способы добавления сохраняемости к приложению рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fce00-117">Describes how to add persistence to a workflow application.</span></span>  
  
 [<span data-ttu-id="fce00-118">Практическое руководство. Создание пользовательского участника отслеживания</span><span class="sxs-lookup"><span data-stu-id="fce00-118">How to: Create a Custom Tracking Participant</span></span>](how-to-create-a-custom-tracking-participant.md)  
 <span data-ttu-id="fce00-119">Описывает процесс создания настраиваемого участника отслеживания и профиля отслеживания.</span><span class="sxs-lookup"><span data-stu-id="fce00-119">Describes how to create a custom tracking participant and tracking profile.</span></span>  
  
 [<span data-ttu-id="fce00-120">Практическое руководство. Размещение нескольких версий рабочего процесса Side-by-Side</span><span class="sxs-lookup"><span data-stu-id="fce00-120">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)  
 <span data-ttu-id="fce00-121">Описывает, как использовать `WorkflowIdentity` для параллельного размещения нескольких версий рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fce00-121">Describes how to use `WorkflowIdentity` to host multiple versions of a workflow side-by-side.</span></span>  
  
 [<span data-ttu-id="fce00-122">Практическое руководство. Обновить определение выполняющегося экземпляра рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="fce00-122">How to: Update the Definition of a Running Workflow Instance</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md)  
 <span data-ttu-id="fce00-123">Описывает, как использовать динамическое обновление для изменения выполняемых экземпляров рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="fce00-123">Describes how to use dynamic update to modify running workflow instances.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fce00-124">См. также</span><span class="sxs-lookup"><span data-stu-id="fce00-124">See also</span></span>

- [<span data-ttu-id="fce00-125">Программирование в Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="fce00-125">Windows Workflow Foundation Programming</span></span>](programming.md)
