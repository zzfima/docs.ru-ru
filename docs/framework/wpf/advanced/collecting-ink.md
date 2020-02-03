---
title: Получение цифрового рукописного ввода
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], collecting
- InkCanvas element [WPF]
- properties [WPF], DrawingAttributes
- collecting digital ink [WPF]
- digital ink [WPF], collecting
- properties [WPF], DefaultDrawingAttributes
- DefaultDrawingAttributes property [WPF]
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
ms.openlocfilehash: 813a5313a6fbf83c36cdbed1f64ce69a217ad788
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747024"
---
# <a name="collect-ink"></a><span data-ttu-id="cf774-102">Собирайте рукописные данные</span><span class="sxs-lookup"><span data-stu-id="cf774-102">Collect Ink</span></span>

<span data-ttu-id="cf774-103">Платформа [Windows Presentation Foundation](../index.md) выполняет сбор цифровых рукописных фрагментов, что является одной из основных ее функций.</span><span class="sxs-lookup"><span data-stu-id="cf774-103">The [Windows Presentation Foundation](../index.md) platform collects digital ink as a core part of its functionality.</span></span> <span data-ttu-id="cf774-104">В этом разделе обсуждаются методы сбора рукописного ввода в Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="cf774-104">This topic discusses methods for collection of ink in Windows Presentation Foundation (WPF).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cf774-105">предварительные требования</span><span class="sxs-lookup"><span data-stu-id="cf774-105">Prerequisites</span></span>

