---
title: Рекомендации по настройке конструктора рабочих процессов
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0ee64ae3db9dbf98f2a62397075406c118a867bb
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="customizing-the-workflow-design-experience"></a><span data-ttu-id="ca2e6-102">Рекомендации по настройке конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="ca2e6-102">Customizing the Workflow Design Experience</span></span>
<span data-ttu-id="ca2e6-103">Сценарии для разработки пользовательских действий и повторного размещения [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] были значительно упрощены в [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca2e6-103">The scenarios for designing custom activities and for rehosting the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] have been greatly simplified in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span></span> <span data-ttu-id="ca2e6-104">Разработка и развертывание упрощены и являются более гибкими по сравнению с предыдущими версиями.</span><span class="sxs-lookup"><span data-stu-id="ca2e6-104">Development and deployment are now both easier and more flexible.</span></span> <span data-ttu-id="ca2e6-105">Основное изменение инфраструктуры состоит в том, что новое действие модели программирования конструктора построена после Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="ca2e6-105">The key infrastructural change is that the new activity designer programming model is built upon Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="ca2e6-106">Это позволяет декларативно определять конструкторы действий и упрощает повторное размещение [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] в других приложениях.</span><span class="sxs-lookup"><span data-stu-id="ca2e6-106">This gives you the ability to define activity designers declaratively and to rehost the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in other applications with comparative easy.</span></span> <span data-ttu-id="ca2e6-107">При повторном размещении может быть создан редактор пользовательских выражений, поддерживающий IntelliSense, или упрощенный домен выражений.</span><span class="sxs-lookup"><span data-stu-id="ca2e6-107">When rehosting, a custom expression editor can be developed to support IntelliSense or a simplified expression domain.</span></span> <span data-ttu-id="ca2e6-108">Интеграция с [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] стала более плавной с использованием служб рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="ca2e6-108">The integration with [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] has become more seamless with use of workflow services.</span></span> <span data-ttu-id="ca2e6-109">Конструкторы пользовательских действий и дерево элементов модели могут быть использованы для улучшения действий во время разработки во вновь размещенных конструкторах рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="ca2e6-109">Custom activity designers and the Model Item Tree can be used to enhance design time experiences in rehosted workflow designers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ca2e6-110">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="ca2e6-110">In This Section</span></span>  
 [<span data-ttu-id="ca2e6-111">Настраиваемые конструкторы и шаблоны действий</span><span class="sxs-lookup"><span data-stu-id="ca2e6-111">Using Custom Activity Designers and Templates</span></span>](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md)  
 <span data-ttu-id="ca2e6-112">Описывается порядок создания новых конструкторов и шаблонов пользовательских действий.</span><span class="sxs-lookup"><span data-stu-id="ca2e6-112">Describes how to create new custom activity designers and templates.</span></span>  
  
 [<span data-ttu-id="ca2e6-113">Отдельное размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="ca2e6-113">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 <span data-ttu-id="ca2e6-114">Описывается способ повторного размещения [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] вне [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] и отображения ошибок проверки.</span><span class="sxs-lookup"><span data-stu-id="ca2e6-114">Describes how to re-host the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] outside of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] and how to display validation errors.</span></span>  
  
 [<span data-ttu-id="ca2e6-115">Настраиваемый редактор выражений</span><span class="sxs-lookup"><span data-stu-id="ca2e6-115">Using a Custom Expression Editor</span></span>](../../../docs/framework/windows-workflow-foundation/using-a-custom-expression-editor.md)  
 <span data-ttu-id="ca2e6-116">Описан способ реализации редактора пользовательских выражений для использования с конструкторами рабочих процессов, повторно размещенными вне [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca2e6-116">Describes how to implement a custom expression editor to use with workflow designers rehosted outside of [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ca2e6-117">Ссылка</span><span class="sxs-lookup"><span data-stu-id="ca2e6-117">Reference</span></span>  
 <xref:System.Activities.Presentation.ActivityDesigner>  
  
## <a name="see-also"></a><span data-ttu-id="ca2e6-118">См. также</span><span class="sxs-lookup"><span data-stu-id="ca2e6-118">See Also</span></span>  
 [<span data-ttu-id="ca2e6-119">Расширение Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="ca2e6-119">Extending Windows Workflow Foundation</span></span>](../../../docs/framework/windows-workflow-foundation/extend.md)  
 [<span data-ttu-id="ca2e6-120">Конструктор</span><span class="sxs-lookup"><span data-stu-id="ca2e6-120">Designer</span></span>](../../../docs/framework/windows-workflow-foundation/samples/designer.md)  
 [<span data-ttu-id="ca2e6-121">Пользовательские конструкторы действий</span><span class="sxs-lookup"><span data-stu-id="ca2e6-121">Custom Activity Designers</span></span>](../../../docs/framework/windows-workflow-foundation/samples/custom-activity-designers.md)  
 [<span data-ttu-id="ca2e6-122">Повторное размещение конструктора</span><span class="sxs-lookup"><span data-stu-id="ca2e6-122">Designer ReHosting</span></span>](../../../docs/framework/windows-workflow-foundation/samples/designer-rehosting.md)
