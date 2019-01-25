---
title: Как выполнить Мозаичное заполнение фигуры заданным изображением
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
ms.openlocfilehash: f2edde7e78f996d4a7bfbc636210f315c0718f6d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693218"
---
# <a name="how-to-tile-a-shape-with-an-image"></a><span data-ttu-id="42a7e-102">Как выполнить Мозаичное заполнение фигуры заданным изображением</span><span class="sxs-lookup"><span data-stu-id="42a7e-102">How to: Tile a Shape with an Image</span></span>
<span data-ttu-id="42a7e-103">Так же, как плиток можно поместить рядом друг с другом пола, прямоугольные изображения можно поместить рядом друг с другом заполнить фигуру.</span><span class="sxs-lookup"><span data-stu-id="42a7e-103">Just as tiles can be placed next to each other to cover a floor, rectangular images can be placed next to each other to fill (tile) a shape.</span></span> <span data-ttu-id="42a7e-104">Для мозаичного внутренней части фигуры, используйте кисть текстуры.</span><span class="sxs-lookup"><span data-stu-id="42a7e-104">To tile the interior of a shape, use a texture brush.</span></span> <span data-ttu-id="42a7e-105">При построении <xref:System.Drawing.TextureBrush> объекта, один из аргументов, передать конструктору <xref:System.Drawing.Image> объекта.</span><span class="sxs-lookup"><span data-stu-id="42a7e-105">When you construct a <xref:System.Drawing.TextureBrush> object, one of the arguments you pass to the constructor is an <xref:System.Drawing.Image> object.</span></span> <span data-ttu-id="42a7e-106">При использовании текстуры кисть для закрашивания внутренней части фигуры, фигура заполняется повторяющиеся копии этого образа.</span><span class="sxs-lookup"><span data-stu-id="42a7e-106">When you use the texture brush to paint the interior of a shape, the shape is filled with repeated copies of this image.</span></span>  
  
 <span data-ttu-id="42a7e-107">Свойство mode wrap <xref:System.Drawing.TextureBrush> определяет способ ориентации изображения при его повторяется в пределах прямоугольной сетки.</span><span class="sxs-lookup"><span data-stu-id="42a7e-107">The wrap mode property of the <xref:System.Drawing.TextureBrush> object determines how the image is oriented as it is repeated in a rectangular grid.</span></span> <span data-ttu-id="42a7e-108">Можно выполнить всего плитки отображаются в сетке же ориентацию или внесения зеркальное отображение изображения от позиции одной сетки к другому.</span><span class="sxs-lookup"><span data-stu-id="42a7e-108">You can make all the tiles in the grid have the same orientation, or you can make the image flip from one grid position to the next.</span></span> <span data-ttu-id="42a7e-109">Зеркальное отображение может быть горизонтальным, vertical или both.</span><span class="sxs-lookup"><span data-stu-id="42a7e-109">The flipping can be horizontal, vertical, or both.</span></span> <span data-ttu-id="42a7e-110">В следующих примерах демонстрируется мозаики с использованием различных типов зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="42a7e-110">The following examples demonstrate tiling with different types of flipping.</span></span>  
  
### <a name="to-tile-an-image"></a><span data-ttu-id="42a7e-111">Мозаичное заполнение изображением</span><span class="sxs-lookup"><span data-stu-id="42a7e-111">To tile an image</span></span>  
  
-   <span data-ttu-id="42a7e-112">В этом примере используется на следующем рисунке 75 × 75 для мозаичного заполнения прямоугольника размером 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="42a7e-112">This example uses the following 75×75 image to tile a 200×200 rectangle.</span></span>  
  
 <span data-ttu-id="42a7e-113">![Плитка 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")</span><span class="sxs-lookup"><span data-stu-id="42a7e-113">![Tile 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")</span></span>  
  