<span data-ttu-id="cf774-106">Чтобы использовать следующие примеры, необходимо сначала установить Visual Studio и Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="cf774-106">To use the following examples, you must first install Visual Studio and the Windows SDK.</span></span> <span data-ttu-id="cf774-107">Следует также понимать, как писать приложения для WPF.</span><span class="sxs-lookup"><span data-stu-id="cf774-107">You should also understand how to write applications for the WPF.</span></span> <span data-ttu-id="cf774-108">Дополнительные сведения о начале работы с WPF см. в разделе [Пошаговое руководство. мое первое классическое приложение WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="cf774-108">For more information about getting started with WPF, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="use-the-inkcanvas-element"></a><span data-ttu-id="cf774-109">Использование элемента InkCanvas</span><span class="sxs-lookup"><span data-stu-id="cf774-109">Use the InkCanvas Element</span></span>

<span data-ttu-id="cf774-110">Элемент <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> предоставляет самый простой способ собираются рукописный ввод в WPF.</span><span class="sxs-lookup"><span data-stu-id="cf774-110">The <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> element provides the easiest way to collect ink in WPF.</span></span> <span data-ttu-id="cf774-111">Используйте элемент <xref:System.Windows.Controls.InkCanvas> для получения и вывода рукописных данных.</span><span class="sxs-lookup"><span data-stu-id="cf774-111">Use an <xref:System.Windows.Controls.InkCanvas> element to receive and display ink input.</span></span> <span data-ttu-id="cf774-112">Рукописный ввод, как правило, осуществляется с помощью пера, которое взаимодействует с дигитайзером для создания рукописных штрихов.</span><span class="sxs-lookup"><span data-stu-id="cf774-112">You commonly input ink through the use of a stylus, which interacts with a digitizer to produce ink strokes.</span></span> <span data-ttu-id="cf774-113">Кроме того, вместо пера можно использовать мышь.</span><span class="sxs-lookup"><span data-stu-id="cf774-113">In addition, a mouse can be used in place of a stylus.</span></span> <span data-ttu-id="cf774-114">Созданные штрихи представляются как <xref:System.Windows.Ink.Stroke> объекты, и их можно манипулировать как программно, так и с помощью пользовательского ввода.</span><span class="sxs-lookup"><span data-stu-id="cf774-114">The created strokes are represented as <xref:System.Windows.Ink.Stroke> objects, and they can be manipulated both programmatically and by user input.</span></span> <span data-ttu-id="cf774-115"><xref:System.Windows.Controls.InkCanvas> позволяет пользователям выбирать, изменять или удалять существующие <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="cf774-115">The <xref:System.Windows.Controls.InkCanvas> enables users to select, modify, or delete an existing <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="cf774-116">С помощью XAML можно настроить сбор рукописных данных так же легко, как добавить элемент **InkCanvas** в дерево.</span><span class="sxs-lookup"><span data-stu-id="cf774-116">By using XAML, you can set up ink collection as easily as adding an **InkCanvas** element to your tree.</span></span> <span data-ttu-id="cf774-117">В следующем примере добавляется <xref:System.Windows.Controls.InkCanvas> в проект WPF по умолчанию, созданный в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cf774-117">The following example adds an <xref:System.Windows.Controls.InkCanvas> to a default WPF project created in Visual Studio:</span></span>

[!code-xaml[DigitalInkTopics#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

<span data-ttu-id="cf774-118">Элемент **InkCanvas** также может содержать дочерние элементы, что позволяет добавлять возможности рукописных заметок практически к любому типу элемента XAML.</span><span class="sxs-lookup"><span data-stu-id="cf774-118">The **InkCanvas** element can also contain child elements, making it possible to add ink annotation capabilities to almost any type of XAML element.</span></span> <span data-ttu-id="cf774-119">Например, чтобы добавить возможности рукописного ввода в текстовый элемент, просто сделайте его дочерним элементом <xref:System.Windows.Controls.InkCanvas>:</span><span class="sxs-lookup"><span data-stu-id="cf774-119">For example, to add inking capabilities to a text element, simply make it a child of an <xref:System.Windows.Controls.InkCanvas>:</span></span>

[!code-xaml[DigitalInkTopics#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

<span data-ttu-id="cf774-120">Добавление поддержки пометки изображения с помощью рукописного ввода — это так же просто:</span><span class="sxs-lookup"><span data-stu-id="cf774-120">Adding support for marking up an image with ink is just as easy:</span></span>

[!code-xaml[DigitalInkTopics#7](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a><span data-ttu-id="cf774-121">Режимы InkCollection</span><span class="sxs-lookup"><span data-stu-id="cf774-121">InkCollection Modes</span></span>

<span data-ttu-id="cf774-122"><xref:System.Windows.Controls.InkCanvas> обеспечивает поддержку различных режимов ввода с помощью свойства <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="cf774-122">The <xref:System.Windows.Controls.InkCanvas> provides support for various input modes through its <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> property.</span></span>

### <a name="manipulate-ink"></a><span data-ttu-id="cf774-123">Работа с рукописными данными</span><span class="sxs-lookup"><span data-stu-id="cf774-123">Manipulate Ink</span></span>

<span data-ttu-id="cf774-124"><xref:System.Windows.Controls.InkCanvas> обеспечивает поддержку многих операций редактирования рукописных данных.</span><span class="sxs-lookup"><span data-stu-id="cf774-124">The <xref:System.Windows.Controls.InkCanvas> provides support for many ink editing operations.</span></span> <span data-ttu-id="cf774-125">Например, <xref:System.Windows.Controls.InkCanvas> поддерживает стирание в обратном пера, а дополнительный код не требуется для добавления функциональности в элемент.</span><span class="sxs-lookup"><span data-stu-id="cf774-125">For example, <xref:System.Windows.Controls.InkCanvas> supports back-of-pen erase, and no additional code is needed to add the functionality to the element.</span></span>

#### <a name="selection"></a><span data-ttu-id="cf774-126">Выбор</span><span class="sxs-lookup"><span data-stu-id="cf774-126">Selection</span></span>

<span data-ttu-id="cf774-127">Настройка режима выделения так же проста, как установка свойства <xref:System.Windows.Controls.InkCanvasEditingMode> для **выбора**.</span><span class="sxs-lookup"><span data-stu-id="cf774-127">Setting selection mode is as simple as setting the <xref:System.Windows.Controls.InkCanvasEditingMode> property to **Select**.</span></span>

<span data-ttu-id="cf774-128">Следующий код задает режим редактирования на основе значения <xref:System.Windows.Forms.CheckBox>:</span><span class="sxs-lookup"><span data-stu-id="cf774-128">The following code sets the editing mode based on the value of a <xref:System.Windows.Forms.CheckBox>:</span></span>

[!code-csharp[DigitalInkTopics#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a><span data-ttu-id="cf774-129">DrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="cf774-129">DrawingAttributes</span></span>

<span data-ttu-id="cf774-130">Используйте свойство <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A>, чтобы изменить внешний вид рукописных штрихов.</span><span class="sxs-lookup"><span data-stu-id="cf774-130">Use the <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> property to change the appearance of ink strokes.</span></span> <span data-ttu-id="cf774-131">Например, элемент <xref:System.Windows.Ink.DrawingAttributes.Color%2A> <xref:System.Windows.Ink.DrawingAttributes> задает цвет отображаемого <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="cf774-131">For instance, the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> member of <xref:System.Windows.Ink.DrawingAttributes> sets the color of the rendered <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="cf774-132">В следующем примере цвет выбранных штрихов меняется на красный:</span><span class="sxs-lookup"><span data-stu-id="cf774-132">The following example changes the color of the selected strokes to red:</span></span>

[!code-csharp[DigitalInkTopics#9](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a><span data-ttu-id="cf774-133">DefaultDrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="cf774-133">DefaultDrawingAttributes</span></span>

<span data-ttu-id="cf774-134">Свойство <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> предоставляет доступ к свойствам, таким как высота, ширина и цвет штрихов, создаваемых в <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="cf774-134">The <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property provides access to properties such as the height, width, and color of the strokes to be created in an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="cf774-135">После изменения <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>все будущие штрихи, введенные в <xref:System.Windows.Controls.InkCanvas>, подготавливаются к просмотру новыми значениями свойств.</span><span class="sxs-lookup"><span data-stu-id="cf774-135">Once you change the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, all future strokes entered into the <xref:System.Windows.Controls.InkCanvas> are rendered with the new property values.</span></span>

<span data-ttu-id="cf774-136">В дополнение к изменению <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> в файле кода программной части можно использовать синтаксис XAML для указания свойств <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>.</span><span class="sxs-lookup"><span data-stu-id="cf774-136">In addition to modifying the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in the code-behind file, you can use XAML syntax for specifying <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties.</span></span>

<span data-ttu-id="cf774-137">В следующем примере показано, как задать свойство <xref:System.Windows.Ink.DrawingAttributes.Color%2A>.</span><span class="sxs-lookup"><span data-stu-id="cf774-137">The next example demonstrates how to set the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> property.</span></span> <span data-ttu-id="cf774-138">Чтобы использовать этот код, создайте новый проект WPF с именем "Хеллоинкканвас" в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cf774-138">To use this code, create a new WPF project called "HelloInkCanvas" in Visual Studio.</span></span> <span data-ttu-id="cf774-139">Замените код в файле *MainWindow. XAML* следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="cf774-139">Replace the code in the *MainWindow.xaml* file with the following code:</span></span>

[!code-xaml[HelloInkCanvas#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

<span data-ttu-id="cf774-140">Затем добавьте следующие обработчики событий кнопок в файл кода программной части внутри класса MainWindow:</span><span class="sxs-lookup"><span data-stu-id="cf774-140">Next, add the following button event handlers to the code behind file, inside the MainWindow class:</span></span>

[!code-csharp[HelloInkCanvas#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

<span data-ttu-id="cf774-141">После копирования этого кода нажмите клавишу **F5** в Visual Studio, чтобы запустить программу в отладчике.</span><span class="sxs-lookup"><span data-stu-id="cf774-141">After copying this code, press **F5** in Visual Studio to run the program in the debugger.</span></span>

<span data-ttu-id="cf774-142">Обратите внимание на то, как <xref:System.Windows.Controls.StackPanel> помещает кнопки поверх <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="cf774-142">Notice how the <xref:System.Windows.Controls.StackPanel> places the buttons on top of the <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="cf774-143">При попытке рукописного ввода в верхней части кнопок <xref:System.Windows.Controls.InkCanvas> собирает и отображает рукописные данные позади кнопок.</span><span class="sxs-lookup"><span data-stu-id="cf774-143">If you try to ink over the top of the buttons, the <xref:System.Windows.Controls.InkCanvas> collects and renders the ink behind the buttons.</span></span> <span data-ttu-id="cf774-144">Это связано с тем, что кнопки являются одноуровневыми элементами <xref:System.Windows.Controls.InkCanvas>, а не дочерними.</span><span class="sxs-lookup"><span data-stu-id="cf774-144">This is because the buttons are siblings of the <xref:System.Windows.Controls.InkCanvas> as opposed to children.</span></span> <span data-ttu-id="cf774-145">Кроме того, кнопки находятся выше в z-порядке, поэтому рукописные фрагменты отображаются позади них.</span><span class="sxs-lookup"><span data-stu-id="cf774-145">Also, the buttons are higher in the z-order, so the ink is rendered behind them.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf774-146">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cf774-146">See also</span></span>

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>
