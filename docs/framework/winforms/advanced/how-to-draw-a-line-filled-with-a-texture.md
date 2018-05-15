---
title: Практическое руководство. Рисование линии с текстурным заполнением
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
ms.openlocfilehash: 1895c752340d8d764205b5a32b9af0861303841a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a><span data-ttu-id="605fd-102">Практическое руководство. Рисование линии с текстурным заполнением</span><span class="sxs-lookup"><span data-stu-id="605fd-102">How to: Draw a Line Filled with a Texture</span></span>
<span data-ttu-id="605fd-103">Вместо рисования линии сплошным цветом, можно нарисовать линии с текстурным заполнением.</span><span class="sxs-lookup"><span data-stu-id="605fd-103">Instead of drawing a line with a solid color, you can draw a line with a texture.</span></span> <span data-ttu-id="605fd-104">Рисование линий и кривых с текстурным заполнением, создайте <xref:System.Drawing.TextureBrush> и передать, <xref:System.Drawing.TextureBrush> объект <xref:System.Drawing.Pen.%23ctor%2A> конструктор.</span><span class="sxs-lookup"><span data-stu-id="605fd-104">To draw lines and curves with a texture, create a <xref:System.Drawing.TextureBrush> object, and pass that <xref:System.Drawing.TextureBrush> object to a <xref:System.Drawing.Pen.%23ctor%2A> constructor.</span></span> <span data-ttu-id="605fd-105">Растровое изображение, связанное с кистью текстуры используется для мозаичного плоскости (незаметно), и когда перо рисует линию или кривую, соответствующие пиксели мозаичную текстуру пера, становятся видимыми.</span><span class="sxs-lookup"><span data-stu-id="605fd-105">The bitmap associated with the texture brush is used to tile the plane (invisibly), and when the pen draws a line or curve, the stroke of the pen uncovers certain pixels of the tiled texture.</span></span>  
  
## <a name="example"></a><span data-ttu-id="605fd-106">Пример</span><span class="sxs-lookup"><span data-stu-id="605fd-106">Example</span></span>  
 <span data-ttu-id="605fd-107">В следующем примере создается <xref:System.Drawing.Bitmap> объекта из файла `Texture1.jpg`.</span><span class="sxs-lookup"><span data-stu-id="605fd-107">The following example creates a <xref:System.Drawing.Bitmap> object from the file `Texture1.jpg`.</span></span> <span data-ttu-id="605fd-108">Это растровое изображение используется для создания <xref:System.Drawing.TextureBrush> объекта и <xref:System.Drawing.TextureBrush> объект используется для создания <xref:System.Drawing.Pen> объекта.</span><span class="sxs-lookup"><span data-stu-id="605fd-108">That bitmap is used to construct a <xref:System.Drawing.TextureBrush> object, and the <xref:System.Drawing.TextureBrush> object is used to construct a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="605fd-109">Вызов метода <xref:System.Drawing.Graphics.DrawImage%2A> рисуется растровое изображение с его верхнего левого угла на (0, 0).</span><span class="sxs-lookup"><span data-stu-id="605fd-109">The call to <xref:System.Drawing.Graphics.DrawImage%2A> draws the bitmap with its upper-left corner at (0, 0).</span></span> <span data-ttu-id="605fd-110">Вызов <xref:System.Drawing.Graphics.DrawEllipse%2A> использует <xref:System.Drawing.Pen> объекта, чтобы нарисовать эллипс текстуры.</span><span class="sxs-lookup"><span data-stu-id="605fd-110">The call to <xref:System.Drawing.Graphics.DrawEllipse%2A> uses the <xref:System.Drawing.Pen> object to draw a textured ellipse.</span></span>  
  
 <span data-ttu-id="605fd-111">Точечный рисунок и текстуры эллипс на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="605fd-111">The following illustration shows the bitmap and the textured ellipse.</span></span>  
  
 <span data-ttu-id="605fd-112">![Перья](../../../../docs/framework/winforms/advanced/media/pens7.png "pens7")</span><span class="sxs-lookup"><span data-stu-id="605fd-112">![Pens](../../../../docs/framework/winforms/advanced/media/pens7.png "pens7")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="605fd-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="605fd-113">Compiling the Code</span></span>  
 <span data-ttu-id="605fd-114">Создайте форму Windows Form и обработки формы <xref:System.Windows.Forms.Control.Paint> событий.</span><span class="sxs-lookup"><span data-stu-id="605fd-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="605fd-115">Вставьте приведенный выше код в <xref:System.Windows.Forms.Control.Paint> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="605fd-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="605fd-116">Замените `Texture.jpg` с изображением в вашей системе.</span><span class="sxs-lookup"><span data-stu-id="605fd-116">Replace `Texture.jpg` with an image valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="605fd-117">См. также</span><span class="sxs-lookup"><span data-stu-id="605fd-117">See Also</span></span>  
 [<span data-ttu-id="605fd-118">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="605fd-118">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="605fd-119">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="605fd-119">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
