---
title: Улучшение производительности приложений WPF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
caps.latest.revision: 45
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d2de2d4009cb29c5e9cbdace0d69c220f95a54e1
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="a8fbd-102">Улучшение производительности приложений WPF</span><span class="sxs-lookup"><span data-stu-id="a8fbd-102">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="a8fbd-103">Этот раздел предназначен в качестве справочника по [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] разработчики приложений, которым нужны дополнительные способы повышения производительности своих приложений.</span><span class="sxs-lookup"><span data-stu-id="a8fbd-103">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="a8fbd-104">Если вы являетесь разработчиком, является новой возможностью в Microsoft .NET Framework и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], следует сначала ознакомиться с обеими платформами.</span><span class="sxs-lookup"><span data-stu-id="a8fbd-104">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="a8fbd-105">Этот раздел предполагает понимание принципов работы обеих и предназначен для программистов, уже достаточно информации, чтобы получить работающую систему свои приложения.</span><span class="sxs-lookup"><span data-stu-id="a8fbd-105">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8fbd-106">Данные о производительности в этом разделе основаны на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложений, выполняющихся на 2,8 ГГц ПК с 512 МБ оперативной памяти и ATI Radeon 9700 видеокарте.</span><span class="sxs-lookup"><span data-stu-id="a8fbd-106">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a8fbd-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a8fbd-107">In This Section</span></span>  
 [<span data-ttu-id="a8fbd-108">Планирование производительности приложения</span><span class="sxs-lookup"><span data-stu-id="a8fbd-108">Planning for Application Performance</span></span>](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
  
 [<span data-ttu-id="a8fbd-109">Использование преимуществ оборудования</span><span class="sxs-lookup"><span data-stu-id="a8fbd-109">Taking Advantage of Hardware</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="a8fbd-110">Разметка и разработка</span><span class="sxs-lookup"><span data-stu-id="a8fbd-110">Layout and Design</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="a8fbd-111">Двумерная графика и изображения</span><span class="sxs-lookup"><span data-stu-id="a8fbd-111">2D Graphics and Imaging</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="a8fbd-112">Поведение объекта</span><span class="sxs-lookup"><span data-stu-id="a8fbd-112">Object Behavior</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="a8fbd-113">Ресурсы приложений</span><span class="sxs-lookup"><span data-stu-id="a8fbd-113">Application Resources</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="a8fbd-114">Text</span><span class="sxs-lookup"><span data-stu-id="a8fbd-114">Text</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
  
 [<span data-ttu-id="a8fbd-115">Привязка данных</span><span class="sxs-lookup"><span data-stu-id="a8fbd-115">Data Binding</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="a8fbd-116">Элементы управления</span><span class="sxs-lookup"><span data-stu-id="a8fbd-116">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)  
  
 [<span data-ttu-id="a8fbd-117">Дополнительные рекомендации по повышению производительности</span><span class="sxs-lookup"><span data-stu-id="a8fbd-117">Other Performance Recommendations</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="a8fbd-118">Время запуска приложения</span><span class="sxs-lookup"><span data-stu-id="a8fbd-118">Application Startup Time</span></span>](../../../../docs/framework/wpf/advanced/application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="a8fbd-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a8fbd-119">See Also</span></span>  
 <xref:System.Windows.Media.RenderOptions>  
 <xref:System.Windows.Media.RenderCapability>  
 [<span data-ttu-id="a8fbd-120">Уровни графической отрисовки</span><span class="sxs-lookup"><span data-stu-id="a8fbd-120">Graphics Rendering Tiers</span></span>](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)  
 [<span data-ttu-id="a8fbd-121">Общие сведения об отрисовке графики в WPF</span><span class="sxs-lookup"><span data-stu-id="a8fbd-121">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [<span data-ttu-id="a8fbd-122">Макет</span><span class="sxs-lookup"><span data-stu-id="a8fbd-122">Layout</span></span>](../../../../docs/framework/wpf/advanced/layout.md)  
 [<span data-ttu-id="a8fbd-123">Деревья в WPF</span><span class="sxs-lookup"><span data-stu-id="a8fbd-123">Trees in WPF</span></span>](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)  
 [<span data-ttu-id="a8fbd-124">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="a8fbd-124">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="a8fbd-125">Использование объектов DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="a8fbd-125">Using DrawingVisual Objects</span></span>](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)  
 [<span data-ttu-id="a8fbd-126">Общие сведения о свойствах зависимости</span><span class="sxs-lookup"><span data-stu-id="a8fbd-126">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [<span data-ttu-id="a8fbd-127">Общие сведения об объектах класса Freezable</span><span class="sxs-lookup"><span data-stu-id="a8fbd-127">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="a8fbd-128">Ресурсы XAML</span><span class="sxs-lookup"><span data-stu-id="a8fbd-128">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="a8fbd-129">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="a8fbd-129">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="a8fbd-130">Рисование форматированного текста</span><span class="sxs-lookup"><span data-stu-id="a8fbd-130">Drawing Formatted Text</span></span>](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)  
 [<span data-ttu-id="a8fbd-131">Оформление в WPF</span><span class="sxs-lookup"><span data-stu-id="a8fbd-131">Typography in WPF</span></span>](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [<span data-ttu-id="a8fbd-132">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="a8fbd-132">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="a8fbd-133">Общие сведения о переходах</span><span class="sxs-lookup"><span data-stu-id="a8fbd-133">Navigation Overview</span></span>](../../../../docs/framework/wpf/app-development/navigation-overview.md)  
 [<span data-ttu-id="a8fbd-134">Советы и рекомендации по анимации</span><span class="sxs-lookup"><span data-stu-id="a8fbd-134">Animation Tips and Tricks</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)  
 [<span data-ttu-id="a8fbd-135">Пошаговое руководство. Кэширование данных приложения WPF</span><span class="sxs-lookup"><span data-stu-id="a8fbd-135">Walkthrough: Caching Application Data in a WPF Application</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)
