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
ms.openlocfilehash: 37296298bda514d507b8fe65af516de74289d6a0
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="customizing-the-workflow-design-experience"></a><span data-ttu-id="23edd-102">Рекомендации по настройке конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="23edd-102">Customizing the Workflow Design Experience</span></span>
<span data-ttu-id="23edd-103">Сценарии для разработки пользовательских действий и повторного размещения [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] были значительно упрощены в [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23edd-103">The scenarios for designing custom activities and for rehosting the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] have been greatly simplified in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span></span> <span data-ttu-id="23edd-104">Разработка и развертывание упрощены и являются более гибкими по сравнению с предыдущими версиями.</span><span class="sxs-lookup"><span data-stu-id="23edd-104">Development and deployment are now both easier and more flexible.</span></span> <span data-ttu-id="23edd-105">Основное изменение инфраструктуры состоит в том, что новое действие модели программирования конструктора построена после Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="23edd-105">The key infrastructural change is that the new activity designer programming model is built upon Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="23edd-106">Это позволяет декларативно определять конструкторы действий и упрощает повторное размещение [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] в других приложениях.</span><span class="sxs-lookup"><span data-stu-id="23edd-106">This gives you the ability to define activity designers declaratively and to rehost the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in other applications with comparative easy.</span></span> <span data-ttu-id="23edd-107">При повторном размещении может быть создан редактор пользовательских выражений, поддерживающий IntelliSense, или упрощенный домен выражений.</span><span class="sxs-lookup"><span data-stu-id="23edd-107">When rehosting, a custom expression editor can be developed to support IntelliSense or a simplified expression domain.</span></span> <span data-ttu-id="23edd-108">Интеграция с [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] стала более плавной с использованием служб рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="23edd-108">The integration with [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] has become more seamless with use of workflow services.</span></span> <span data-ttu-id="23edd-109">Конструкторы пользовательских действий и дерево элементов модели могут быть использованы для улучшения действий во время разработки во вновь размещенных конструкторах рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="23edd-109">Custom activity designers and the Model Item Tree can be used to enhance design time experiences in rehosted workflow designers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="23edd-110">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="23edd-110">In This Section</span></span>  
 [<span data-ttu-id="23edd-111">Настраиваемые конструкторы и шаблоны действий</span><span class="sxs-lookup"><span data-stu-id="23edd-111">Using Custom Activity Designers and Templates</span></span>](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md)  
 <span data-ttu-id="23edd-112">Описывается порядок создания новых конструкторов и шаблонов пользовательских действий.</span><span class="sxs-lookup"><span data-stu-id="23edd-112">Describes how to create new custom activity designers and templates.</span></span>  
  
 [<span data-ttu-id="23edd-113">Отдельное размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="23edd-113">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 <span data-ttu-id="23edd-114">Описывает способ повторного размещения [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] вне Visual Studio и способ отображения ошибок проверки.</span><span class="sxs-lookup"><span data-stu-id="23edd-114">Describes how to re-host the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] outside of Visual Studio and how to display validation errors.</span></span>  
  
 [<span data-ttu-id="23edd-115">Настраиваемый редактор выражений</span><span class="sxs-lookup"><span data-stu-id="23edd-115">Using a Custom Expression Editor</span></span>](../../../docs/framework/windows-workflow-foundation/using-a-custom-expression-editor.md)  
 <span data-ttu-id="23edd-116">Описан способ реализации редактора пользовательских выражений для использования с конструкторами рабочих процессов, повторно размещенными вне [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23edd-116">Describes how to implement a custom expression editor to use with workflow designers rehosted outside of [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
## <a name="reference"></a><span data-ttu-id="23edd-117">Ссылка</span><span class="sxs-lookup"><span data-stu-id="23edd-117">Reference</span></span>  
 <xref:System.Activities.Presentation.ActivityDesigner>  
  
## <a name="see-also"></a><span data-ttu-id="23edd-118">См. также</span><span class="sxs-lookup"><span data-stu-id="23edd-118">See Also</span></span>  
 [<span data-ttu-id="23edd-119">Расширение Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="23edd-119">Extending Windows Workflow Foundation</span></span>](../../../docs/framework/windows-workflow-foundation/extend.md)  
 [<span data-ttu-id="23edd-120">Конструктор</span><span class="sxs-lookup"><span data-stu-id="23edd-120">Designer</span></span>](../../../docs/framework/windows-workflow-foundation/samples/designer.md)  
 [<span data-ttu-id="23edd-121">Пользовательские конструкторы действий</span><span class="sxs-lookup"><span data-stu-id="23edd-121">Custom Activity Designers</span></span>](../../../docs/framework/windows-workflow-foundation/samples/custom-activity-designers.md)  
 [<span data-ttu-id="23edd-122">Повторное размещение конструктора</span><span class="sxs-lookup"><span data-stu-id="23edd-122">Designer ReHosting</span></span>](../../../docs/framework/windows-workflow-foundation/samples/designer-rehosting.md)
