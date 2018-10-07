---
title: Рекомендации по настройке конструктора рабочих процессов
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: ed4ccb45e4470eb03cec856e865d4b50220816e3
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2018
ms.locfileid: "48836463"
---
# <a name="customizing-the-workflow-design-experience"></a><span data-ttu-id="e9d08-102">Рекомендации по настройке конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="e9d08-102">Customizing the Workflow Design Experience</span></span>

<span data-ttu-id="e9d08-103">Сценарии для разработки пользовательских действий и повторного размещения [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] были значительно упрощены в [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9d08-103">The scenarios for designing custom activities and for rehosting the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] have been greatly simplified in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span></span> <span data-ttu-id="e9d08-104">Разработка и развертывание упрощены и являются более гибкими по сравнению с предыдущими версиями.</span><span class="sxs-lookup"><span data-stu-id="e9d08-104">Development and deployment are now both easier and more flexible.</span></span> <span data-ttu-id="e9d08-105">Основное изменение инфраструктуры состоит является то, что новый модель программирования конструктора действий построена на Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="e9d08-105">The key infrastructural change is that the new activity designer programming model is built upon Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="e9d08-106">Это позволяет декларативно определять конструкторы действий и упрощает повторное размещение [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] в других приложениях.</span><span class="sxs-lookup"><span data-stu-id="e9d08-106">This gives you the ability to define activity designers declaratively and to rehost the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in other applications with comparative easy.</span></span> <span data-ttu-id="e9d08-107">При повторном размещении может быть создан редактор пользовательских выражений, поддерживающий IntelliSense, или упрощенный домен выражений.</span><span class="sxs-lookup"><span data-stu-id="e9d08-107">When rehosting, a custom expression editor can be developed to support IntelliSense or a simplified expression domain.</span></span> <span data-ttu-id="e9d08-108">Интеграция с Windows Communication Foundation (WCF) также стала более плавной с использованием служб рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="e9d08-108">The integration with Windows Communication Foundation (WCF) has become more seamless with use of workflow services.</span></span> <span data-ttu-id="e9d08-109">Конструкторы пользовательских действий и дерево элементов модели могут быть использованы для улучшения действий во время разработки во вновь размещенных конструкторах рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="e9d08-109">Custom activity designers and the Model Item Tree can be used to enhance design time experiences in rehosted workflow designers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e9d08-110">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="e9d08-110">In This Section</span></span>

 [<span data-ttu-id="e9d08-111">Настраиваемые конструкторы и шаблоны действий</span><span class="sxs-lookup"><span data-stu-id="e9d08-111">Using Custom Activity Designers and Templates</span></span>](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md)

 <span data-ttu-id="e9d08-112">Описывается порядок создания новых конструкторов и шаблонов пользовательских действий.</span><span class="sxs-lookup"><span data-stu-id="e9d08-112">Describes how to create new custom activity designers and templates.</span></span>

 [<span data-ttu-id="e9d08-113">Отдельное размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="e9d08-113">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)

 <span data-ttu-id="e9d08-114">Описывается способ повторного размещения [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] вне Visual Studio и способ отображения ошибок проверки.</span><span class="sxs-lookup"><span data-stu-id="e9d08-114">Describes how to re-host the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] outside of Visual Studio and how to display validation errors.</span></span>

 [<span data-ttu-id="e9d08-115">Настраиваемый редактор выражений</span><span class="sxs-lookup"><span data-stu-id="e9d08-115">Using a Custom Expression Editor</span></span>](../../../docs/framework/windows-workflow-foundation/using-a-custom-expression-editor.md)

 <span data-ttu-id="e9d08-116">В этой статье описывается реализация редактора пользовательских выражений для использования с конструкторами рабочих процессов, повторно размещенными вне Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="e9d08-116">Describes how to implement a custom expression editor to use with workflow designers rehosted outside of Visual Studio 2010.</span></span>

## <a name="reference"></a><span data-ttu-id="e9d08-117">Ссылка</span><span class="sxs-lookup"><span data-stu-id="e9d08-117">Reference</span></span>

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a><span data-ttu-id="e9d08-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e9d08-118">See Also</span></span>

- [<span data-ttu-id="e9d08-119">Расширение Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="e9d08-119">Extending Windows Workflow Foundation</span></span>](../../../docs/framework/windows-workflow-foundation/extend.md)
- [<span data-ttu-id="e9d08-120">Конструктор</span><span class="sxs-lookup"><span data-stu-id="e9d08-120">Designer</span></span>](../../../docs/framework/windows-workflow-foundation/samples/designer.md)
- [<span data-ttu-id="e9d08-121">Пользовательские конструкторы действий</span><span class="sxs-lookup"><span data-stu-id="e9d08-121">Custom Activity Designers</span></span>](../../../docs/framework/windows-workflow-foundation/samples/custom-activity-designers.md)
- [<span data-ttu-id="e9d08-122">Повторное размещение конструктора</span><span class="sxs-lookup"><span data-stu-id="e9d08-122">Designer ReHosting</span></span>](../../../docs/framework/windows-workflow-foundation/samples/designer-rehosting.md)