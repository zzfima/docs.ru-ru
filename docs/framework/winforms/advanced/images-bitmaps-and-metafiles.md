---
title: "Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- metafiles [Windows Forms], about metafiles
- bitmaps [Windows Forms], about bitmaps
- images [Windows Forms], about images
- Windows Forms, images
ms.assetid: 7152b45b-a55c-49bc-8c78-ae002a844f71
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 67f72847e5dca20acd623c566a882e0094e94f68
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="images-bitmaps-and-metafiles"></a><span data-ttu-id="39d30-102">Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile</span><span class="sxs-lookup"><span data-stu-id="39d30-102">Images, Bitmaps, and Metafiles</span></span>
<span data-ttu-id="39d30-103">`Image` — это абстрактный базовый класс, содержащий методы для работы с растровыми изображениями (точечными рисунками) и векторными изображениями (метафайлами).</span><span class="sxs-lookup"><span data-stu-id="39d30-103">The `Image` class is an abstract base class that provides methods for working with raster images (bitmaps) and vector images (metafiles).</span></span> <span data-ttu-id="39d30-104">Классы `Bitmap` и <xref:System.Drawing.Imaging.Metafile> унаследованы от класса `Image`.</span><span class="sxs-lookup"><span data-stu-id="39d30-104">The `Bitmap` class and the <xref:System.Drawing.Imaging.Metafile> class both inherit from the `Image` class.</span></span> <span data-ttu-id="39d30-105">Класс `Bitmap` расширяет возможности класса `Image` за счет дополнительных методов для загрузки, сохранения и использования растровых изображений.</span><span class="sxs-lookup"><span data-stu-id="39d30-105">The `Bitmap` class expands on the capabilities of the `Image` class by providing additional methods for loading, saving, and manipulating raster images.</span></span> <span data-ttu-id="39d30-106">Класс <xref:System.Drawing.Imaging.Metafile> расширяет возможности класса `Image` за счет дополнительных методов для записи и анализа векторных изображений.</span><span class="sxs-lookup"><span data-stu-id="39d30-106">The <xref:System.Drawing.Imaging.Metafile> class expands on the capabilities of the `Image` class by providing additional methods for recording and examining vector images.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="39d30-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="39d30-107">In This Section</span></span>  
 [<span data-ttu-id="39d30-108">Типы растровых изображений</span><span class="sxs-lookup"><span data-stu-id="39d30-108">Types of Bitmaps</span></span>](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)  
 <span data-ttu-id="39d30-109">Описываются различные форматы изображений.</span><span class="sxs-lookup"><span data-stu-id="39d30-109">Discusses the various image formats.</span></span>  
  
 [<span data-ttu-id="39d30-110">Метафайлы в GDI+</span><span class="sxs-lookup"><span data-stu-id="39d30-110">Metafiles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/metafiles-in-gdi.md)  
 <span data-ttu-id="39d30-111">Описывается поддержка метафайлов в [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39d30-111">Discusses [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] support for metafiles.</span></span>  
  
 [<span data-ttu-id="39d30-112">Рисование, позиционирование и клонирование изображений в GDI+</span><span class="sxs-lookup"><span data-stu-id="39d30-112">Drawing, Positioning, and Cloning Images in GDI+</span></span>](../../../../docs/framework/winforms/advanced/drawing-positioning-and-cloning-images-in-gdi.md)  
 <span data-ttu-id="39d30-113">Описываются методы, которые служат для рисования векторных и растровых изображений в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="39d30-113">Discusses methods for drawing vector and raster images with managed code.</span></span>  
  
 [<span data-ttu-id="39d30-114">Обрезка и масштабирование изображений в GDI+</span><span class="sxs-lookup"><span data-stu-id="39d30-114">Cropping and Scaling Images in GDI+</span></span>](../../../../docs/framework/winforms/advanced/cropping-and-scaling-images-in-gdi.md)  
 <span data-ttu-id="39d30-115">Описываются методы, которые служат для обрезки и масштабирования векторных и растровых изображений в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="39d30-115">Discusses methods for cropping and scaling vector and raster images with managed code</span></span>  
  
## <a name="reference"></a><span data-ttu-id="39d30-116">Ссылка</span><span class="sxs-lookup"><span data-stu-id="39d30-116">Reference</span></span>  
 <xref:System.Drawing.Image>  
 <span data-ttu-id="39d30-117">Описывает данный класс и предоставляет ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="39d30-117">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Bitmap>  
 <span data-ttu-id="39d30-118">Описание класса и ссылки на разделы с описаниями всех его членов.</span><span class="sxs-lookup"><span data-stu-id="39d30-118">Describes this class and has links to all of its members</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="39d30-119">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="39d30-119">Related Sections</span></span>  
 [<span data-ttu-id="39d30-120">Работа с растровыми и векторными изображениями, значками и метафайлами</span><span class="sxs-lookup"><span data-stu-id="39d30-120">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)  
 <span data-ttu-id="39d30-121">Ссылки на разделы, в которых демонстрируется использование изображений в приложениях.</span><span class="sxs-lookup"><span data-stu-id="39d30-121">Contains links to topics that demonstrate how to use images in your application.</span></span>
