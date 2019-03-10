---
title: Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile
ms.date: 03/30/2017
helpviewer_keywords:
- metafiles [Windows Forms], about metafiles
- bitmaps [Windows Forms], about bitmaps
- images [Windows Forms], about images
- Windows Forms, images
ms.assetid: 7152b45b-a55c-49bc-8c78-ae002a844f71
ms.openlocfilehash: 2ce19642b37946db7a172e61004688059dba61db
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717431"
---
# <a name="images-bitmaps-and-metafiles"></a><span data-ttu-id="222cd-102">Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile</span><span class="sxs-lookup"><span data-stu-id="222cd-102">Images, Bitmaps, and Metafiles</span></span>
<span data-ttu-id="222cd-103">
  `Image\` — это абстрактный базовый класс, содержащий методы для работы с растровыми изображениями (точечными рисунками) и векторными изображениями (метафайлами).</span><span class="sxs-lookup"><span data-stu-id="222cd-103">The `Image` class is an abstract base class that provides methods for working with raster images (bitmaps) and vector images (metafiles).</span></span> <span data-ttu-id="222cd-104">Классы `Bitmap` и <xref:System.Drawing.Imaging.Metafile> унаследованы от класса `Image`.</span><span class="sxs-lookup"><span data-stu-id="222cd-104">The `Bitmap` class and the <xref:System.Drawing.Imaging.Metafile> class both inherit from the `Image` class.</span></span> <span data-ttu-id="222cd-105">Класс `Bitmap` расширяет возможности класса `Image` за счет дополнительных методов для загрузки, сохранения и использования растровых изображений.</span><span class="sxs-lookup"><span data-stu-id="222cd-105">The `Bitmap` class expands on the capabilities of the `Image` class by providing additional methods for loading, saving, and manipulating raster images.</span></span> <span data-ttu-id="222cd-106">Класс <xref:System.Drawing.Imaging.Metafile> расширяет возможности класса `Image` за счет дополнительных методов для записи и анализа векторных изображений.</span><span class="sxs-lookup"><span data-stu-id="222cd-106">The <xref:System.Drawing.Imaging.Metafile> class expands on the capabilities of the `Image` class by providing additional methods for recording and examining vector images.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="222cd-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="222cd-107">In This Section</span></span>  
 [<span data-ttu-id="222cd-108">Типы растровых изображений</span><span class="sxs-lookup"><span data-stu-id="222cd-108">Types of Bitmaps</span></span>](types-of-bitmaps.md)  
 <span data-ttu-id="222cd-109">Описываются различные форматы изображений.</span><span class="sxs-lookup"><span data-stu-id="222cd-109">Discusses the various image formats.</span></span>  
  
 [<span data-ttu-id="222cd-110">Метафайлы в GDI+</span><span class="sxs-lookup"><span data-stu-id="222cd-110">Metafiles in GDI+</span></span>](metafiles-in-gdi.md)  
 <span data-ttu-id="222cd-111">Описывается поддержка метафайлов в [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="222cd-111">Discusses [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] support for metafiles.</span></span>  
  
 [<span data-ttu-id="222cd-112">Рисование, позиционирование и клонирование изображений в GDI+</span><span class="sxs-lookup"><span data-stu-id="222cd-112">Drawing, Positioning, and Cloning Images in GDI+</span></span>](drawing-positioning-and-cloning-images-in-gdi.md)  
 <span data-ttu-id="222cd-113">Описываются методы, которые служат для рисования векторных и растровых изображений в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="222cd-113">Discusses methods for drawing vector and raster images with managed code.</span></span>  
  
 [<span data-ttu-id="222cd-114">Обрезка и масштабирование изображений в GDI+</span><span class="sxs-lookup"><span data-stu-id="222cd-114">Cropping and Scaling Images in GDI+</span></span>](cropping-and-scaling-images-in-gdi.md)  
 <span data-ttu-id="222cd-115">Описываются методы, которые служат для обрезки и масштабирования векторных и растровых изображений в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="222cd-115">Discusses methods for cropping and scaling vector and raster images with managed code</span></span>  
  
## <a name="reference"></a><span data-ttu-id="222cd-116">Ссылка</span><span class="sxs-lookup"><span data-stu-id="222cd-116">Reference</span></span>  
 <xref:System.Drawing.Image>  
 <span data-ttu-id="222cd-117">Описывает данный класс и предоставляет ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="222cd-117">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Bitmap>  
 <span data-ttu-id="222cd-118">Описание класса и ссылки на разделы с описаниями всех его членов.</span><span class="sxs-lookup"><span data-stu-id="222cd-118">Describes this class and has links to all of its members</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="222cd-119">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="222cd-119">Related Sections</span></span>  
 [<span data-ttu-id="222cd-120">Работа с растровыми и векторными изображениями, значками и метафайлами</span><span class="sxs-lookup"><span data-stu-id="222cd-120">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)  
 <span data-ttu-id="222cd-121">Ссылки на разделы, в которых демонстрируется использование изображений в приложениях.</span><span class="sxs-lookup"><span data-stu-id="222cd-121">Contains links to topics that demonstrate how to use images in your application.</span></span>
