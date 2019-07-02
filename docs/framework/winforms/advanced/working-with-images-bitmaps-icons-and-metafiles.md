---
title: Работа с растровыми и векторными изображениями
ms.date: 03/30/2017
helpviewer_keywords:
- metafiles [Windows Forms], working with
- examples [Windows Forms], bitmaps
- examples [Windows Forms], images
- bitmaps [Windows Forms], working with
- images [Windows Forms], working with
- examples [Windows Forms], metafiles
ms.assetid: a626d701-bd99-4fd8-b92f-7b8f794e042b
ms.openlocfilehash: 8c778018a2d78fbec67a3bf41b5cbaa8e4bfb606
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504854"
---
# <a name="working-with-images-bitmaps-icons-and-metafiles"></a><span data-ttu-id="0bd3d-102">Работа с растровыми и векторными изображениями</span><span class="sxs-lookup"><span data-stu-id="0bd3d-102">Working with Images, Bitmaps, Icons, and Metafiles</span></span>
<span data-ttu-id="0bd3d-103">GDI + предоставляет `Bitmap` класс для работы с растровыми изображениями и `Metafile` класс для работы с векторными изображениями.</span><span class="sxs-lookup"><span data-stu-id="0bd3d-103">GDI+ provides the `Bitmap` class for working with raster images and the `Metafile` class for working with vector images.</span></span> <span data-ttu-id="0bd3d-104">Классы `Bitmap` и `Metafile` являются производными от класса `Image`.</span><span class="sxs-lookup"><span data-stu-id="0bd3d-104">The `Bitmap` and the `Metafile` classes both inherit from the `Image` class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0bd3d-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="0bd3d-105">In This Section</span></span>  
 [<span data-ttu-id="0bd3d-106">Практическое руководство. Рисование существующего растрового изображения на экране</span><span class="sxs-lookup"><span data-stu-id="0bd3d-106">How to: Draw an Existing Bitmap to the Screen</span></span>](how-to-draw-an-existing-bitmap-to-the-screen.md)  
 <span data-ttu-id="0bd3d-107">Описано, как загружать и отображать точечные рисунки.</span><span class="sxs-lookup"><span data-stu-id="0bd3d-107">Describes how to load and draw bitmaps.</span></span>  
  
 [<span data-ttu-id="0bd3d-108">Практическое руководство. Загрузка и отображение метафайлов</span><span class="sxs-lookup"><span data-stu-id="0bd3d-108">How to: Load and Display Metafiles</span></span>](how-to-load-and-display-metafiles.md)  
 <span data-ttu-id="0bd3d-109">Описано, как загружать и отображать метафайлы.</span><span class="sxs-lookup"><span data-stu-id="0bd3d-109">Shows how to load and draw metafiles.</span></span>  
  
 [<span data-ttu-id="0bd3d-110">Обрезка и масштабирование изображений в GDI+</span><span class="sxs-lookup"><span data-stu-id="0bd3d-110">Cropping and Scaling Images in GDI+</span></span>](cropping-and-scaling-images-in-gdi.md)  
 <span data-ttu-id="0bd3d-111">Описано, как обрезать и масштабировать векторные и растровые изображения.</span><span class="sxs-lookup"><span data-stu-id="0bd3d-111">Explains how to crop and scale vector and raster images.</span></span>  
  
 [<span data-ttu-id="0bd3d-112">Практическое руководство. Поворот, отражение и наклон изображений</span><span class="sxs-lookup"><span data-stu-id="0bd3d-112">How to: Rotate, Reflect, and Skew Images</span></span>](how-to-rotate-reflect-and-skew-images.md)  
 <span data-ttu-id="0bd3d-113">Описано, как поворачивать, отражать и наклонять изображения.</span><span class="sxs-lookup"><span data-stu-id="0bd3d-113">Describes how to draw rotated, reflected and skewed images.</span></span>  
  
 [<span data-ttu-id="0bd3d-114">Практическое руководство. Использование режима интерполяции для управления качеством изображений при масштабировании</span><span class="sxs-lookup"><span data-stu-id="0bd3d-114">How to: Use Interpolation Mode to Control Image Quality During Scaling</span></span>](how-to-use-interpolation-mode-to-control-image-quality-during-scaling.md)  
 <span data-ttu-id="0bd3d-115">Показано, как использовать перечисления <xref:System.Drawing.Drawing2D.InterpolationMode> для изменения качества изображения.</span><span class="sxs-lookup"><span data-stu-id="0bd3d-115">Shows how to use the <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration to change image quality.</span></span>  
  
 [<span data-ttu-id="0bd3d-116">Практическое руководство. Создание эскизов изображений</span><span class="sxs-lookup"><span data-stu-id="0bd3d-116">How to: Create Thumbnail Images</span></span>](how-to-create-thumbnail-images.md)  
 <span data-ttu-id="0bd3d-117">Описано, как создавать эскизы изображений.</span><span class="sxs-lookup"><span data-stu-id="0bd3d-117">Describes how to create thumbnail images.</span></span>  
  
 [<span data-ttu-id="0bd3d-118">Практическое руководство. Повышение производительности за счет отключения автоматического масштабирования</span><span class="sxs-lookup"><span data-stu-id="0bd3d-118">How to: Improve Performance by Avoiding Automatic Scaling</span></span>](how-to-improve-performance-by-avoiding-automatic-scaling.md)  
 <span data-ttu-id="0bd3d-119">Объясняется, как рисовать изображения без автоматического масштабирования.</span><span class="sxs-lookup"><span data-stu-id="0bd3d-119">Explains how to draw an image without automatic scaling.</span></span>  
  
 [<span data-ttu-id="0bd3d-120">Практическое руководство. Чтение метаданных изображения</span><span class="sxs-lookup"><span data-stu-id="0bd3d-120">How to: Read Image Metadata</span></span>](how-to-read-image-metadata.md)  
 <span data-ttu-id="0bd3d-121">Описано, как производить чтение метаданных изображения.</span><span class="sxs-lookup"><span data-stu-id="0bd3d-121">Describes how to read metadata from an image.</span></span>  
  
 [<span data-ttu-id="0bd3d-122">Практическое руководство. Создание растрового изображения во время выполнения</span><span class="sxs-lookup"><span data-stu-id="0bd3d-122">How to: Create a Bitmap at Run Time</span></span>](how-to-create-a-bitmap-at-run-time.md)  
 <span data-ttu-id="0bd3d-123">Показано, как рисовать точечный рисунок во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0bd3d-123">Shows how to draw a bitmap at runtime.</span></span>  
  
 [<span data-ttu-id="0bd3d-124">Практическое руководство. Извлечение значка, связанного с файлом в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0bd3d-124">How to: Extract the Icon Associated with a File in Windows Forms</span></span>](how-to-extract-the-icon-associated-with-a-file-in-windows-forms.md)  
 <span data-ttu-id="0bd3d-125">Описано, как извлекать значок, являющийся внедренным ресурсом файла.</span><span class="sxs-lookup"><span data-stu-id="0bd3d-125">Describes how to extract an icon that is an embedded resource of a file.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0bd3d-126">Ссылка</span><span class="sxs-lookup"><span data-stu-id="0bd3d-126">Reference</span></span>  
 <xref:System.Drawing.Image>  
 <span data-ttu-id="0bd3d-127">Описывает данный класс и предоставляет ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="0bd3d-127">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Imaging.Metafile>  
 <span data-ttu-id="0bd3d-128">Описывает данный класс и предоставляет ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="0bd3d-128">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Bitmap>  
 <span data-ttu-id="0bd3d-129">Описывает данный класс и предоставляет ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="0bd3d-129">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0bd3d-130">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="0bd3d-130">Related Sections</span></span>  
 [<span data-ttu-id="0bd3d-131">Изображения, точечные рисунки и метафайлы</span><span class="sxs-lookup"><span data-stu-id="0bd3d-131">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)  
 <span data-ttu-id="0bd3d-132">Содержит ссылки на разделы с описанием различных типов растровых изображений и способов работы с ними в приложениях.</span><span class="sxs-lookup"><span data-stu-id="0bd3d-132">Contains links to topics that discuss different types of bitmaps and manipulating them in your applications.</span></span>
