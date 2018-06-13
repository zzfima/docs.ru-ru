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
# <a name="how-to-tile-a-shape-with-an-image"></a>Практическое руководство. Мозаичное заполнение фигуры заданным изображением
Аналогично плитки можно поместить рядом друг с другом пола, чтобы заполнить фигуру прямоугольные изображения можно поместить рядом друг с другом. Для мозаичного заполнения внутренней области фигуры, используйте кисти текстуры. При построении <xref:System.Drawing.TextureBrush> объекта, один из аргументов, можно передать конструктору <xref:System.Drawing.Image> объекта. При использовании кисти текстуры для рисования внутренней части фигуры заполнение повторяющиеся копии изображения.  
  
 Свойства режима переноса <xref:System.Drawing.TextureBrush> определяет способ ориентации изображения при повторяется в прямоугольной сетки. Можно выполнить прислали плитки в сетке ту же ориентацию, или чтобы зеркальное отображение изображения от позиции одной сетки к другому. Зеркальное отображение может быть горизонтальным, по вертикали или оба. В следующих примерах демонстрируется мозаичное заполнение с использованием различных типов зеркального отображения.  
  
### <a name="to-tile-an-image"></a>Мозаичное заполнение изображением  
  
-   В этом примере используется на следующем рисунке 75 × 75 для мозаичного заполнения прямоугольника размером 200 × 200.  
  
 ![Плитки 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")  
  
-   Ниже показано, как выполняется мозаичное заполнение прямоугольника с изображением. Обратите внимание, что все плитки ту же ориентацию; не существует зеркального отображения.  
  
 ![Плитки 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")  
  
 [!code-csharp[System.Drawing.UsingABrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a>Отражение изображения по горизонтали при мозаичное заполнение  
  
-   В этом примере используется одно изображение размером 75 × 75 для заполнения прямоугольника размером 200 × 200. Режим переноса равно отражение изображения по горизонтали. Ниже показано, как выполняется мозаичное заполнение прямоугольника с изображением. Обратите внимание, что при переходе от одного элемента к другому в данной строке сетки изображение зеркально отображается по горизонтали.  
  
 ![Плитки 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")  
  
 [!code-csharp[System.Drawing.UsingABrush#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a>Отражение изображения по вертикали при мозаичное заполнение  
  
-   В этом примере используется одно изображение размером 75 × 75 для заполнения прямоугольника размером 200 × 200. Режим переноса равно отражение изображения по вертикали.  
  
     [!code-csharp[System.Drawing.UsingABrush#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a>Отражение изображения по горизонтали и вертикали мозаичное  
  
-   В этом примере используется одно изображение размером 75 × 75 для мозаичного заполнения прямоугольника размером 200 × 200. Режим переноса равно зеркальное отражение изображения по горизонтали и вертикали. Ниже показано, как выполняется мозаичное заполнение прямоугольник в изображении. Обратите внимание, что при переходе от одного элемента к другому в данной строке сетки изображение зеркально отображается по горизонтали, а при переходе от одного элемента к элементу в заданном столбце изображение перевернута вертикально.  
  
 ![Плитки 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")  
  
 [!code-csharp[System.Drawing.UsingABrush#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>См. также  
 [Использование кисти для заливки фигур](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
