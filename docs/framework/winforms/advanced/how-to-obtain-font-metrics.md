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
ms.openlocfilehash: 3cc5ee303efe6c703a61eef6c7448979b487f6bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-obtain-font-metrics"></a><span data-ttu-id="53de2-102">Практическое руководство. Получение метрик шрифтов</span><span class="sxs-lookup"><span data-stu-id="53de2-102">How to: Obtain Font Metrics</span></span>
<span data-ttu-id="53de2-103"><xref:System.Drawing.FontFamily> Класс предоставляет следующие методы для получения различных метрик для определенного семейства и стиля сочетания:</span><span class="sxs-lookup"><span data-stu-id="53de2-103">The <xref:System.Drawing.FontFamily> class provides the following methods that retrieve various metrics for a particular family/style combination:</span></span>  
  
-   <span data-ttu-id="53de2-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="53de2-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="53de2-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="53de2-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="53de2-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="53de2-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="53de2-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="53de2-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span></span>  
  
 <span data-ttu-id="53de2-108">Номера, возвращаемые этими методами, в единицах измерения конструктора, поэтому они не зависят от размера и единиц измерения конкретного <xref:System.Drawing.Font> объекта.</span><span class="sxs-lookup"><span data-stu-id="53de2-108">The numbers returned by these methods are in font design units, so they are independent of the size and units of a particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="53de2-109">На следующем рисунке различные метрики.</span><span class="sxs-lookup"><span data-stu-id="53de2-109">The following illustration shows the various metrics.</span></span>  
  
 <span data-ttu-id="53de2-110">![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/fontstext7a.png "fontstext7A")</span><span class="sxs-lookup"><span data-stu-id="53de2-110">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext7a.png "fontstext7A")</span></span>  
  
