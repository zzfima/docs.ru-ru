---
title: Улучшение производительности приложений WPF
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: 98c7022eab9153808d47d7da69c23349032165c3
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460846"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="8f61f-102">Улучшение производительности приложений WPF</span><span class="sxs-lookup"><span data-stu-id="8f61f-102">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="8f61f-103">Этот раздел предназначен для разработчиков приложений [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], которые ищут способы повышения производительности приложений.</span><span class="sxs-lookup"><span data-stu-id="8f61f-103">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="8f61f-104">Если вы являетесь разработчиком, который не знаком с платформой Microsoft .NET и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], необходимо сначала ознакомиться с обеими платформами.</span><span class="sxs-lookup"><span data-stu-id="8f61f-104">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="8f61f-105">В этом разделе предполагается работа с базами знаний и написана для программистов, которые уже знакомы, чтобы заставить их работать.</span><span class="sxs-lookup"><span data-stu-id="8f61f-105">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8f61f-106">Данные о производительности, приведенные в этом разделе, основаны на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложениях, работающих на ПК 2,8 ГГц с 512 ОЗУ и графической картой ATI Radeon 9700.</span><span class="sxs-lookup"><span data-stu-id="8f61f-106">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8f61f-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="8f61f-107">In This Section</span></span>  
 [<span data-ttu-id="8f61f-108">Планирование производительности приложения</span><span class="sxs-lookup"><span data-stu-id="8f61f-108">Planning for Application Performance</span></span>](planning-for-application-performance.md)  
  
 [<span data-ttu-id="8f61f-109">Использование преимуществ оборудования</span><span class="sxs-lookup"><span data-stu-id="8f61f-109">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="8f61f-110">Разметка и разработка</span><span class="sxs-lookup"><span data-stu-id="8f61f-110">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="8f61f-111">Двумерная графика и изображения</span><span class="sxs-lookup"><span data-stu-id="8f61f-111">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="8f61f-112">Поведение объекта</span><span class="sxs-lookup"><span data-stu-id="8f61f-112">Object Behavior</span></span>](optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="8f61f-113">Ресурсы приложений</span><span class="sxs-lookup"><span data-stu-id="8f61f-113">Application Resources</span></span>](optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="8f61f-114">Текст</span><span class="sxs-lookup"><span data-stu-id="8f61f-114">Text</span></span>](optimizing-performance-text.md)  
  
 [<span data-ttu-id="8f61f-115">Привязка данных</span><span class="sxs-lookup"><span data-stu-id="8f61f-115">Data Binding</span></span>](optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="8f61f-116">Элементы управления</span><span class="sxs-lookup"><span data-stu-id="8f61f-116">Controls</span></span>](optimizing-performance-controls.md)  
  
 [<span data-ttu-id="8f61f-117">Дополнительные рекомендации по повышению производительности</span><span class="sxs-lookup"><span data-stu-id="8f61f-117">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="8f61f-118">Время запуска приложения</span><span class="sxs-lookup"><span data-stu-id="8f61f-118">Application Startup Time</span></span>](application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="8f61f-119">См. также</span><span class="sxs-lookup"><span data-stu-id="8f61f-119">See also</span></span>

- <xref:System.Windows.Media.RenderOptions>
- <xref:System.Windows.Media.RenderCapability>
- [<span data-ttu-id="8f61f-120">Уровни графической отрисовки</span><span class="sxs-lookup"><span data-stu-id="8f61f-120">Graphics Rendering Tiers</span></span>](graphics-rendering-tiers.md)
- [<span data-ttu-id="8f61f-121">Общие сведения об отрисовке графики в WPF</span><span class="sxs-lookup"><span data-stu-id="8f61f-121">WPF Graphics Rendering Overview</span></span>](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="8f61f-122">Макет</span><span class="sxs-lookup"><span data-stu-id="8f61f-122">Layout</span></span>](layout.md)
- [<span data-ttu-id="8f61f-123">Деревья в WPF</span><span class="sxs-lookup"><span data-stu-id="8f61f-123">Trees in WPF</span></span>](trees-in-wpf.md)
- [<span data-ttu-id="8f61f-124">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="8f61f-124">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="8f61f-125">Использование объектов DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="8f61f-125">Using DrawingVisual Objects</span></span>](../graphics-multimedia/using-drawingvisual-objects.md)
- [<span data-ttu-id="8f61f-126">Общие сведения о свойствах зависимости</span><span class="sxs-lookup"><span data-stu-id="8f61f-126">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="8f61f-127">Общие сведения об объектах класса Freezable</span><span class="sxs-lookup"><span data-stu-id="8f61f-127">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="8f61f-128">Ресурсы XAML</span><span class="sxs-lookup"><span data-stu-id="8f61f-128">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="8f61f-129">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="8f61f-129">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="8f61f-130">Рисование форматированного текста</span><span class="sxs-lookup"><span data-stu-id="8f61f-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
- [<span data-ttu-id="8f61f-131">Оформление в WPF</span><span class="sxs-lookup"><span data-stu-id="8f61f-131">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="8f61f-132">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="8f61f-132">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="8f61f-133">Общие сведения о переходах</span><span class="sxs-lookup"><span data-stu-id="8f61f-133">Navigation Overview</span></span>](../app-development/navigation-overview.md)
- [<span data-ttu-id="8f61f-134">Советы и рекомендации по анимации</span><span class="sxs-lookup"><span data-stu-id="8f61f-134">Animation Tips and Tricks</span></span>](../graphics-multimedia/animation-tips-and-tricks.md)
- [<span data-ttu-id="8f61f-135">Пошаговое руководство. Кэширование данных приложения WPF</span><span class="sxs-lookup"><span data-stu-id="8f61f-135">Walkthrough: Caching Application Data in a WPF Application</span></span>](walkthrough-caching-application-data-in-a-wpf-application.md)
