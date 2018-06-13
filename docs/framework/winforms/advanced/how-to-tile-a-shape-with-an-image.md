---
title: Практическое руководство. Мозаичное заполнение фигуры заданным изображением
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- texture brushes [Windows Forms], tiling images with
- images [Windows Forms], filling shapes with
- shapes [Windows Forms], tiling with images
- bitmaps [Windows Forms], filling shapes with
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
ms.openlocfilehash: 0905f29b0f74c72979e252cf94e677d1c7e0525d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523127"
---
# <a name="how-to-tile-a-shape-with-an-image"></a><span data-ttu-id="552ef-102">Практическое руководство. Мозаичное заполнение фигуры заданным изображением</span><span class="sxs-lookup"><span data-stu-id="552ef-102">How to: Tile a Shape with an Image</span></span>
<span data-ttu-id="552ef-103">Аналогично плитки можно поместить рядом друг с другом пола, чтобы заполнить фигуру прямоугольные изображения можно поместить рядом друг с другом.</span><span class="sxs-lookup"><span data-stu-id="552ef-103">Just as tiles can be placed next to each other to cover a floor, rectangular images can be placed next to each other to fill (tile) a shape.</span></span> <span data-ttu-id="552ef-104">Для мозаичного заполнения внутренней области фигуры, используйте кисти текстуры.</span><span class="sxs-lookup"><span data-stu-id="552ef-104">To tile the interior of a shape, use a texture brush.</span></span> <span data-ttu-id="552ef-105">При построении <xref:System.Drawing.TextureBrush> объекта, один из аргументов, можно передать конструктору <xref:System.Drawing.Image> объекта.</span><span class="sxs-lookup"><span data-stu-id="552ef-105">When you construct a <xref:System.Drawing.TextureBrush> object, one of the arguments you pass to the constructor is an <xref:System.Drawing.Image> object.</span></span> <span data-ttu-id="552ef-106">При использовании кисти текстуры для рисования внутренней части фигуры заполнение повторяющиеся копии изображения.</span><span class="sxs-lookup"><span data-stu-id="552ef-106">When you use the texture brush to paint the interior of a shape, the shape is filled with repeated copies of this image.</span></span>  
  
 <span data-ttu-id="552ef-107">Свойства режима переноса <xref:System.Drawing.TextureBrush> определяет способ ориентации изображения при повторяется в прямоугольной сетки.</span><span class="sxs-lookup"><span data-stu-id="552ef-107">The wrap mode property of the <xref:System.Drawing.TextureBrush> object determines how the image is oriented as it is repeated in a rectangular grid.</span></span> <span data-ttu-id="552ef-108">Можно выполнить прислали плитки в сетке ту же ориентацию, или чтобы зеркальное отображение изображения от позиции одной сетки к другому.</span><span class="sxs-lookup"><span data-stu-id="552ef-108">You can make all the tiles in the grid have the same orientation, or you can make the image flip from one grid position to the next.</span></span> <span data-ttu-id="552ef-109">Зеркальное отображение может быть горизонтальным, по вертикали или оба.</span><span class="sxs-lookup"><span data-stu-id="552ef-109">The flipping can be horizontal, vertical, or both.</span></span> <span data-ttu-id="552ef-110">В следующих примерах демонстрируется мозаичное заполнение с использованием различных типов зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="552ef-110">The following examples demonstrate tiling with different types of flipping.</span></span>  
  
### <a name="to-tile-an-image"></a><span data-ttu-id="552ef-111">Мозаичное заполнение изображением</span><span class="sxs-lookup"><span data-stu-id="552ef-111">To tile an image</span></span>  
  
-   <span data-ttu-id="552ef-112">В этом примере используется на следующем рисунке 75 × 75 для мозаичного заполнения прямоугольника размером 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="552ef-112">This example uses the following 75×75 image to tile a 200×200 rectangle.</span></span>  
  
 <span data-ttu-id="552ef-113">![Плитки 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")</span><span class="sxs-lookup"><span data-stu-id="552ef-113">![Tile 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")</span></span>  
  
