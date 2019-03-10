---
title: Разработка и реализация настраиваемых действий
ms.date: 03/30/2017
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
ms.openlocfilehash: 61a5de5a15835c728c18c0136952cf7ffdbaf000
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57706407"
---
# <a name="designing-and-implementing-custom-activities"></a><span data-ttu-id="1b191-102">Разработка и реализация настраиваемых действий</span><span class="sxs-lookup"><span data-stu-id="1b191-102">Designing and Implementing Custom Activities</span></span>
<span data-ttu-id="1b191-103">Настраиваемые действия в [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] создаются либо посредством сборки системных действий в составные действия, либо путем создания новых типов, производных от <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> или <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="1b191-103">Custom activities in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] are created by either assembling system-provided activities into composite activities or by creating new types that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, or <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="1b191-104">В этом разделе описываются способы создания пользовательских действий обоими способами.</span><span class="sxs-lookup"><span data-stu-id="1b191-104">This section describes how to create custom activities with either method.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1b191-105">Настраиваемые действия по умолчанию отображаются в конструкторе рабочих процессов в виде простого прямоугольника с именем действия.</span><span class="sxs-lookup"><span data-stu-id="1b191-105">Custom activities by default display within the workflow designer as a simple rectangle with the activity’s name.</span></span> <span data-ttu-id="1b191-106">Для создания настраиваемого визуального представления действия в конструкторе рабочих процессов также необходимо создать пользовательский конструктор.</span><span class="sxs-lookup"><span data-stu-id="1b191-106">To provide a custom visual representation of your activity in the workflow designer you must also create a custom designer.</span></span> <span data-ttu-id="1b191-107">Дополнительные сведения см. в разделе [шаблонов и с помощью конструкторов пользовательских действий](using-custom-activity-designers-and-templates.md).</span><span class="sxs-lookup"><span data-stu-id="1b191-107">For more information, see [Using Custom Activity Designers and Templates](using-custom-activity-designers-and-templates.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1b191-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="1b191-108">In This Section</span></span>  
 [<span data-ttu-id="1b191-109">Параметры разработки действий</span><span class="sxs-lookup"><span data-stu-id="1b191-109">Activity Authoring Options</span></span>](activity-authoring-options-in-wf.md)  
 <span data-ttu-id="1b191-110">Описывает стили разработки, доступные в [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b191-110">Discusses the authoring styles available in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="1b191-111">Использование настраиваемого действия</span><span class="sxs-lookup"><span data-stu-id="1b191-111">Using a custom activity</span></span>](using-a-custom-activity.md)  
 <span data-ttu-id="1b191-112">Описывает, как добавить пользовательское действие в проект рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1b191-112">Describes how to add a custom activity to a workflow project.</span></span>  
  
  [<span data-ttu-id="1b191-113">Создание асинхронных действий</span><span class="sxs-lookup"><span data-stu-id="1b191-113">Creating Asynchronous Activities</span></span>](creating-asynchronous-activities-in-wf.md)  
 <span data-ttu-id="1b191-114">Описывает создание асинхронных действий.</span><span class="sxs-lookup"><span data-stu-id="1b191-114">Describes how to create asynchronous activities.</span></span>  
  
 [<span data-ttu-id="1b191-115">Настройка проверки действий</span><span class="sxs-lookup"><span data-stu-id="1b191-115">Configuring Activity Validation</span></span>](configuring-activity-validation.md)  
 <span data-ttu-id="1b191-116">Описывает, как проверка действия может быть использована для выявления ошибок в конфигурации действия до его выполнения.</span><span class="sxs-lookup"><span data-stu-id="1b191-116">Describes how activity validation can be used to identify and report errors in an activity’s configuration prior to its execution.</span></span>  
  
 [<span data-ttu-id="1b191-117">Создание действия в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="1b191-117">Creating an Activity at Runtime</span></span>](creating-an-activity-at-runtime-with-dynamicactivity.md)  
 <span data-ttu-id="1b191-118">Описывает, как создавать действия во время выполнения с помощью <xref:System.Activities.DynamicActivity>.</span><span class="sxs-lookup"><span data-stu-id="1b191-118">Discusses how to create activities at runtime using <xref:System.Activities.DynamicActivity>.</span></span>  
  
 [<span data-ttu-id="1b191-119">Свойства выполнения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="1b191-119">Workflow Execution Properties</span></span>](workflow-execution-properties.md)  
 <span data-ttu-id="1b191-120">Описывает, как использовать свойства выполнения рабочего процесса для добавления определенных свойств контекста к среде действия.</span><span class="sxs-lookup"><span data-stu-id="1b191-120">Describes how to use workflow execution properties to add context specific properties to an activity’s environment</span></span>  
  
 [<span data-ttu-id="1b191-121">Использование делегатов действий</span><span class="sxs-lookup"><span data-stu-id="1b191-121">Using Activity Delegates</span></span>](using-activity-delegates.md)  
 <span data-ttu-id="1b191-122">Описывает создание и использование действий, содержащих делегаты действий.</span><span class="sxs-lookup"><span data-stu-id="1b191-122">Discusses how to author and use activities that contain activity delegates.</span></span>
  
 [<span data-ttu-id="1b191-123">Использование расширений действий</span><span class="sxs-lookup"><span data-stu-id="1b191-123">Using Activity Extensions</span></span>](using-activity-extensions.md)  
 <span data-ttu-id="1b191-124">Описывает, как создавать и использовать расширения действий.</span><span class="sxs-lookup"><span data-stu-id="1b191-124">Describes how to author and use activity extensions.</span></span>  
  
 [<span data-ttu-id="1b191-125">Использование каналов OData из рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="1b191-125">Consuming OData Feeds from a Workflow</span></span>](consuming-odata-feeds-from-a-workflow.md)  
 <span data-ttu-id="1b191-126">Описывает различные методы для вызова службы данных WCF из рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1b191-126">Describes several methods for calling a WCF Data Service from a workflow.</span></span>  
  
 [<span data-ttu-id="1b191-127">Определение области и видимости действия</span><span class="sxs-lookup"><span data-stu-id="1b191-127">Activity Definition Scoping and Visibility</span></span>](activity-definition-scoping-and-visibility.md)  
 <span data-ttu-id="1b191-128">Описывает параметры и правила для определения области данных и видимости элементов для действий.</span><span class="sxs-lookup"><span data-stu-id="1b191-128">Describes the options and rules for defining data scoping and member visibility for activities.</span></span>
