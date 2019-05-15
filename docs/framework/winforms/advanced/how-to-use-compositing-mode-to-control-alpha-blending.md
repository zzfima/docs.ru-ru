---
title: Практическое руководство. Использование режима комбинирования для управления альфа-смешением
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
ms.openlocfilehash: 6863e59efa25323f80933bf8ab595316b430ef53
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65590139"
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a><span data-ttu-id="917f2-102">Практическое руководство. Использование режима комбинирования для управления альфа-смешением</span><span class="sxs-lookup"><span data-stu-id="917f2-102">How to: Use Compositing Mode to Control Alpha Blending</span></span>
<span data-ttu-id="917f2-103">Могут возникнуть ситуации, когда нужно создать в битовом изображении, который имеет следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="917f2-103">There may be times when you want to create an off-screen bitmap that has the following characteristics:</span></span>  
  
- <span data-ttu-id="917f2-104">Цвета имеют альфа-значения, которые меньше 255.</span><span class="sxs-lookup"><span data-stu-id="917f2-104">Colors have alpha values that are less than 255.</span></span>  
  
- <span data-ttu-id="917f2-105">Не выполняется альфа-смешение цветов друг с другом при создании точечного рисунка.</span><span class="sxs-lookup"><span data-stu-id="917f2-105">Colors are not alpha blended with each other as you create the bitmap.</span></span>  
  
- <span data-ttu-id="917f2-106">При отображении завершения растрового изображения, цвета в битовой карте, альфа-смешением с фоновыми цветами на устройстве отображения.</span><span class="sxs-lookup"><span data-stu-id="917f2-106">When you display the finished bitmap, colors in the bitmap are alpha blended with the background colors on the display device.</span></span>  
  
 <span data-ttu-id="917f2-107">Чтобы создать такой точечный рисунок, создайте пустой <xref:System.Drawing.Bitmap> объекта, а затем постройте <xref:System.Drawing.Graphics> на его основе объект.</span><span class="sxs-lookup"><span data-stu-id="917f2-107">To create such a bitmap, construct a blank <xref:System.Drawing.Bitmap> object, and then construct a <xref:System.Drawing.Graphics> object based on that bitmap.</span></span> <span data-ttu-id="917f2-108">Установка режима комбинирования для <xref:System.Drawing.Graphics> объект <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="917f2-108">Set the compositing mode of the <xref:System.Drawing.Graphics> object to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="917f2-109">Пример</span><span class="sxs-lookup"><span data-stu-id="917f2-109">Example</span></span>  
 <span data-ttu-id="917f2-110">В следующем примере создается <xref:System.Drawing.Graphics> на основе <xref:System.Drawing.Bitmap> объекта.</span><span class="sxs-lookup"><span data-stu-id="917f2-110">The following example creates a <xref:System.Drawing.Graphics> object based on a <xref:System.Drawing.Bitmap> object.</span></span> <span data-ttu-id="917f2-111">Код использует <xref:System.Drawing.Graphics> вместе с двумя полупрозрачными кистями (альфа-канал = 160) для рисования изображения на точечный рисунок.</span><span class="sxs-lookup"><span data-stu-id="917f2-111">The code uses the <xref:System.Drawing.Graphics> object along with two semitransparent brushes (alpha = 160) to paint on the bitmap.</span></span> <span data-ttu-id="917f2-112">Код заполняет красного и зеленого эллипса, с помощью полупрозрачными кистями.</span><span class="sxs-lookup"><span data-stu-id="917f2-112">The code fills a red ellipse and a green ellipse using the semitransparent brushes.</span></span> <span data-ttu-id="917f2-113">Зеленый эллипс перекрывается красным эллипсом, но зеленый и красный значок не смешиваются, потому что режим комбинирования <xref:System.Drawing.Graphics> имеет значение <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.</span><span class="sxs-lookup"><span data-stu-id="917f2-113">The green ellipse overlaps the red ellipse, but the green is not blended with the red because the compositing mode of the <xref:System.Drawing.Graphics> object is set to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.</span></span>  
  
 <span data-ttu-id="917f2-114">Точечный рисунок рисуется на экране дважды: один раз на белом фоне и один раз на многоцветном фоне.</span><span class="sxs-lookup"><span data-stu-id="917f2-114">The code draws the bitmap on the screen twice: once on a white background and once on a multicolored background.</span></span> <span data-ttu-id="917f2-115">Пиксели растрового изображения, которые являются частью двух эллипсов имеют альфа-составляющей 160, поэтому многоточие смешиваются с фоновыми цветами на экране.</span><span class="sxs-lookup"><span data-stu-id="917f2-115">The pixels in the bitmap that are part of the two ellipses have an alpha component of 160, so the ellipses are blended with the background colors on the screen.</span></span>  
  
 <span data-ttu-id="917f2-116">Ниже показаны выходные данные примера кода.</span><span class="sxs-lookup"><span data-stu-id="917f2-116">The following illustration shows the output of the code example.</span></span> <span data-ttu-id="917f2-117">Обратите внимание, что многоточие смешиваются с фоном, но не смешиваются друг с другом.</span><span class="sxs-lookup"><span data-stu-id="917f2-117">Note that the ellipses are blended with the background, but they are not blended with each other.</span></span>  
  
 ![Схема отображение многоточие смешением с фоном, не друг с другом.](./media/how-to-use-compositing-mode-to-control-alpha-blending/ellipses-blended-background.png)  
  
 <span data-ttu-id="917f2-119">В примере кода содержит следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="917f2-119">The code example contains this statement:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 <span data-ttu-id="917f2-120">Если требуется многоточие смешивались друг с другом, а также с фоном, измените этот оператор следующим:</span><span class="sxs-lookup"><span data-stu-id="917f2-120">If you want the ellipses to be blended with each other as well as with the background, change that statement to the following:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 <span data-ttu-id="917f2-121">Ниже показан результат выполнения обновленного кода.</span><span class="sxs-lookup"><span data-stu-id="917f2-121">The following illustration shows the output of the revised code.</span></span>  
  
 ![Схема, показывающая многоточие смешением друг с другом и с фоном.](./media/how-to-use-compositing-mode-to-control-alpha-blending/blend-ellipses-background.png)  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="917f2-123">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="917f2-123">Compiling the Code</span></span>  
 <span data-ttu-id="917f2-124">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="917f2-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="917f2-125">См. также</span><span class="sxs-lookup"><span data-stu-id="917f2-125">See also</span></span>

- <xref:System.Drawing.Color.FromArgb%2A>
- [<span data-ttu-id="917f2-126">Альфа-смешение цвета для линий и заливок</span><span class="sxs-lookup"><span data-stu-id="917f2-126">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
