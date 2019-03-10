---
title: Применение кодировщиков и декодеров изображений в управляемом GDI+
ms.date: 03/30/2017
helpviewer_keywords:
- image encoders [Windows Forms], using
- image decoders [Windows Forms], using
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
ms.openlocfilehash: bf0d3a64ce8860d67f0dcfd37c780f03fbd7471a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713271"
---
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a><span data-ttu-id="925f4-102">Применение кодировщиков и декодеров изображений в управляемом GDI+</span><span class="sxs-lookup"><span data-stu-id="925f4-102">Using Image Encoders and Decoders in Managed GDI+</span></span>
<span data-ttu-id="925f4-103"><xref:System.Drawing> Пространство имен предоставляет <xref:System.Drawing.Image> и <xref:System.Drawing.Bitmap> классы для хранения и управления изображениями.</span><span class="sxs-lookup"><span data-stu-id="925f4-103">The <xref:System.Drawing> namespace provides the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> classes for storing and manipulating images.</span></span> <span data-ttu-id="925f4-104">С помощью кодировщиков изображений [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], можно сохранять изображения из памяти на диск.</span><span class="sxs-lookup"><span data-stu-id="925f4-104">By using image encoders in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can write images from memory to disk.</span></span> <span data-ttu-id="925f4-105">С помощью декодеров изображений в [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], можно загружать изображения с диска в память.</span><span class="sxs-lookup"><span data-stu-id="925f4-105">By using image decoders in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can load images from disk into memory.</span></span> <span data-ttu-id="925f4-106">Кодировщик преобразует данные в <xref:System.Drawing.Image> или <xref:System.Drawing.Bitmap> объект в формат файла выделенном диске.</span><span class="sxs-lookup"><span data-stu-id="925f4-106">An encoder translates the data in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object into a designated disk file format.</span></span> <span data-ttu-id="925f4-107">Декодер преобразует данные в файл на диске в формате, необходимом <xref:System.Drawing.Image> и <xref:System.Drawing.Bitmap> объектов.</span><span class="sxs-lookup"><span data-stu-id="925f4-107">A decoder translates the data in a disk file to the format required by the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> objects.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="925f4-108">имеет встроенные кодировщики и декодеры, которые поддерживают следующие типы файлов:</span><span class="sxs-lookup"><span data-stu-id="925f4-108">has built-in encoders and decoders that support the following file types:</span></span>  
  
-   <span data-ttu-id="925f4-109">BMP</span><span class="sxs-lookup"><span data-stu-id="925f4-109">BMP</span></span>  
  
-   <span data-ttu-id="925f4-110">GIF</span><span class="sxs-lookup"><span data-stu-id="925f4-110">GIF</span></span>  
  
-   <span data-ttu-id="925f4-111">JPEG</span><span class="sxs-lookup"><span data-stu-id="925f4-111">JPEG</span></span>  
  
-   <span data-ttu-id="925f4-112">PNG</span><span class="sxs-lookup"><span data-stu-id="925f4-112">PNG</span></span>  
  
-   <span data-ttu-id="925f4-113">TIFF</span><span class="sxs-lookup"><span data-stu-id="925f4-113">TIFF</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="925f4-114">также имеются встроенные декодеры, которые поддерживают следующие типы файлов:</span><span class="sxs-lookup"><span data-stu-id="925f4-114">also has built-in decoders that support the following file types:</span></span>  
  
-   <span data-ttu-id="925f4-115">WMF</span><span class="sxs-lookup"><span data-stu-id="925f4-115">WMF</span></span>  
  
-   <span data-ttu-id="925f4-116">EMF</span><span class="sxs-lookup"><span data-stu-id="925f4-116">EMF</span></span>  
  
-   <span data-ttu-id="925f4-117">ЗНАЧОК</span><span class="sxs-lookup"><span data-stu-id="925f4-117">ICON</span></span>  
  
 <span data-ttu-id="925f4-118">Кодировщики и декодеры, более подробно рассматривается в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="925f4-118">The following topics discuss encoders and decoders in more detail:</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="925f4-119">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="925f4-119">In This Section</span></span>  
 [<span data-ttu-id="925f4-120">Практическое руководство. Получение списка установленных кодировщиков</span><span class="sxs-lookup"><span data-stu-id="925f4-120">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)  
 <span data-ttu-id="925f4-121">Описывает способы просмотра кодировщикам, которые доступны на компьютере.</span><span class="sxs-lookup"><span data-stu-id="925f4-121">Describes how to list the encoders available on a computer.</span></span>  
  
 [<span data-ttu-id="925f4-122">Практическое руководство. Получение списка установленных декодеров</span><span class="sxs-lookup"><span data-stu-id="925f4-122">How to: List Installed Decoders</span></span>](how-to-list-installed-decoders.md)  
 <span data-ttu-id="925f4-123">Описывает способы просмотра декодеров на компьютере.</span><span class="sxs-lookup"><span data-stu-id="925f4-123">Describes how to list the decoders available on a computer.</span></span>  
  
 [<span data-ttu-id="925f4-124">Практическое руководство. Определение параметров, поддерживаемых кодировщиком</span><span class="sxs-lookup"><span data-stu-id="925f4-124">How to: Determine the Parameters Supported by an Encoder</span></span>](how-to-determine-the-parameters-supported-by-an-encoder.md)  
 <span data-ttu-id="925f4-125">Описывает способы просмотра <xref:System.Drawing.Imaging.EncoderParameters> поддерживаемых кодировщиком.</span><span class="sxs-lookup"><span data-stu-id="925f4-125">Describes how to list the <xref:System.Drawing.Imaging.EncoderParameters> supported by an encoder.</span></span>  
  
 [<span data-ttu-id="925f4-126">Практическое руководство. Преобразовать изображение из формата BMP в формат PNG</span><span class="sxs-lookup"><span data-stu-id="925f4-126">How to: Convert a BMP image to a PNG image</span></span>](how-to-convert-a-bmp-image-to-a-png-image.md)  
 <span data-ttu-id="925f4-127">В этой статье описывается сохранение изображения в различный формат изображения.</span><span class="sxs-lookup"><span data-stu-id="925f4-127">Describes how to save a image in a different image format.</span></span>  
  
 [<span data-ttu-id="925f4-128">Практическое руководство. Установка уровня сжатия JPEG</span><span class="sxs-lookup"><span data-stu-id="925f4-128">How to: Set JPEG Compression Level</span></span>](how-to-set-jpeg-compression-level.md)  
 <span data-ttu-id="925f4-129">В этой статье описывается изменение уровень качества изображения.</span><span class="sxs-lookup"><span data-stu-id="925f4-129">Describes how to change the quality level of an image.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="925f4-130">Ссылка</span><span class="sxs-lookup"><span data-stu-id="925f4-130">Reference</span></span>  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a><span data-ttu-id="925f4-131">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="925f4-131">Related Sections</span></span>  
 [<span data-ttu-id="925f4-132">Управляемый код GDI+</span><span class="sxs-lookup"><span data-stu-id="925f4-132">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
  
 [<span data-ttu-id="925f4-133">Изображения, точечные рисунки и метафайлы</span><span class="sxs-lookup"><span data-stu-id="925f4-133">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
