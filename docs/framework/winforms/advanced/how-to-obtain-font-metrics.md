---
title: Практическое руководство. Получение метрик шрифтов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
ms.openlocfilehash: 7d7ad92199bb8a8f01290066f8ae023a14c2f9ce
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/21/2019
ms.locfileid: "67307425"
---
# <a name="how-to-obtain-font-metrics"></a><span data-ttu-id="79095-102">Практическое руководство. Получение метрик шрифтов</span><span class="sxs-lookup"><span data-stu-id="79095-102">How to: Obtain Font Metrics</span></span>
<span data-ttu-id="79095-103"><xref:System.Drawing.FontFamily> Класс предоставляет следующие методы для получения различных метрик для определенного семейства/style сочетания:</span><span class="sxs-lookup"><span data-stu-id="79095-103">The <xref:System.Drawing.FontFamily> class provides the following methods that retrieve various metrics for a particular family/style combination:</span></span>  
  
- <span data-ttu-id="79095-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="79095-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span></span>  
  
- <span data-ttu-id="79095-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="79095-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span></span>  
  
- <span data-ttu-id="79095-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="79095-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span></span>  
  
- <span data-ttu-id="79095-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="79095-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span></span>  
  
 <span data-ttu-id="79095-108">Значения, возвращаемые этими методами, в единицах конструктора, поэтому они не зависят от размера и единиц измерения конкретного <xref:System.Drawing.Font> объекта.</span><span class="sxs-lookup"><span data-stu-id="79095-108">The values returned by these methods are in font design units, so they are independent of the size and units of a particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="79095-109">На следующем рисунке показан различные метрики:</span><span class="sxs-lookup"><span data-stu-id="79095-109">The following illustration shows the various metrics:</span></span>
  
 ![Illustration of font metrics: ascent, descent, and line spacing.](./media/how-to-obtain-font-metrics/various-font-metrics.png)  
  
