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
ms.openlocfilehash: a906db44a548361df2822efa24d1dd1849cb5a24
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063736"
---
# <a name="how-to-tile-a-shape-with-an-image"></a><span data-ttu-id="bf51a-102">Практическое руководство. Мозаичное заполнение фигуры заданным изображением</span><span class="sxs-lookup"><span data-stu-id="bf51a-102">How to: Tile a Shape with an Image</span></span>
<span data-ttu-id="bf51a-103">Так же, как плиток можно поместить рядом друг с другом пола, прямоугольные изображения можно поместить рядом друг с другом заполнить фигуру.</span><span class="sxs-lookup"><span data-stu-id="bf51a-103">Just as tiles can be placed next to each other to cover a floor, rectangular images can be placed next to each other to fill (tile) a shape.</span></span> <span data-ttu-id="bf51a-104">Для мозаичного внутренней части фигуры, используйте кисть текстуры.</span><span class="sxs-lookup"><span data-stu-id="bf51a-104">To tile the interior of a shape, use a texture brush.</span></span> <span data-ttu-id="bf51a-105">При построении <xref:System.Drawing.TextureBrush> объекта, один из аргументов, передать конструктору <xref:System.Drawing.Image> объекта.</span><span class="sxs-lookup"><span data-stu-id="bf51a-105">When you construct a <xref:System.Drawing.TextureBrush> object, one of the arguments you pass to the constructor is an <xref:System.Drawing.Image> object.</span></span> <span data-ttu-id="bf51a-106">При использовании текстуры кисть для закрашивания внутренней части фигуры, фигура заполняется повторяющиеся копии этого образа.</span><span class="sxs-lookup"><span data-stu-id="bf51a-106">When you use the texture brush to paint the interior of a shape, the shape is filled with repeated copies of this image.</span></span>  
  
 <span data-ttu-id="bf51a-107">Свойство mode wrap <xref:System.Drawing.TextureBrush> определяет способ ориентации изображения при его повторяется в пределах прямоугольной сетки.</span><span class="sxs-lookup"><span data-stu-id="bf51a-107">The wrap mode property of the <xref:System.Drawing.TextureBrush> object determines how the image is oriented as it is repeated in a rectangular grid.</span></span> <span data-ttu-id="bf51a-108">Можно выполнить всего плитки отображаются в сетке же ориентацию или внесения зеркальное отображение изображения от позиции одной сетки к другому.</span><span class="sxs-lookup"><span data-stu-id="bf51a-108">You can make all the tiles in the grid have the same orientation, or you can make the image flip from one grid position to the next.</span></span> <span data-ttu-id="bf51a-109">Зеркальное отображение может быть горизонтальным, vertical или both.</span><span class="sxs-lookup"><span data-stu-id="bf51a-109">The flipping can be horizontal, vertical, or both.</span></span> <span data-ttu-id="bf51a-110">В следующих примерах демонстрируется мозаики с использованием различных типов зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="bf51a-110">The following examples demonstrate tiling with different types of flipping.</span></span>  
  
### <a name="to-tile-an-image"></a><span data-ttu-id="bf51a-111">Мозаичное заполнение изображением</span><span class="sxs-lookup"><span data-stu-id="bf51a-111">To tile an image</span></span>  
  
- <span data-ttu-id="bf51a-112">В этом примере используется на следующем рисунке 75 × 75 для мозаичного заполнения прямоугольника размером 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="bf51a-112">This example uses the following 75×75 image to tile a 200×200 rectangle.</span></span>  
  
 ![Изображение плитки, отображаются красным дома и дерева.](./media/how-to-tile-a-shape-with-an-image/rectangle-tile-200x200.gif)  
  
