---
title: Рекомендации по настройке конструктора рабочих процессов
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 27be398d874747b65ae051224070d3f40f1fbbb0
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715138"
---
# <a name="customizing-the-workflow-design-experience"></a><span data-ttu-id="22112-102">Рекомендации по настройке конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="22112-102">Customizing the Workflow Design Experience</span></span>

<span data-ttu-id="22112-103">Сценарии разработки пользовательских действий и для повторного размещения конструктор рабочих процессов Windows были значительно упрощены в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="22112-103">The scenarios for designing custom activities and for rehosting the Windows Workflow Designer have been greatly simplified in .NET Framework 4.</span></span> <span data-ttu-id="22112-104">Разработка и развертывание упрощены и являются более гибкими по сравнению с предыдущими версиями.</span><span class="sxs-lookup"><span data-stu-id="22112-104">Development and deployment are now both easier and more flexible.</span></span> <span data-ttu-id="22112-105">Основное инфраструктуры изменение заключается в том, что новая модель программирования конструктора действий строится на основе Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="22112-105">The key infrastructural change is that the new activity designer programming model is built upon Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="22112-106">Это дает возможность декларативно определять конструкторы действий и повторно размещать конструктор рабочих процессов в других приложениях с помощью сравнительно простой.</span><span class="sxs-lookup"><span data-stu-id="22112-106">This gives you the ability to define activity designers declaratively and to rehost the Workflow Designer in other applications with comparative easy.</span></span> <span data-ttu-id="22112-107">При повторном размещении может быть создан редактор пользовательских выражений, поддерживающий IntelliSense, или упрощенный домен выражений.</span><span class="sxs-lookup"><span data-stu-id="22112-107">When rehosting, a custom expression editor can be developed to support IntelliSense or a simplified expression domain.</span></span> <span data-ttu-id="22112-108">Интеграция с Windows Communication Foundation (WCF) стала более простой в использовании служб рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="22112-108">The integration with Windows Communication Foundation (WCF) has become more seamless with use of workflow services.</span></span> <span data-ttu-id="22112-109">Конструкторы пользовательских действий и дерево элементов модели могут быть использованы для улучшения действий во время разработки во вновь размещенных конструкторах рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="22112-109">Custom activity designers and the Model Item Tree can be used to enhance design time experiences in rehosted workflow designers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="22112-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="22112-110">In This Section</span></span>

 [<span data-ttu-id="22112-111">Настраиваемые конструкторы и шаблоны действий</span><span class="sxs-lookup"><span data-stu-id="22112-111">Using Custom Activity Designers and Templates</span></span>](using-custom-activity-designers-and-templates.md)

 <span data-ttu-id="22112-112">Описывается порядок создания новых конструкторов и шаблонов пользовательских действий.</span><span class="sxs-lookup"><span data-stu-id="22112-112">Describes how to create new custom activity designers and templates.</span></span>

 [<span data-ttu-id="22112-113">Отдельное размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="22112-113">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)

 <span data-ttu-id="22112-114">В этой статье описывается, как повторно разместить конструктор рабочих процессов Windows за пределами Visual Studio и как отобразить ошибки проверки.</span><span class="sxs-lookup"><span data-stu-id="22112-114">Describes how to re-host the Windows Workflow Designer outside of Visual Studio and how to display validation errors.</span></span>

 [<span data-ttu-id="22112-115">Настраиваемый редактор выражений</span><span class="sxs-lookup"><span data-stu-id="22112-115">Using a Custom Expression Editor</span></span>](using-a-custom-expression-editor.md)

 <span data-ttu-id="22112-116">Описание реализации пользовательского редактора выражений для использования с конструкторами рабочих процессов, которые перемещаются вне Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="22112-116">Describes how to implement a custom expression editor to use with workflow designers rehosted outside of Visual Studio 2010.</span></span>

## <a name="reference"></a><span data-ttu-id="22112-117">Справочники</span><span class="sxs-lookup"><span data-stu-id="22112-117">Reference</span></span>

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a><span data-ttu-id="22112-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="22112-118">See also</span></span>

- [<span data-ttu-id="22112-119">Расширение Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="22112-119">Extending Windows Workflow Foundation</span></span>](extend.md)
- [<span data-ttu-id="22112-120">Конструктор</span><span class="sxs-lookup"><span data-stu-id="22112-120">Designer</span></span>](./samples/designer.md)
- [<span data-ttu-id="22112-121">Пользовательские конструкторы действий</span><span class="sxs-lookup"><span data-stu-id="22112-121">Custom Activity Designers</span></span>](./samples/custom-activity-designers.md)
- [<span data-ttu-id="22112-122">Повторное размещение конструктора</span><span class="sxs-lookup"><span data-stu-id="22112-122">Designer ReHosting</span></span>](./samples/designer-rehosting.md)
