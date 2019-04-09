---
title: Улучшение производительности приложений WPF
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: 53291a0e428b723cd7a6e7b1184639a7b3c3b972
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141561"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="d5dff-102">Улучшение производительности приложений WPF</span><span class="sxs-lookup"><span data-stu-id="d5dff-102">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="d5dff-103">Этот раздел предназначен в качестве справочника по [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] разработчикам приложений, которым нужны дополнительные способы повышения производительности своих приложений.</span><span class="sxs-lookup"><span data-stu-id="d5dff-103">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="d5dff-104">Если вы являетесь разработчиком, даже новичок в Microsoft .NET Framework и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], следует сначала ознакомиться с обеими платформами.</span><span class="sxs-lookup"><span data-stu-id="d5dff-104">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="d5dff-105">В этом разделе, предполагает оба и написан для программистов, которые уже знают достаточно, чтобы приступить к работе своих приложений.</span><span class="sxs-lookup"><span data-stu-id="d5dff-105">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5dff-106">Данные о производительности в этом разделе основаны на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложений, выполняющихся на 2,8 ГГц ПК с 512, ОЗУ и ATI Radeon 9700 видеокарте.</span><span class="sxs-lookup"><span data-stu-id="d5dff-106">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5dff-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="d5dff-107">In This Section</span></span>  
 [<span data-ttu-id="d5dff-108">Планирование производительности приложения</span><span class="sxs-lookup"><span data-stu-id="d5dff-108">Planning for Application Performance</span></span>](planning-for-application-performance.md)  
  
 [<span data-ttu-id="d5dff-109">Использование преимуществ оборудования</span><span class="sxs-lookup"><span data-stu-id="d5dff-109">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="d5dff-110">Разметка и разработка</span><span class="sxs-lookup"><span data-stu-id="d5dff-110">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="d5dff-111">Двумерная графика и изображения</span><span class="sxs-lookup"><span data-stu-id="d5dff-111">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="d5dff-112">Поведение объекта</span><span class="sxs-lookup"><span data-stu-id="d5dff-112">Object Behavior</span></span>](optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="d5dff-113">Ресурсы приложений</span><span class="sxs-lookup"><span data-stu-id="d5dff-113">Application Resources</span></span>](optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="d5dff-114">Текста</span><span class="sxs-lookup"><span data-stu-id="d5dff-114">Text</span></span>](optimizing-performance-text.md)  
  
 [<span data-ttu-id="d5dff-115">Привязка данных</span><span class="sxs-lookup"><span data-stu-id="d5dff-115">Data Binding</span></span>](optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="d5dff-116">Элементы управления</span><span class="sxs-lookup"><span data-stu-id="d5dff-116">Controls</span></span>](optimizing-performance-controls.md)  
  
 [<span data-ttu-id="d5dff-117">Дополнительные рекомендации по повышению производительности</span><span class="sxs-lookup"><span data-stu-id="d5dff-117">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="d5dff-118">Время запуска приложения</span><span class="sxs-lookup"><span data-stu-id="d5dff-118">Application Startup Time</span></span>](application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="d5dff-119">См. также</span><span class="sxs-lookup"><span data-stu-id="d5dff-119">See also</span></span>

- <xref:System.Windows.Media.RenderOptions>
- <xref:System.Windows.Media.RenderCapability>
- [<span data-ttu-id="d5dff-120">Уровни графической отрисовки</span><span class="sxs-lookup"><span data-stu-id="d5dff-120">Graphics Rendering Tiers</span></span>](graphics-rendering-tiers.md)
- [<span data-ttu-id="d5dff-121">Общие сведения об отрисовке графики в WPF</span><span class="sxs-lookup"><span data-stu-id="d5dff-121">WPF Graphics Rendering Overview</span></span>](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="d5dff-122">Макет</span><span class="sxs-lookup"><span data-stu-id="d5dff-122">Layout</span></span>](layout.md)
- [<span data-ttu-id="d5dff-123">Деревья в WPF</span><span class="sxs-lookup"><span data-stu-id="d5dff-123">Trees in WPF</span></span>](trees-in-wpf.md)
- [<span data-ttu-id="d5dff-124">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="d5dff-124">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="d5dff-125">Использование объектов DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="d5dff-125">Using DrawingVisual Objects</span></span>](../graphics-multimedia/using-drawingvisual-objects.md)
- [<span data-ttu-id="d5dff-126">Общие сведения о свойствах зависимости</span><span class="sxs-lookup"><span data-stu-id="d5dff-126">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="d5dff-127">Общие сведения об объектах класса Freezable</span><span class="sxs-lookup"><span data-stu-id="d5dff-127">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="d5dff-128">Ресурсы XAML</span><span class="sxs-lookup"><span data-stu-id="d5dff-128">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="d5dff-129">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="d5dff-129">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="d5dff-130">Рисование форматированного текста</span><span class="sxs-lookup"><span data-stu-id="d5dff-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
- [<span data-ttu-id="d5dff-131">Оформление в WPF</span><span class="sxs-lookup"><span data-stu-id="d5dff-131">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="d5dff-132">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="d5dff-132">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="d5dff-133">Общие сведения о переходах</span><span class="sxs-lookup"><span data-stu-id="d5dff-133">Navigation Overview</span></span>](../app-development/navigation-overview.md)
- [<span data-ttu-id="d5dff-134">Советы и рекомендации по анимации</span><span class="sxs-lookup"><span data-stu-id="d5dff-134">Animation Tips and Tricks</span></span>](../graphics-multimedia/animation-tips-and-tricks.md)
- [<span data-ttu-id="d5dff-135">Пошаговое руководство. Кэширование данных приложения WPF</span><span class="sxs-lookup"><span data-stu-id="d5dff-135">Walkthrough: Caching Application Data in a WPF Application</span></span>](walkthrough-caching-application-data-in-a-wpf-application.md)