- <span data-ttu-id="bf51a-114">Ниже показано, как выполняется мозаичное заполнение прямоугольника с изображением.</span><span class="sxs-lookup"><span data-stu-id="bf51a-114">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="bf51a-115">Обратите внимание, что все плитки же ориентацию; нет в зеркального отражения.</span><span class="sxs-lookup"><span data-stu-id="bf51a-115">Note that all tiles have the same orientation; there is no flipping.</span></span>  
  
 ![Прямоугольника мозаикой заливка, выполненная с помощью образа, используя ту же ориентацию для всех элементов мозаики.](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-no-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a><span data-ttu-id="bf51a-117">Изображения по горизонтали мозаичное</span><span class="sxs-lookup"><span data-stu-id="bf51a-117">To flip an image horizontally while tiling</span></span>  
  
- <span data-ttu-id="bf51a-118">В этом примере используется одно изображение размером 75 × 75 для заполнения прямоугольника размером 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="bf51a-118">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="bf51a-119">Режим переноса присваивается переворачивание изображения по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="bf51a-119">The wrap mode is set to flip the image horizontally.</span></span> <span data-ttu-id="bf51a-120">Ниже показано, как выполняется мозаичное заполнение прямоугольника с изображением.</span><span class="sxs-lookup"><span data-stu-id="bf51a-120">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="bf51a-121">Обратите внимание на то, что при переходе от одного элемента к другому в данной строке, является перевернуть изображение по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="bf51a-121">Note that as you move from one tile to the next in a given row, the image is flipped horizontally.</span></span>  
  
 ![Прямоугольника мозаикой заливка, выполненная с помощью образа, отражаются по горизонтали.](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a><span data-ttu-id="bf51a-123">Изображения по вертикали мозаичное</span><span class="sxs-lookup"><span data-stu-id="bf51a-123">To flip an image vertically while tiling</span></span>  
  
- <span data-ttu-id="bf51a-124">В этом примере используется одно изображение размером 75 × 75 для заполнения прямоугольника размером 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="bf51a-124">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="bf51a-125">Режим переноса присваивается переворачивание изображения по вертикали.</span><span class="sxs-lookup"><span data-stu-id="bf51a-125">The wrap mode is set to flip the image vertically.</span></span>  
  
     [!code-csharp[System.Drawing.UsingABrush#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a><span data-ttu-id="bf51a-126">Отражение изображения по горизонтали и вертикали мозаичное</span><span class="sxs-lookup"><span data-stu-id="bf51a-126">To flip an image horizontally and vertically while tiling</span></span>  
  
- <span data-ttu-id="bf51a-127">В этом примере используется одно изображение размером 75 × 75 для мозаичного заполнения прямоугольника размером 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="bf51a-127">This example uses the same 75×75 image to tile a 200×200 rectangle.</span></span> <span data-ttu-id="bf51a-128">Режим переноса присваивается переворачивание изображения по горизонтали и вертикали.</span><span class="sxs-lookup"><span data-stu-id="bf51a-128">The wrap mode is set to flip the image both horizontally and vertically.</span></span> <span data-ttu-id="bf51a-129">Ниже показано, как выполняется мозаичное заполнение прямоугольник в изображении.</span><span class="sxs-lookup"><span data-stu-id="bf51a-129">The following illustration shows how the rectangle is tiled by the image.</span></span> <span data-ttu-id="bf51a-130">Обратите внимание, что при переходе от одного элемента к другому в данной строке, является перевернуть изображение по горизонтали, а при переходе от элемента к другому в указанном столбце, изображение отражаются по вертикали.</span><span class="sxs-lookup"><span data-stu-id="bf51a-130">Note that as you move from one tile to the next in a given row, the image is flipped horizontally, and as you move from one tile to the next in a given column, the image is flipped vertically.</span></span>  
  
 ![Прямоугольника мозаикой заливка, выполненная с изображением перевернуто по горизонтали и вертикали.](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-vertical-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="bf51a-132">См. также</span><span class="sxs-lookup"><span data-stu-id="bf51a-132">See also</span></span>

- [<span data-ttu-id="bf51a-133">Использование кисти для заливки фигур</span><span class="sxs-lookup"><span data-stu-id="bf51a-133">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
