---
title: Разработка и реализация настраиваемых действий
ms.date: 03/30/2017
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
ms.openlocfilehash: 2ed80b5cbb27c6647053ee9b8f4cd2bedb0c6cde
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513823"
---
# <a name="designing-and-implementing-custom-activities"></a><span data-ttu-id="775eb-102">Разработка и реализация настраиваемых действий</span><span class="sxs-lookup"><span data-stu-id="775eb-102">Designing and Implementing Custom Activities</span></span>
<span data-ttu-id="775eb-103">Настраиваемые действия в [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] создаются либо посредством сборки системных действий в составные действия, либо путем создания новых типов, производных от <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> или <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="775eb-103">Custom activities in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] are created by either assembling system-provided activities into composite activities or by creating new types that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, or <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="775eb-104">В этом разделе описываются способы создания пользовательских действий обоими способами.</span><span class="sxs-lookup"><span data-stu-id="775eb-104">This section describes how to create custom activities with either method.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="775eb-105">Настраиваемые действия по умолчанию отображаются в конструкторе рабочих процессов в виде простого прямоугольника с именем действия.</span><span class="sxs-lookup"><span data-stu-id="775eb-105">Custom activities by default display within the workflow designer as a simple rectangle with the activity’s name.</span></span> <span data-ttu-id="775eb-106">Для создания настраиваемого визуального представления действия в конструкторе рабочих процессов также необходимо создать пользовательский конструктор.</span><span class="sxs-lookup"><span data-stu-id="775eb-106">To provide a custom visual representation of your activity in the workflow designer you must also create a custom designer.</span></span> <span data-ttu-id="775eb-107">Дополнительные сведения см. в разделе [с помощью пользовательских конструкторов действий и шаблоны](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md).</span><span class="sxs-lookup"><span data-stu-id="775eb-107">For more information, see [Using Custom Activity Designers and Templates](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="775eb-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="775eb-108">In This Section</span></span>  
 [<span data-ttu-id="775eb-109">Параметры разработки действий</span><span class="sxs-lookup"><span data-stu-id="775eb-109">Activity Authoring Options</span></span>](../../../docs/framework/windows-workflow-foundation/activity-authoring-options-in-wf.md)  
 <span data-ttu-id="775eb-110">Описывает стили разработки, доступные в [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="775eb-110">Discusses the authoring styles available in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="775eb-111">Использование настраиваемого действия</span><span class="sxs-lookup"><span data-stu-id="775eb-111">Using a custom activity</span></span>](../../../docs/framework/windows-workflow-foundation/using-a-custom-activity.md)  
 <span data-ttu-id="775eb-112">Описывает, как добавить пользовательское действие в проект рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="775eb-112">Describes how to add a custom activity to a workflow project.</span></span>  
  
  [<span data-ttu-id="775eb-113">Создание асинхронных действий</span><span class="sxs-lookup"><span data-stu-id="775eb-113">Creating Asynchronous Activities</span></span>](../../../docs/framework/windows-workflow-foundation/creating-asynchronous-activities-in-wf.md)  
 <span data-ttu-id="775eb-114">Описывает создание асинхронных действий.</span><span class="sxs-lookup"><span data-stu-id="775eb-114">Describes how to create asynchronous activities.</span></span>  
  
 [<span data-ttu-id="775eb-115">Настройка проверки действий</span><span class="sxs-lookup"><span data-stu-id="775eb-115">Configuring Activity Validation</span></span>](../../../docs/framework/windows-workflow-foundation/configuring-activity-validation.md)  
 <span data-ttu-id="775eb-116">Описывает, как проверка действия может быть использована для выявления ошибок в конфигурации действия до его выполнения.</span><span class="sxs-lookup"><span data-stu-id="775eb-116">Describes how activity validation can be used to identify and report errors in an activity’s configuration prior to its execution.</span></span>  
  
 [<span data-ttu-id="775eb-117">Создание действия в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="775eb-117">Creating an Activity at Runtime</span></span>](../../../docs/framework/windows-workflow-foundation/creating-an-activity-at-runtime-with-dynamicactivity.md)  
 <span data-ttu-id="775eb-118">Описывает, как создавать действия во время выполнения с помощью <xref:System.Activities.DynamicActivity>.</span><span class="sxs-lookup"><span data-stu-id="775eb-118">Discusses how to create activities at runtime using <xref:System.Activities.DynamicActivity>.</span></span>  
  
 [<span data-ttu-id="775eb-119">Свойства выполнения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="775eb-119">Workflow Execution Properties</span></span>](../../../docs/framework/windows-workflow-foundation/workflow-execution-properties.md)  
 <span data-ttu-id="775eb-120">Описывает, как использовать свойства выполнения рабочего процесса для добавления определенных свойств контекста к среде действия.</span><span class="sxs-lookup"><span data-stu-id="775eb-120">Describes how to use workflow execution properties to add context specific properties to an activity’s environment</span></span>  
  
 [<span data-ttu-id="775eb-121">Использование делегатов действий</span><span class="sxs-lookup"><span data-stu-id="775eb-121">Using Activity Delegates</span></span>](../../../docs/framework/windows-workflow-foundation/using-activity-delegates.md)  
 <span data-ttu-id="775eb-122">Описывает создание и использование действий, содержащих делегаты действий.</span><span class="sxs-lookup"><span data-stu-id="775eb-122">Discusses how to author and use activities that contain activity delegates.</span></span>  
  
 [<span data-ttu-id="775eb-123">Локализация действий</span><span class="sxs-lookup"><span data-stu-id="775eb-123">Activity Localization</span></span>](../../../docs/framework/windows-workflow-foundation/activity-localization.md)  
 <span data-ttu-id="775eb-124">Описывает использование в действиях локализации строковых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="775eb-124">Describes how to use localization of string resources in activities.</span></span>  
  
 [<span data-ttu-id="775eb-125">Использование расширений действий</span><span class="sxs-lookup"><span data-stu-id="775eb-125">Using Activity Extensions</span></span>](../../../docs/framework/windows-workflow-foundation/using-activity-extensions.md)  
 <span data-ttu-id="775eb-126">Описывает, как создавать и использовать расширения действий.</span><span class="sxs-lookup"><span data-stu-id="775eb-126">Describes how to author and use activity extensions.</span></span>  
  
 [<span data-ttu-id="775eb-127">Использование каналов OData из рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="775eb-127">Consuming OData Feeds from a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/consuming-odata-feeds-from-a-workflow.md)  
 <span data-ttu-id="775eb-128">Описывает различные методы для вызова службы данных WCF из рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="775eb-128">Describes several methods for calling a WCF Data Service from a workflow.</span></span>  
  
 [<span data-ttu-id="775eb-129">Определение области и видимости действия</span><span class="sxs-lookup"><span data-stu-id="775eb-129">Activity Definition Scoping and Visibility</span></span>](../../../docs/framework/windows-workflow-foundation/activity-definition-scoping-and-visibility.md)  
 <span data-ttu-id="775eb-130">Описывает параметры и правила для определения области данных и видимости элементов для действий.</span><span class="sxs-lookup"><span data-stu-id="775eb-130">Describes the options and rules for defining data scoping and member visibility for activities.</span></span>
