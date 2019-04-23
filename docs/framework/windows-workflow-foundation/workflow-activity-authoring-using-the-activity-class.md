---
title: Разработка действий рабочих процессов с помощью класса Activity
ms.date: 03/30/2017
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
ms.openlocfilehash: 1bec10b6ae9fb43319cfb6acbf59133e1acca09c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770777"
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a><span data-ttu-id="813ec-102">Разработка действий рабочих процессов с помощью класса Activity</span><span class="sxs-lookup"><span data-stu-id="813ec-102">Workflow Activity Authoring Using the Activity Class</span></span>
<span data-ttu-id="813ec-103">Самый простой способ создать действие с помощью Windows Workflow Foundation (WF) в [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] заключается в создании класса, который наследует от <xref:System.Activities.Activity> создающего функциональность путем сборки пользовательских действий или действий из [встроенные Библиотека действий](net-framework-4-5-built-in-activity-library.md).</span><span class="sxs-lookup"><span data-stu-id="813ec-103">The most basic way to create an activity using Windows Workflow Foundation (WF) in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] is to create a class that inherits from <xref:System.Activities.Activity> that creates functionality by assembling custom activities or activities from the [Built-In Activity Library](net-framework-4-5-built-in-activity-library.md).</span></span> <span data-ttu-id="813ec-104">В этом разделе показано, как создать действие для вывода двух сообщений на консоль.</span><span class="sxs-lookup"><span data-stu-id="813ec-104">This topic demonstrates how to create an activity that writes two messages to the console.</span></span>

### <a name="to-create-a-custom-activity-using-the-activity-designer"></a><span data-ttu-id="813ec-105">Для создания пользовательского действия с помощью конструктора действий сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="813ec-105">To create a custom Activity using the activity designer</span></span>

1. <span data-ttu-id="813ec-106">Откройте Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="813ec-106">Open Visual Studio 2012.</span></span>

2. <span data-ttu-id="813ec-107">Выберите в меню «Файл» пункт «Создать», затем пункт «Создать проект».</span><span class="sxs-lookup"><span data-stu-id="813ec-107">Select File, New, Project.</span></span> <span data-ttu-id="813ec-108">Выберите **Workflow 4.0** под **Visual C#** в **типы проектов** затем выберите **v2010** узла.</span><span class="sxs-lookup"><span data-stu-id="813ec-108">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="813ec-109">Выберите **библиотеки действий** в **шаблоны** окна.</span><span class="sxs-lookup"><span data-stu-id="813ec-109">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="813ec-110">Задайте имя для нового проекта HelloActivity.</span><span class="sxs-lookup"><span data-stu-id="813ec-110">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="813ec-111">Откройте окно создания нового действия.</span><span class="sxs-lookup"><span data-stu-id="813ec-111">Open the new activity.</span></span>  <span data-ttu-id="813ec-112">Перетащите действие <xref:System.Activities.Statements.Sequence> из области элементов в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="813ec-112">Drag a <xref:System.Activities.Statements.Sequence> activity from the toolbox onto the designer surface.</span></span>

4. <span data-ttu-id="813ec-113">Перетащите действие <xref:System.Activities.Statements.WriteLine> в действие <xref:System.Activities.Statements.Sequence> activity.</span><span class="sxs-lookup"><span data-stu-id="813ec-113">Drag a <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="813ec-114">Введите `"Hello World"` (с кавычками) в **текст** поля.</span><span class="sxs-lookup"><span data-stu-id="813ec-114">Enter `"Hello World"` (with quotes) into the **Text** field.</span></span>

5. <span data-ttu-id="813ec-115">Перетащите второе действие <xref:System.Activities.Statements.WriteLine> в действие <xref:System.Activities.Statements.Sequence> под первым.</span><span class="sxs-lookup"><span data-stu-id="813ec-115">Drag a second <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity, below the first one.</span></span> <span data-ttu-id="813ec-116">Введите `"Goodbye"` (с кавычками) в **текст** поля.</span><span class="sxs-lookup"><span data-stu-id="813ec-116">Enter `"Goodbye"` (with quotes) into the **Text** field.</span></span>
