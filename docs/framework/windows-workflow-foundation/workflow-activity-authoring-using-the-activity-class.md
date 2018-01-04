---
title: "Разработка действий рабочих процессов с помощью класса Activity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 52d29f9cbed65932b3f9e97f0e9275861953b5d0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a><span data-ttu-id="2aa84-102">Разработка действий рабочих процессов с помощью класса Activity</span><span class="sxs-lookup"><span data-stu-id="2aa84-102">Workflow Activity Authoring Using the Activity Class</span></span>
<span data-ttu-id="2aa84-103">Самый простой способ создания действия с помощью [!INCLUDE[wf](../../../includes/wf-md.md)] в [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] необходимо создать класс, наследующий от <xref:System.Activities.Activity> , создающего функциональность путем сборки пользовательских действий или действий для [библиотека встроенных действий ](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md).</span><span class="sxs-lookup"><span data-stu-id="2aa84-103">The most basic way to create an activity using [!INCLUDE[wf](../../../includes/wf-md.md)] in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] is to create a class that inherits from <xref:System.Activities.Activity> that creates functionality by assembling custom activities or activities from the [Built-In Activity Library](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md).</span></span> <span data-ttu-id="2aa84-104">В этом разделе показано, как создать действие для вывода двух сообщений на консоль.</span><span class="sxs-lookup"><span data-stu-id="2aa84-104">This topic demonstrates how to create an activity that writes two messages to the console.</span></span>  
  
### <a name="to-create-a-custom-activity-using-the-activity-designer"></a><span data-ttu-id="2aa84-105">Для создания пользовательского действия с помощью конструктора действий сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="2aa84-105">To create a custom Activity using the activity designer</span></span>  
  
1.  <span data-ttu-id="2aa84-106">Откройте [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2aa84-106">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="2aa84-107">Выберите в меню «Файл» пункт «Создать», затем пункт «Создать проект».</span><span class="sxs-lookup"><span data-stu-id="2aa84-107">Select File, New, Project.</span></span> <span data-ttu-id="2aa84-108">Выберите **Workflow 4.0** под **Visual C#** в **типы проектов** затем выберите **v2010** узла.</span><span class="sxs-lookup"><span data-stu-id="2aa84-108">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="2aa84-109">Выберите **библиотеки действий** в **шаблоны** окна.</span><span class="sxs-lookup"><span data-stu-id="2aa84-109">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="2aa84-110">Задайте имя для нового проекта HelloActivity.</span><span class="sxs-lookup"><span data-stu-id="2aa84-110">Name the new project HelloActivity.</span></span>  
  
3.  <span data-ttu-id="2aa84-111">Откройте окно создания нового действия.</span><span class="sxs-lookup"><span data-stu-id="2aa84-111">Open the new activity.</span></span>  <span data-ttu-id="2aa84-112">Перетащите действие <xref:System.Activities.Statements.Sequence> из области элементов в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="2aa84-112">Drag a <xref:System.Activities.Statements.Sequence> activity from the toolbox onto the designer surface.</span></span>  
  
4.  <span data-ttu-id="2aa84-113">Перетащите действие <xref:System.Activities.Statements.WriteLine> в действие <xref:System.Activities.Statements.Sequence> activity.</span><span class="sxs-lookup"><span data-stu-id="2aa84-113">Drag a <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="2aa84-114">Введите `"Hello World"` (с кавычками) в **текст** поля.</span><span class="sxs-lookup"><span data-stu-id="2aa84-114">Enter `"Hello World"` (with quotes) into the **Text** field.</span></span>  
  
5.  <span data-ttu-id="2aa84-115">Перетащите второе действие <xref:System.Activities.Statements.WriteLine> в действие <xref:System.Activities.Statements.Sequence> под первым.</span><span class="sxs-lookup"><span data-stu-id="2aa84-115">Drag a second <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity, below the first one.</span></span> <span data-ttu-id="2aa84-116">Введите `"Goodbye"` (с кавычками) в **текст** поля.</span><span class="sxs-lookup"><span data-stu-id="2aa84-116">Enter `"Goodbye"` (with quotes) into the **Text** field.</span></span>
