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
ms.openlocfilehash: 55c6db1029c6823652ac29fca46f6f8dc4ec40d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a><span data-ttu-id="05e2b-102">Практическое руководство. Использование режима комбинирования для управления альфа-смешением</span><span class="sxs-lookup"><span data-stu-id="05e2b-102">How to: Use Compositing Mode to Control Alpha Blending</span></span>
<span data-ttu-id="05e2b-103">Могут возникнуть ситуации, когда требуется создать в битовом изображении, который имеет следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="05e2b-103">There may be times when you want to create an off-screen bitmap that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="05e2b-104">Цвета имеет альфа-значения, которые меньше 255.</span><span class="sxs-lookup"><span data-stu-id="05e2b-104">Colors have alpha values that are less than 255.</span></span>  
  
-   <span data-ttu-id="05e2b-105">Не выполняется альфа-смешение цветов друг с другом, как создать точечный рисунок.</span><span class="sxs-lookup"><span data-stu-id="05e2b-105">Colors are not alpha blended with each other as you create the bitmap.</span></span>  
  
-   <span data-ttu-id="05e2b-106">При отображении готовой растрового изображения, цвета в битовой карте, альфа-смешение цвета фона на устройстве отображения.</span><span class="sxs-lookup"><span data-stu-id="05e2b-106">When you display the finished bitmap, colors in the bitmap are alpha blended with the background colors on the display device.</span></span>  
  
 <span data-ttu-id="05e2b-107">Чтобы создать такой точечный рисунок, создать пустой <xref:System.Drawing.Bitmap> объекта, а затем постройте <xref:System.Drawing.Graphics> объекта на его основе.</span><span class="sxs-lookup"><span data-stu-id="05e2b-107">To create such a bitmap, construct a blank <xref:System.Drawing.Bitmap> object, and then construct a <xref:System.Drawing.Graphics> object based on that bitmap.</span></span> <span data-ttu-id="05e2b-108">Установите режим композиции <xref:System.Drawing.Graphics> объект <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="05e2b-108">Set the compositing mode of the <xref:System.Drawing.Graphics> object to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05e2b-109">Пример</span><span class="sxs-lookup"><span data-stu-id="05e2b-109">Example</span></span>  
 <span data-ttu-id="05e2b-110">В следующем примере создается <xref:System.Drawing.Graphics> объекта, основанного на <xref:System.Drawing.Bitmap> объекта.</span><span class="sxs-lookup"><span data-stu-id="05e2b-110">The following example creates a <xref:System.Drawing.Graphics> object based on a <xref:System.Drawing.Bitmap> object.</span></span> <span data-ttu-id="05e2b-111">Код использует <xref:System.Drawing.Graphics> вместе с двумя полупрозрачными кистями (альфа = 160) для рисования растрового изображения.</span><span class="sxs-lookup"><span data-stu-id="05e2b-111">The code uses the <xref:System.Drawing.Graphics> object along with two semitransparent brushes (alpha = 160) to paint on the bitmap.</span></span> <span data-ttu-id="05e2b-112">В коде осуществляется заливка красного и зеленого эллипсов, с помощью полупрозрачными кистями.</span><span class="sxs-lookup"><span data-stu-id="05e2b-112">The code fills a red ellipse and a green ellipse using the semitransparent brushes.</span></span> <span data-ttu-id="05e2b-113">Зеленый эллипс частично перекрывается с красным эллипсом, но зеленый и красный значок не смешиваются, потому что режим комбинирования <xref:System.Drawing.Graphics> , присваивается значение <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.</span><span class="sxs-lookup"><span data-stu-id="05e2b-113">The green ellipse overlaps the red ellipse, but the green is not blended with the red because the compositing mode of the <xref:System.Drawing.Graphics> object is set to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.</span></span>  
  
 <span data-ttu-id="05e2b-114">Точечный рисунок рисуется на экране дважды: один раз на белом фоне и один раз на многоцветном фоне.</span><span class="sxs-lookup"><span data-stu-id="05e2b-114">The code draws the bitmap on the screen twice: once on a white background and once on a multicolored background.</span></span> <span data-ttu-id="05e2b-115">Точки в битовой карте, являющиеся частью двух эллипсов имеют альфа-компонент, равный 160, поэтому цвета эллипсов смешиваются с фоновыми цветами на экране.</span><span class="sxs-lookup"><span data-stu-id="05e2b-115">The pixels in the bitmap that are part of the two ellipses have an alpha component of 160, so the ellipses are blended with the background colors on the screen.</span></span>  
  
 <span data-ttu-id="05e2b-116">Ниже показан результат выполнения примера кода.</span><span class="sxs-lookup"><span data-stu-id="05e2b-116">The following illustration shows the output of the code example.</span></span> <span data-ttu-id="05e2b-117">Обратите внимание, что цвета эллипсов смешиваются с фоном, но не смешиваются друг с другом.</span><span class="sxs-lookup"><span data-stu-id="05e2b-117">Note that the ellipses are blended with the background, but they are not blended with each other.</span></span>  
  
 <span data-ttu-id="05e2b-118">![Источник копирования](../../../../docs/framework/winforms/advanced/media/sourcecopy.png "sourcecopy")</span><span class="sxs-lookup"><span data-stu-id="05e2b-118">![Source Copy](../../../../docs/framework/winforms/advanced/media/sourcecopy.png "sourcecopy")</span></span>  
  
 <span data-ttu-id="05e2b-119">Пример кода содержит следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="05e2b-119">The code example contains this statement:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 <span data-ttu-id="05e2b-120">Если требуется эллипсов смешивались друг с другом, а также с цветом фона, измените этот оператор следующим образом:</span><span class="sxs-lookup"><span data-stu-id="05e2b-120">If you want the ellipses to be blended with each other as well as with the background, change that statement to the following:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 <span data-ttu-id="05e2b-121">Ниже показан результат выполнения измененного кода.</span><span class="sxs-lookup"><span data-stu-id="05e2b-121">The following illustration shows the output of the revised code.</span></span>  
  
 <span data-ttu-id="05e2b-122">![Источник над](../../../../docs/framework/winforms/advanced/media/sourceover.png "sourceover")</span><span class="sxs-lookup"><span data-stu-id="05e2b-122">![Source Over](../../../../docs/framework/winforms/advanced/media/sourceover.png "sourceover")</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="05e2b-123">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="05e2b-123">Compiling the Code</span></span>  
 <span data-ttu-id="05e2b-124">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="05e2b-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05e2b-125">См. также</span><span class="sxs-lookup"><span data-stu-id="05e2b-125">See Also</span></span>  
 <xref:System.Drawing.Color.FromArgb%2A>  
 [<span data-ttu-id="05e2b-126">Альфа-смешение цвета для линий и заливок</span><span class="sxs-lookup"><span data-stu-id="05e2b-126">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