## <a name="example"></a><span data-ttu-id="53de2-111">Пример</span><span class="sxs-lookup"><span data-stu-id="53de2-111">Example</span></span>  
 <span data-ttu-id="53de2-112">В следующем примере отображаются метрики для семейства шрифтов Arial обычного стиля.</span><span class="sxs-lookup"><span data-stu-id="53de2-112">The following example displays the metrics for the regular style of the Arial font family.</span></span> <span data-ttu-id="53de2-113">Код также создает <xref:System.Drawing.Font> объекта (на основании семейства шрифтов Arial) с размером в 16 пикселей и отображаются метрики (в пикселях) для этой конкретной <xref:System.Drawing.Font> объекта.</span><span class="sxs-lookup"><span data-stu-id="53de2-113">The code also creates a <xref:System.Drawing.Font> object (based on the Arial family) with size 16 pixels and displays the metrics (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="53de2-114">Ниже показан результат выполнения примера кода.</span><span class="sxs-lookup"><span data-stu-id="53de2-114">The following illustration shows the output of the example code.</span></span>  
  
 <span data-ttu-id="53de2-115">![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/csfontstext8.png "csFontsText8")</span><span class="sxs-lookup"><span data-stu-id="53de2-115">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext8.png "csFontsText8")</span></span>  
  
 <span data-ttu-id="53de2-116">Обратите внимание, первые две строки выходных данных на предыдущем рисунке.</span><span class="sxs-lookup"><span data-stu-id="53de2-116">Note the first two lines of output in the preceding illustration.</span></span> <span data-ttu-id="53de2-117"><xref:System.Drawing.Font> Размер 16, возвращает объект и <xref:System.Drawing.FontFamily> объект возвращает максимального пробела, равный 2048.</span><span class="sxs-lookup"><span data-stu-id="53de2-117">The <xref:System.Drawing.Font> object returns a size of 16, and the <xref:System.Drawing.FontFamily> object returns an em height of 2,048.</span></span> <span data-ttu-id="53de2-118">Эти два числа (16 и 2048) являются основой для преобразования между единицах измерения конструктора и единиц (в данном случае это пиксели) <xref:System.Drawing.Font> объекта.</span><span class="sxs-lookup"><span data-stu-id="53de2-118">These two numbers (16 and 2,048) are the key to converting between font design units and the units (in this case pixels) of the <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="53de2-119">Например можно преобразовать единицах измерения конструктора Восхождение точек следующим образом:</span><span class="sxs-lookup"><span data-stu-id="53de2-119">For example, you can convert the ascent from design units to pixels as follows:</span></span>  
  
 <span data-ttu-id="53de2-120">![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/fontstext9.png "FontsText9")</span><span class="sxs-lookup"><span data-stu-id="53de2-120">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext9.png "FontsText9")</span></span>  
  
 <span data-ttu-id="53de2-121">Следующий код располагает текст по вертикали, устанавливая <xref:System.Drawing.PointF.Y%2A> данными-членом <xref:System.Drawing.PointF> объекта.</span><span class="sxs-lookup"><span data-stu-id="53de2-121">The following code positions text vertically by setting the <xref:System.Drawing.PointF.Y%2A> data member of a <xref:System.Drawing.PointF> object.</span></span> <span data-ttu-id="53de2-122">Координата y увеличивается на `font.Height` для каждой новой строки текста.</span><span class="sxs-lookup"><span data-stu-id="53de2-122">The y-coordinate is increased by `font.Height` for each new line of text.</span></span> <span data-ttu-id="53de2-123"><xref:System.Drawing.Font.Height%2A> Свойство <xref:System.Drawing.Font> объект возвращает межстрочный интервал (в пикселях) для этой конкретной <xref:System.Drawing.Font> объекта.</span><span class="sxs-lookup"><span data-stu-id="53de2-123">The <xref:System.Drawing.Font.Height%2A> property of a <xref:System.Drawing.Font> object returns the line spacing (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="53de2-124">В этом примере возвращаемое значение <xref:System.Drawing.Font.Height%2A> равно 19.</span><span class="sxs-lookup"><span data-stu-id="53de2-124">In this example, the number returned by <xref:System.Drawing.Font.Height%2A> is 19.</span></span> <span data-ttu-id="53de2-125">Обратите внимание, что это то же самое число (округляется в сторону увеличения до целого), получаемому при преобразовании метрики межстрочного интервала в пикселях.</span><span class="sxs-lookup"><span data-stu-id="53de2-125">Note that this is the same as the number (rounded up to an integer) obtained by converting the line-spacing metric to pixels.</span></span>  
  
 <span data-ttu-id="53de2-126">Обратите внимание, что (также называемые размер размер или em) не является сумма Восхождение и спуск.</span><span class="sxs-lookup"><span data-stu-id="53de2-126">Note that the em height (also called size or em size) is not the sum of the ascent and the descent.</span></span> <span data-ttu-id="53de2-127">Сумма размеров верхнего и спуск называется высота ячейки.</span><span class="sxs-lookup"><span data-stu-id="53de2-127">The sum of the ascent and the descent is called the cell height.</span></span> <span data-ttu-id="53de2-128">Высота ячейки минус внутренней начальные равно высоту максимального пробела.</span><span class="sxs-lookup"><span data-stu-id="53de2-128">The cell height minus the internal leading is equal to the em height.</span></span> <span data-ttu-id="53de2-129">Высота ячейки, а также внешних начальные равно межстрочный интервал.</span><span class="sxs-lookup"><span data-stu-id="53de2-129">The cell height plus the external leading is equal to the line spacing.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="53de2-130">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="53de2-130">Compiling the Code</span></span>  
 <span data-ttu-id="53de2-131">Предыдущий пример кода предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="53de2-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53de2-132">См. также</span><span class="sxs-lookup"><span data-stu-id="53de2-132">See Also</span></span>  
 [<span data-ttu-id="53de2-133">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="53de2-133">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="53de2-134">Работами со шрифтами и текстом</span><span class="sxs-lookup"><span data-stu-id="53de2-134">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