-   <span data-ttu-id="552ef-114">Ниже показано, как выполняется мозаичное заполнение прямоугольника с изображением.</span><span class="sxs-lookup"><span data-stu-id="552ef-114">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="552ef-115">Обратите внимание, что все плитки ту же ориентацию; не существует зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="552ef-115">Note that all tiles have the same orientation; there is no flipping.</span></span>  
  
 <span data-ttu-id="552ef-116">![Плитки 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")</span><span class="sxs-lookup"><span data-stu-id="552ef-116">![Tile 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a><span data-ttu-id="552ef-117">Отражение изображения по горизонтали при мозаичное заполнение</span><span class="sxs-lookup"><span data-stu-id="552ef-117">To flip an image horizontally while tiling</span></span>  
  
-   <span data-ttu-id="552ef-118">В этом примере используется одно изображение размером 75 × 75 для заполнения прямоугольника размером 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="552ef-118">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="552ef-119">Режим переноса равно отражение изображения по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="552ef-119">The wrap mode is set to flip the image horizontally.</span></span> <span data-ttu-id="552ef-120">Ниже показано, как выполняется мозаичное заполнение прямоугольника с изображением.</span><span class="sxs-lookup"><span data-stu-id="552ef-120">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="552ef-121">Обратите внимание, что при переходе от одного элемента к другому в данной строке сетки изображение зеркально отображается по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="552ef-121">Note that as you move from one tile to the next in a given row, the image is flipped horizontally.</span></span>  
  
 <span data-ttu-id="552ef-122">![Плитки 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")</span><span class="sxs-lookup"><span data-stu-id="552ef-122">![Tile 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a><span data-ttu-id="552ef-123">Отражение изображения по вертикали при мозаичное заполнение</span><span class="sxs-lookup"><span data-stu-id="552ef-123">To flip an image vertically while tiling</span></span>  
  
-   <span data-ttu-id="552ef-124">В этом примере используется одно изображение размером 75 × 75 для заполнения прямоугольника размером 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="552ef-124">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="552ef-125">Режим переноса равно отражение изображения по вертикали.</span><span class="sxs-lookup"><span data-stu-id="552ef-125">The wrap mode is set to flip the image vertically.</span></span>  
  
     [!code-csharp[System.Drawing.UsingABrush#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a><span data-ttu-id="552ef-126">Отражение изображения по горизонтали и вертикали мозаичное</span><span class="sxs-lookup"><span data-stu-id="552ef-126">To flip an image horizontally and vertically while tiling</span></span>  
  
-   <span data-ttu-id="552ef-127">В этом примере используется одно изображение размером 75 × 75 для мозаичного заполнения прямоугольника размером 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="552ef-127">This example uses the same 75×75 image to tile a 200×200 rectangle.</span></span> <span data-ttu-id="552ef-128">Режим переноса равно зеркальное отражение изображения по горизонтали и вертикали.</span><span class="sxs-lookup"><span data-stu-id="552ef-128">The wrap mode is set to flip the image both horizontally and vertically.</span></span> <span data-ttu-id="552ef-129">Ниже показано, как выполняется мозаичное заполнение прямоугольник в изображении.</span><span class="sxs-lookup"><span data-stu-id="552ef-129">The following illustration shows how the rectangle is tiled by the image.</span></span> <span data-ttu-id="552ef-130">Обратите внимание, что при переходе от одного элемента к другому в данной строке сетки изображение зеркально отображается по горизонтали, а при переходе от одного элемента к элементу в заданном столбце изображение перевернута вертикально.</span><span class="sxs-lookup"><span data-stu-id="552ef-130">Note that as you move from one tile to the next in a given row, the image is flipped horizontally, and as you move from one tile to the next in a given column, the image is flipped vertically.</span></span>  
  
 <span data-ttu-id="552ef-131">![Плитки 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")</span><span class="sxs-lookup"><span data-stu-id="552ef-131">![Tile 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="552ef-132">См. также</span><span class="sxs-lookup"><span data-stu-id="552ef-132">See Also</span></span>  
 [<span data-ttu-id="552ef-133">Использование кисти для заливки фигур</span><span class="sxs-lookup"><span data-stu-id="552ef-133">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
