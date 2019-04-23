---
title: Отрисовка, позиционирование и клонирование изображений в GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- raster images [Windows Forms]
- images [Windows Forms], positioning
- drawing [Windows Forms], images
- drawing [Windows Forms], raster images
- images [Windows Forms], cloning
- images [Windows Forms], drawing
- GDI+, drawing images
- GDI+, cloning images
- GDI+, positioning images
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
ms.openlocfilehash: b5f98e7bdef9ff8ed0a4cd0e040cb92a31f30503
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59188452"
---
# <a name="drawing-positioning-and-cloning-images-in-gdi"></a><span data-ttu-id="8109c-102">Отрисовка, позиционирование и клонирование изображений в GDI+</span><span class="sxs-lookup"><span data-stu-id="8109c-102">Drawing, Positioning, and Cloning Images in GDI+</span></span>
<span data-ttu-id="8109c-103">Можно использовать <xref:System.Drawing.Bitmap> класс для загрузки и отображения растровых изображений и может использовать <xref:System.Drawing.Imaging.Metafile> класс для загрузки и отображения векторных изображений.</span><span class="sxs-lookup"><span data-stu-id="8109c-103">You can use the <xref:System.Drawing.Bitmap> class to load and display raster images, and you can use the <xref:System.Drawing.Imaging.Metafile> class to load and display vector images.</span></span> <span data-ttu-id="8109c-104"><xref:System.Drawing.Bitmap> И <xref:System.Drawing.Imaging.Metafile> классы наследуют от <xref:System.Drawing.Image> класса.</span><span class="sxs-lookup"><span data-stu-id="8109c-104">The <xref:System.Drawing.Bitmap> and <xref:System.Drawing.Imaging.Metafile> classes inherit from the <xref:System.Drawing.Image> class.</span></span> <span data-ttu-id="8109c-105">Чтобы отобразить векторного изображения, вам потребуется экземпляр <xref:System.Drawing.Graphics> класс и <xref:System.Drawing.Imaging.Metafile>.</span><span class="sxs-lookup"><span data-stu-id="8109c-105">To display a vector image, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="8109c-106">Чтобы отобразить растровое изображение, требуется экземпляр <xref:System.Drawing.Graphics> класс и <xref:System.Drawing.Bitmap>.</span><span class="sxs-lookup"><span data-stu-id="8109c-106">To display a raster image, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="8109c-107">Экземпляр <xref:System.Drawing.Graphics> класс предоставляет <xref:System.Drawing.Graphics.DrawImage%2A> метод, который получает <xref:System.Drawing.Imaging.Metafile> или <xref:System.Drawing.Bitmap> в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="8109c-107">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawImage%2A> method, which receives the <xref:System.Drawing.Imaging.Metafile> or <xref:System.Drawing.Bitmap> as an argument.</span></span>  
  
## <a name="file-types-and-cloning"></a><span data-ttu-id="8109c-108">Типы файлов и клонирование</span><span class="sxs-lookup"><span data-stu-id="8109c-108">File Types and Cloning</span></span>  
 <span data-ttu-id="8109c-109">В следующем примере кода показано создание <xref:System.Drawing.Bitmap> из файла Climber.jpg и отображает точечный рисунок.</span><span class="sxs-lookup"><span data-stu-id="8109c-109">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Climber.jpg and displays the bitmap.</span></span> <span data-ttu-id="8109c-110">Конечная точка верхнего левого угла изображения, (10, 10), указанный в второй и третий параметры.</span><span class="sxs-lookup"><span data-stu-id="8109c-110">The destination point for the upper-left corner of the image, (10, 10), is specified in the second and third parameters.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 <span data-ttu-id="8109c-111">Ниже показано изображение.</span><span class="sxs-lookup"><span data-stu-id="8109c-111">The following illustration shows the image.</span></span>  
  
 <span data-ttu-id="8109c-112">![Изображение примера](./media/aboutgdip03-art04.gif "AboutGdip03_Art04")</span><span class="sxs-lookup"><span data-stu-id="8109c-112">![Image Sample](./media/aboutgdip03-art04.gif "AboutGdip03_Art04")</span></span>  
  
 <span data-ttu-id="8109c-113">Вы можете создать <xref:System.Drawing.Bitmap> объекты из различных графических форматов файлов: BMP, GIF, JPEG, EXIF, PNG, TIFF и значок.</span><span class="sxs-lookup"><span data-stu-id="8109c-113">You can construct <xref:System.Drawing.Bitmap> objects from a variety of graphics file formats: BMP, GIF, JPEG, EXIF, PNG, TIFF, and ICON.</span></span>  
  
 <span data-ttu-id="8109c-114">В следующем примере кода показано создание <xref:System.Drawing.Bitmap> объекты из различных типов файлов, а затем отображает точечные рисунки.</span><span class="sxs-lookup"><span data-stu-id="8109c-114">The following code example shows how to construct <xref:System.Drawing.Bitmap> objects from a variety of file types and then displays the bitmaps.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 <span data-ttu-id="8109c-115"><xref:System.Drawing.Bitmap> Класс предоставляет <xref:System.Drawing.Bitmap.Clone%2A> метод, который можно использовать для создания копии существующего <xref:System.Drawing.Bitmap>.</span><span class="sxs-lookup"><span data-stu-id="8109c-115">The <xref:System.Drawing.Bitmap> class provides a <xref:System.Drawing.Bitmap.Clone%2A> method that you can use to make a copy of an existing <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="8109c-116"><xref:System.Drawing.Bitmap.Clone%2A> Метод имеет параметр источника прямоугольник, который можно использовать для указания часть исходного точечного рисунка, который требуется скопировать.</span><span class="sxs-lookup"><span data-stu-id="8109c-116">The <xref:System.Drawing.Bitmap.Clone%2A> method has a source rectangle parameter that you can use to specify the portion of the original bitmap that you want to copy.</span></span> <span data-ttu-id="8109c-117">В следующем примере кода показано, как создать <xref:System.Drawing.Bitmap> путем клонирования в верхней части существующего <xref:System.Drawing.Bitmap>.</span><span class="sxs-lookup"><span data-stu-id="8109c-117">The following code example shows how to create a <xref:System.Drawing.Bitmap> by cloning the top half of an existing <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="8109c-118">Затем оба изображения отображаются.</span><span class="sxs-lookup"><span data-stu-id="8109c-118">Then both images are drawn.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 <span data-ttu-id="8109c-119">На следующем рисунке два изображения.</span><span class="sxs-lookup"><span data-stu-id="8109c-119">The following illustration shows the two images.</span></span>  
  
 <span data-ttu-id="8109c-120">![Обрезка](./media/aboutgdip03-art05.gif "AboutGdip03_Art05")</span><span class="sxs-lookup"><span data-stu-id="8109c-120">![Cropping](./media/aboutgdip03-art05.gif "AboutGdip03_Art05")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8109c-121">См. также</span><span class="sxs-lookup"><span data-stu-id="8109c-121">See also</span></span>

- [<span data-ttu-id="8109c-122">Изображения, точечные рисунки и метафайлы</span><span class="sxs-lookup"><span data-stu-id="8109c-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="8109c-123">Практическое руководство. Создание объектов Graphics для рисования</span><span class="sxs-lookup"><span data-stu-id="8109c-123">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="8109c-124">Работа с растровыми и векторными изображениями, значками и метафайлами</span><span class="sxs-lookup"><span data-stu-id="8109c-124">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