-   <span data-ttu-id="42a7e-114">Ниже показано, как выполняется мозаичное заполнение прямоугольника с изображением.</span><span class="sxs-lookup"><span data-stu-id="42a7e-114">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="42a7e-115">Обратите внимание, что все плитки же ориентацию; нет в зеркального отражения.</span><span class="sxs-lookup"><span data-stu-id="42a7e-115">Note that all tiles have the same orientation; there is no flipping.</span></span>  
  
 <span data-ttu-id="42a7e-116">![Плитки 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")</span><span class="sxs-lookup"><span data-stu-id="42a7e-116">![Tile 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a><span data-ttu-id="42a7e-117">Изображения по горизонтали мозаичное</span><span class="sxs-lookup"><span data-stu-id="42a7e-117">To flip an image horizontally while tiling</span></span>  
  
-   <span data-ttu-id="42a7e-118">В этом примере используется одно изображение размером 75 × 75 для заполнения прямоугольника размером 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="42a7e-118">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="42a7e-119">Режим переноса присваивается переворачивание изображения по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="42a7e-119">The wrap mode is set to flip the image horizontally.</span></span> <span data-ttu-id="42a7e-120">Ниже показано, как выполняется мозаичное заполнение прямоугольника с изображением.</span><span class="sxs-lookup"><span data-stu-id="42a7e-120">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="42a7e-121">Обратите внимание на то, что при переходе от одного элемента к другому в данной строке, является перевернуть изображение по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="42a7e-121">Note that as you move from one tile to the next in a given row, the image is flipped horizontally.</span></span>  
  
 <span data-ttu-id="42a7e-122">![Плитку 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")</span><span class="sxs-lookup"><span data-stu-id="42a7e-122">![Tile 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a><span data-ttu-id="42a7e-123">Изображения по вертикали мозаичное</span><span class="sxs-lookup"><span data-stu-id="42a7e-123">To flip an image vertically while tiling</span></span>  
  
-   <span data-ttu-id="42a7e-124">В этом примере используется одно изображение размером 75 × 75 для заполнения прямоугольника размером 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="42a7e-124">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="42a7e-125">Режим переноса присваивается переворачивание изображения по вертикали.</span><span class="sxs-lookup"><span data-stu-id="42a7e-125">The wrap mode is set to flip the image vertically.</span></span>  
  
     [!code-csharp[System.Drawing.UsingABrush#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a><span data-ttu-id="42a7e-126">Отражение изображения по горизонтали и вертикали мозаичное</span><span class="sxs-lookup"><span data-stu-id="42a7e-126">To flip an image horizontally and vertically while tiling</span></span>  
  
-   <span data-ttu-id="42a7e-127">В этом примере используется одно изображение размером 75 × 75 для мозаичного заполнения прямоугольника размером 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="42a7e-127">This example uses the same 75×75 image to tile a 200×200 rectangle.</span></span> <span data-ttu-id="42a7e-128">Режим переноса присваивается переворачивание изображения по горизонтали и вертикали.</span><span class="sxs-lookup"><span data-stu-id="42a7e-128">The wrap mode is set to flip the image both horizontally and vertically.</span></span> <span data-ttu-id="42a7e-129">Ниже показано, как выполняется мозаичное заполнение прямоугольник в изображении.</span><span class="sxs-lookup"><span data-stu-id="42a7e-129">The following illustration shows how the rectangle is tiled by the image.</span></span> <span data-ttu-id="42a7e-130">Обратите внимание, что при переходе от одного элемента к другому в данной строке, является перевернуть изображение по горизонтали, а при переходе от элемента к другому в указанном столбце, изображение отражаются по вертикали.</span><span class="sxs-lookup"><span data-stu-id="42a7e-130">Note that as you move from one tile to the next in a given row, the image is flipped horizontally, and as you move from one tile to the next in a given column, the image is flipped vertically.</span></span>  
  
 <span data-ttu-id="42a7e-131">![Плитку 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")</span><span class="sxs-lookup"><span data-stu-id="42a7e-131">![Tile 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="42a7e-132">См. также</span><span class="sxs-lookup"><span data-stu-id="42a7e-132">See also</span></span>
- [<span data-ttu-id="42a7e-133">Использование кисти для заливки фигур</span><span class="sxs-lookup"><span data-stu-id="42a7e-133">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
