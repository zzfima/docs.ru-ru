---
title: "Использование управляемых графических классов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GDI+, managed classes
- graphics [Windows Forms], using in Windows Forms
- graphics [Windows Forms], managed classes
ms.assetid: e6d1a42d-2100-46aa-97e6-a5ddc0baaae5
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7a53d5d4961e191ae3f3b821641e3f4b161cddf1
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="using-managed-graphics-classes"></a><span data-ttu-id="f6fee-102">Использование управляемых графических классов</span><span class="sxs-lookup"><span data-stu-id="f6fee-102">Using Managed Graphics Classes</span></span>
<span data-ttu-id="f6fee-103">Ниже описаны способы использования [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API в структуре управляемых классов.</span><span class="sxs-lookup"><span data-stu-id="f6fee-103">The following topics describe how to use the [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API in the managed class framework.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f6fee-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="f6fee-104">In This Section</span></span>  
 [<span data-ttu-id="f6fee-105">Приступая к программированию графики</span><span class="sxs-lookup"><span data-stu-id="f6fee-105">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 <span data-ttu-id="f6fee-106">Описывает, как выполнять основные задачи с помощью [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6fee-106">Describes how to accomplish basic tasks with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
 [<span data-ttu-id="f6fee-107">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="f6fee-107">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 <span data-ttu-id="f6fee-108">Демонстрирует создание пера и его использование для рисования различных линий и фигур.</span><span class="sxs-lookup"><span data-stu-id="f6fee-108">Demonstrates how to construct a pen and use it to draw a variety of lines and shapes.</span></span>  
  
 [<span data-ttu-id="f6fee-109">Использование кисти для заливки фигур</span><span class="sxs-lookup"><span data-stu-id="f6fee-109">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)  
 <span data-ttu-id="f6fee-110">В этой статье демонстрируется создание кисти и заливка фигур с использованием различных эффектов.</span><span class="sxs-lookup"><span data-stu-id="f6fee-110">Demonstrates how to construct a brush and fill shapes with a variety of effects.</span></span>  
  
 [<span data-ttu-id="f6fee-111">Заливка фигур с помощью градиентной кисти</span><span class="sxs-lookup"><span data-stu-id="f6fee-111">Using a Gradient Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)  
 <span data-ttu-id="f6fee-112">Показано, как создавать и использовать различные типы градиента кисти.</span><span class="sxs-lookup"><span data-stu-id="f6fee-112">Shows how to create and use different types of gradient brushes.</span></span>  
  
 [<span data-ttu-id="f6fee-113">Работа с растровыми и векторными изображениями, значками и метафайлами</span><span class="sxs-lookup"><span data-stu-id="f6fee-113">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)  
 <span data-ttu-id="f6fee-114">Описание способа создания и управления ими.</span><span class="sxs-lookup"><span data-stu-id="f6fee-114">Demonstrates how to construct and manipulate images.</span></span>  
  
 [<span data-ttu-id="f6fee-115">Альфа-смешение цвета для линий и заливок</span><span class="sxs-lookup"><span data-stu-id="f6fee-115">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)  
 <span data-ttu-id="f6fee-116">Демонстрируется реализация прозрачности фигур и линий.</span><span class="sxs-lookup"><span data-stu-id="f6fee-116">Demonstrates how to achieve transparency for shapes and lines.</span></span>  
  
 [<span data-ttu-id="f6fee-117">Работами со шрифтами и текстом</span><span class="sxs-lookup"><span data-stu-id="f6fee-117">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 <span data-ttu-id="f6fee-118">Показано, как рисование текста и использование шрифтов и их семейств.</span><span class="sxs-lookup"><span data-stu-id="f6fee-118">Shows how to draw text and use fonts and font families.</span></span>  
  
 [<span data-ttu-id="f6fee-119">Построение и рисование кривых</span><span class="sxs-lookup"><span data-stu-id="f6fee-119">Constructing and Drawing Curves</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)  
 <span data-ttu-id="f6fee-120">Показано, как рисовать фундаментальный и сплайнов Безье.</span><span class="sxs-lookup"><span data-stu-id="f6fee-120">Shows how to draw Cardinal and Bezier splines.</span></span>  
  
 [<span data-ttu-id="f6fee-121">Построение и рисование контуров</span><span class="sxs-lookup"><span data-stu-id="f6fee-121">Constructing and Drawing Paths</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)  
 <span data-ttu-id="f6fee-122">Показано, как создание фигур с помощью пути.</span><span class="sxs-lookup"><span data-stu-id="f6fee-122">Shows how to create figures using paths.</span></span>  
  
 [<span data-ttu-id="f6fee-123">Использование преобразований в управляемом GDI+</span><span class="sxs-lookup"><span data-stu-id="f6fee-123">Using Transformations in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)  
 <span data-ttu-id="f6fee-124">Преобразование матриц.</span><span class="sxs-lookup"><span data-stu-id="f6fee-124">Demonstrates matrix transformations.</span></span>  
  
 [<span data-ttu-id="f6fee-125">Использование графических контейнеров</span><span class="sxs-lookup"><span data-stu-id="f6fee-125">Using Graphics Containers</span></span>](../../../../docs/framework/winforms/advanced/using-graphics-containers.md)  
 <span data-ttu-id="f6fee-126">Показано, как управлять графический объект состояния и вложенных графических контейнеров.</span><span class="sxs-lookup"><span data-stu-id="f6fee-126">Shows how to manage graphics object state and nested graphics containers.</span></span>  
  
 [<span data-ttu-id="f6fee-127">Использование областей</span><span class="sxs-lookup"><span data-stu-id="f6fee-127">Using Regions</span></span>](../../../../docs/framework/winforms/advanced/using-regions.md)  
 <span data-ttu-id="f6fee-128">Демонстрируется проверка попадания и задание области обрезки.</span><span class="sxs-lookup"><span data-stu-id="f6fee-128">Demonstrates hit testing and clipping with regions.</span></span>  
  
 [<span data-ttu-id="f6fee-129">перекрашивание изображений</span><span class="sxs-lookup"><span data-stu-id="f6fee-129">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)  
 <span data-ttu-id="f6fee-130">Описание различных аспектов управления цветами.</span><span class="sxs-lookup"><span data-stu-id="f6fee-130">Demonstrates various aspects of manipulating colors.</span></span>  
  
 [<span data-ttu-id="f6fee-131">Применение кодировщиков и декодеров изображений в управляемом GDI+</span><span class="sxs-lookup"><span data-stu-id="f6fee-131">Using Image Encoders and Decoders in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)  
 <span data-ttu-id="f6fee-132">Показано, как использовать кодировщиков и декодеров изображений для управления ими.</span><span class="sxs-lookup"><span data-stu-id="f6fee-132">Show how to use image encoders and decoders to manipulate images.</span></span>  
  
 [<span data-ttu-id="f6fee-133">Двойная буферизация графики</span><span class="sxs-lookup"><span data-stu-id="f6fee-133">Double Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 <span data-ttu-id="f6fee-134">Показано, как снижение мерцания с помощью двойной буферизации.</span><span class="sxs-lookup"><span data-stu-id="f6fee-134">Demonstrates how to reduce flicker with double buffering.</span></span>
