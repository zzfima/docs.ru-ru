---
title: Практическое руководство. Запрет присоединения дочерней задачи к ее родительской задаче
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, preventing attachments
ms.assetid: c0fb85d4-9e80-4905-9f65-29acc54201c4
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 654bfec4e8ba163c9dc9adf470c45401c0babd8b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-prevent-a-child-task-from-attaching-to-its-parent"></a><span data-ttu-id="ab749-102">Практическое руководство. Запрет присоединения дочерней задачи к ее родительской задаче</span><span class="sxs-lookup"><span data-stu-id="ab749-102">How to: Prevent a Child Task from Attaching to its Parent</span></span>
<span data-ttu-id="ab749-103">В этом документе показано, как предотвратить прикрепление дочерней задачи к родительской.</span><span class="sxs-lookup"><span data-stu-id="ab749-103">This document demonstrates how to prevent a child task from attaching to the parent task.</span></span> <span data-ttu-id="ab749-104">Предотвращение прикрепления дочерней задачи к родительской полезно при вызове компонента, написанного сторонним разработчиком и также использующим задачи.</span><span class="sxs-lookup"><span data-stu-id="ab749-104">Preventing a child task from attaching to its parent is useful when you call a component that is written by a third party and that also uses tasks.</span></span> <span data-ttu-id="ab749-105">Например, компонент стороннего разработчика, использующий параметр <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> для создания объекта <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>, может вызвать проблемы в коде, если он продолжительный или создает необрабатываемое исключение.</span><span class="sxs-lookup"><span data-stu-id="ab749-105">For example, a third-party component that uses the <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> option to create a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> object can cause problems in your code if it is long-running or throws an unhandled exception.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab749-106">Пример</span><span class="sxs-lookup"><span data-stu-id="ab749-106">Example</span></span>  
 <span data-ttu-id="ab749-107">В следующем примере сравниваются последствия использования параметров по умолчанию с последствиями предотвращения прикрепления дочерней задачи к родительской.</span><span class="sxs-lookup"><span data-stu-id="ab749-107">The following example compares the effects of using the default options to the effects of preventing a child task from attaching to the parent.</span></span> <span data-ttu-id="ab749-108">В примере создается объект <xref:System.Threading.Tasks.Task>, вызывающий библиотеку стороннего разработчика, которая также использует объект <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="ab749-108">The example creates a <xref:System.Threading.Tasks.Task> object that calls into a third-party library that also uses a <xref:System.Threading.Tasks.Task> object.</span></span> <span data-ttu-id="ab749-109">Библиотека стороннего разработчика использует параметр <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> для создания объекта <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="ab749-109">The third-party library uses the <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> option to create the <xref:System.Threading.Tasks.Task> object.</span></span> <span data-ttu-id="ab749-110">Приложение использует параметр <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> для создания родительской задачи.</span><span class="sxs-lookup"><span data-stu-id="ab749-110">The application uses the <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> option to create the parent task.</span></span> <span data-ttu-id="ab749-111">Этот параметр выдает среде выполнения указание удалить спецификацию <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> в дочерних задачах.</span><span class="sxs-lookup"><span data-stu-id="ab749-111">This option instructs the runtime to remove the <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> specification in child tasks.</span></span>  
  
 [!code-csharp[TPL_DenyChildAttach#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_denychildattach/cs/denychildattach.cs#1)]
 [!code-vb[TPL_DenyChildAttach#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_denychildattach/vb/denychildattach.vb#1)]  
  
 <span data-ttu-id="ab749-112">Поскольку родительская задача не завершается, пока не завершатся все дочерние задачи, длительная дочерняя задача может привести к ухудшению производительности приложения в целом.</span><span class="sxs-lookup"><span data-stu-id="ab749-112">Because a parent task does not finish until all child tasks finish, a long-running child task can cause the overall application to perform poorly.</span></span> <span data-ttu-id="ab749-113">В этом примере, когда приложение использует параметры по умолчанию для создания родительской задачи, дочерняя задача должна выполниться до завершения родительской задачи.</span><span class="sxs-lookup"><span data-stu-id="ab749-113">In this example, when the application uses the default options to create the parent task, the child task must finish before the parent task finishes.</span></span> <span data-ttu-id="ab749-114">Если приложение использует параметр <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType>, дочерняя задача не будет прикреплена к родительской.</span><span class="sxs-lookup"><span data-stu-id="ab749-114">When the application uses the <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> option, the child is not attached to the parent.</span></span> <span data-ttu-id="ab749-115">Поэтому приложение может выполнять дополнительную работу после завершения родительской задачи и до ожидания завершения дочерней задачи.</span><span class="sxs-lookup"><span data-stu-id="ab749-115">Therefore, the application can perform additional work after the parent task finishes and before it must wait for the child task to finish.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ab749-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="ab749-116">Compiling the Code</span></span>  
 <span data-ttu-id="ab749-117">Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `DenyChildAttach.cs` (`DenyChildAttach.vb` для Visual Basic), затем выполните в окне командной строки Visual Studio следующую команду.</span><span class="sxs-lookup"><span data-stu-id="ab749-117">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DenyChildAttach.cs` (`DenyChildAttach.vb` for Visual Basic), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 <span data-ttu-id="ab749-118">Visual C#</span><span class="sxs-lookup"><span data-stu-id="ab749-118">Visual C#</span></span>  
  
 <span data-ttu-id="ab749-119">**csc.exe DenyChildAttach.cs**</span><span class="sxs-lookup"><span data-stu-id="ab749-119">**csc.exe DenyChildAttach.cs**</span></span>  
  
 <span data-ttu-id="ab749-120">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ab749-120">Visual Basic</span></span>  
  
 <span data-ttu-id="ab749-121">**vbc.exe DenyChildAttach.vb**</span><span class="sxs-lookup"><span data-stu-id="ab749-121">**vbc.exe DenyChildAttach.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ab749-122">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="ab749-122">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab749-123">См. также</span><span class="sxs-lookup"><span data-stu-id="ab749-123">See Also</span></span>  
 [<span data-ttu-id="ab749-124">Асинхронное программирование на основе задач</span><span class="sxs-lookup"><span data-stu-id="ab749-124">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