## <a name="example"></a><span data-ttu-id="79095-111">Пример</span><span class="sxs-lookup"><span data-stu-id="79095-111">Example</span></span>  
 <span data-ttu-id="79095-112">В следующем примере отображается метрики для семейства шрифтов Arial обычного стиля.</span><span class="sxs-lookup"><span data-stu-id="79095-112">The following example displays the metrics for the regular style of the Arial font family.</span></span> <span data-ttu-id="79095-113">Код также создает <xref:System.Drawing.Font> объект (в зависимости от семейства шрифтов Arial) с размером 16 пикселей и отображаются метрики (в пикселях) для этой конкретной <xref:System.Drawing.Font> объекта.</span><span class="sxs-lookup"><span data-stu-id="79095-113">The code also creates a <xref:System.Drawing.Font> object (based on the Arial family) with size 16 pixels and displays the metrics (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="79095-114">На следующем рисунке показан результат выполнения примера кода:</span><span class="sxs-lookup"><span data-stu-id="79095-114">The following illustration shows the output of the example code:</span></span>
  
 ![Пример выходных данных кода шрифт Arial метрик.](./media/how-to-obtain-font-metrics/example-output-code-arial-font.png)  
  
 <span data-ttu-id="79095-116">Обратите внимание, первые две строки выходных данных на предыдущем рисунке.</span><span class="sxs-lookup"><span data-stu-id="79095-116">Note the first two lines of output in the preceding illustration.</span></span> <span data-ttu-id="79095-117"><xref:System.Drawing.Font> Объект возвращает размер 16 и <xref:System.Drawing.FontFamily> объект возвращает em, равный 2048.</span><span class="sxs-lookup"><span data-stu-id="79095-117">The <xref:System.Drawing.Font> object returns a size of 16, and the <xref:System.Drawing.FontFamily> object returns an em height of 2,048.</span></span> <span data-ttu-id="79095-118">Эти два числа (16 и 2048 бит) являются основой для преобразования между единицах измерения конструктора и единиц (в данном случае это пиксели) <xref:System.Drawing.Font> объекта.</span><span class="sxs-lookup"><span data-stu-id="79095-118">These two numbers (16 and 2,048) are the key to converting between font design units and the units (in this case pixels) of the <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="79095-119">Например можно преобразовать единицах измерения конструктора верхнего выносного элемента в пиксели следующим образом:</span><span class="sxs-lookup"><span data-stu-id="79095-119">For example, you can convert the ascent from design units to pixels as follows:</span></span>  
  
 ![Формула, показывающий преобразование из единицах измерения конструктора в пикселях](./media/how-to-obtain-font-metrics/convert-font-units-example.png)  
  
 <span data-ttu-id="79095-121">Следующий код располагает текст по вертикали, задав <xref:System.Drawing.PointF.Y%2A> данными-членом <xref:System.Drawing.PointF> объекта.</span><span class="sxs-lookup"><span data-stu-id="79095-121">The following code positions text vertically by setting the <xref:System.Drawing.PointF.Y%2A> data member of a <xref:System.Drawing.PointF> object.</span></span> <span data-ttu-id="79095-122">Координата по оси y будет увеличена путем `font.Height` для каждой новой строки текста.</span><span class="sxs-lookup"><span data-stu-id="79095-122">The y-coordinate is increased by `font.Height` for each new line of text.</span></span> <span data-ttu-id="79095-123"><xref:System.Drawing.Font.Height%2A> Свойство <xref:System.Drawing.Font> объект возвращает межстрочный интервал (в пикселях) для этой конкретной <xref:System.Drawing.Font> объекта.</span><span class="sxs-lookup"><span data-stu-id="79095-123">The <xref:System.Drawing.Font.Height%2A> property of a <xref:System.Drawing.Font> object returns the line spacing (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="79095-124">В данном случае возвращаемое значение <xref:System.Drawing.Font.Height%2A> равно 19.</span><span class="sxs-lookup"><span data-stu-id="79095-124">In this example, the number returned by <xref:System.Drawing.Font.Height%2A> is 19.</span></span> <span data-ttu-id="79095-125">Обратите внимание на то, что это то же самое, как число (округленный в целое число), получаемому при преобразовании метрики межстрочного интервала в пикселях.</span><span class="sxs-lookup"><span data-stu-id="79095-125">Note that this is the same as the number (rounded up to an integer) obtained by converting the line-spacing metric to pixels.</span></span>  
  
 <span data-ttu-id="79095-126">Обратите внимание на то, что (также называемый размер эм) не равен сумме Восхождение и спуск.</span><span class="sxs-lookup"><span data-stu-id="79095-126">Note that the em height (also called size or em size) is not the sum of the ascent and the descent.</span></span> <span data-ttu-id="79095-127">Сумма размеров верхнего и спуск называется высота ячейки.</span><span class="sxs-lookup"><span data-stu-id="79095-127">The sum of the ascent and the descent is called the cell height.</span></span> <span data-ttu-id="79095-128">Высота ячейки минус внутренней начальные равно высоту максимального пробела.</span><span class="sxs-lookup"><span data-stu-id="79095-128">The cell height minus the internal leading is equal to the em height.</span></span> <span data-ttu-id="79095-129">Высота ячейки, а также внешнее межстрочное расстояние равно междустрочного интервала.</span><span class="sxs-lookup"><span data-stu-id="79095-129">The cell height plus the external leading is equal to the line spacing.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="79095-130">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="79095-130">Compiling the Code</span></span>  
 <span data-ttu-id="79095-131">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="79095-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79095-132">См. также</span><span class="sxs-lookup"><span data-stu-id="79095-132">See also</span></span>

- [<span data-ttu-id="79095-133">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="79095-133">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="79095-134">Работами со шрифтами и текстом</span><span class="sxs-lookup"><span data-stu-id="79095-134">Using Fonts and Text</span></span>](using-fonts-and-text.md)
