---
title: Сбора рукописных данных в приложениях WPF
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
ms.openlocfilehash: 25f9c0141a97d8e52e0883b14fd3e1f4574a05ea
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "45527728"
---
# <a name="collect-ink"></a><span data-ttu-id="db0e1-102">Сбора рукописных фрагментов</span><span class="sxs-lookup"><span data-stu-id="db0e1-102">Collect Ink</span></span>

<span data-ttu-id="db0e1-103">Платформа [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md) выполняет сбор цифровых рукописных фрагментов, что является одной из основных ее функций.</span><span class="sxs-lookup"><span data-stu-id="db0e1-103">The [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md) platform collects digital ink as a core part of its functionality.</span></span> <span data-ttu-id="db0e1-104">В этом разделе обсуждаются методы сбора рукописных данных в Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="db0e1-104">This topic discusses methods for collection of ink in Windows Presentation Foundation (WPF).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="db0e1-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="db0e1-105">Prerequisites</span></span>

<span data-ttu-id="db0e1-106">Чтобы использовать в следующих примерах, сначала необходимо установить Visual Studio и [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db0e1-106">To use the following examples, you must first install Visual Studio and the [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span></span> <span data-ttu-id="db0e1-107">Следует также понять, как создавать приложения для WPF.</span><span class="sxs-lookup"><span data-stu-id="db0e1-107">You should also understand how to write applications for the WPF.</span></span> <span data-ttu-id="db0e1-108">Дополнительные сведения о начале работы с WPF, см. в разделе [Пошаговое руководство: создание первого классического приложения WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="db0e1-108">For more information about getting started with WPF, see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="use-the-inkcanvas-element"></a><span data-ttu-id="db0e1-109">Использование элемента InkCanvas</span><span class="sxs-lookup"><span data-stu-id="db0e1-109">Use the InkCanvas Element</span></span>

<span data-ttu-id="db0e1-110"><xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> Элемент предоставляет самый простой способ сбора рукописных данных в WPF.</span><span class="sxs-lookup"><span data-stu-id="db0e1-110">The <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> element provides the easiest way to collect ink in WPF.</span></span> <span data-ttu-id="db0e1-111">Используйте <xref:System.Windows.Controls.InkCanvas> элемент для получения и отображения рукописного ввода.</span><span class="sxs-lookup"><span data-stu-id="db0e1-111">Use an <xref:System.Windows.Controls.InkCanvas> element to receive and display ink input.</span></span> <span data-ttu-id="db0e1-112">Рукописный ввод, как правило, осуществляется с помощью пера, которое взаимодействует с дигитайзером для создания рукописных штрихов.</span><span class="sxs-lookup"><span data-stu-id="db0e1-112">You commonly input ink through the use of a stylus, which interacts with a digitizer to produce ink strokes.</span></span> <span data-ttu-id="db0e1-113">Кроме того, вместо пера можно использовать мышь.</span><span class="sxs-lookup"><span data-stu-id="db0e1-113">In addition, a mouse can be used in place of a stylus.</span></span> <span data-ttu-id="db0e1-114">Созданные штрихи представляются в виде <xref:System.Windows.Ink.Stroke> объекты и их можно управлять программно или пользователем ввода данных.</span><span class="sxs-lookup"><span data-stu-id="db0e1-114">The created strokes are represented as <xref:System.Windows.Ink.Stroke> objects, and they can be manipulated both programmatically and by user input.</span></span> <span data-ttu-id="db0e1-115"><xref:System.Windows.Controls.InkCanvas> Позволяет пользователям выбор, изменение или удаление существующего <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="db0e1-115">The <xref:System.Windows.Controls.InkCanvas> enables users to select, modify, or delete an existing <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="db0e1-116">С помощью XAML, вы можно настроить сбор рукописных фрагментов, просто добавив **InkCanvas** к дереву.</span><span class="sxs-lookup"><span data-stu-id="db0e1-116">By using XAML, you can set up ink collection as easily as adding an **InkCanvas** element to your tree.</span></span> <span data-ttu-id="db0e1-117">В следующем примере добавляется <xref:System.Windows.Controls.InkCanvas> в проект WPF по умолчанию, созданные в Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="db0e1-117">The following example adds an <xref:System.Windows.Controls.InkCanvas> to a default WPF project created in Visual Studio:</span></span>

[!code-xaml[DigitalInkTopics#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

<span data-ttu-id="db0e1-118">**InkCanvas** элемент также может содержать дочерние элементы, что позволяет добавлять функции рукописных заметок практически любого типа элемента XAML.</span><span class="sxs-lookup"><span data-stu-id="db0e1-118">The **InkCanvas** element can also contain child elements, making it possible to add ink annotation capabilities to almost any type of XAML element.</span></span> <span data-ttu-id="db0e1-119">Например, чтобы добавить возможности рукописного ввода в текстовый элемент, просто сделайте его дочерним элементом <xref:System.Windows.Controls.InkCanvas>:</span><span class="sxs-lookup"><span data-stu-id="db0e1-119">For example, to add inking capabilities to a text element, simply make it a child of an <xref:System.Windows.Controls.InkCanvas>:</span></span>

[!code-xaml[DigitalInkTopics#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

<span data-ttu-id="db0e1-120">Добавление поддержки пометки изображений с помощью рукописного ввода выполняется так же просто:</span><span class="sxs-lookup"><span data-stu-id="db0e1-120">Adding support for marking up an image with ink is just as easy:</span></span>

[!code-xaml[DigitalInkTopics#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a><span data-ttu-id="db0e1-121">Режимы InkCollection</span><span class="sxs-lookup"><span data-stu-id="db0e1-121">InkCollection Modes</span></span>

<span data-ttu-id="db0e1-122"><xref:System.Windows.Controls.InkCanvas> Обеспечивает поддержку различных режимов ввода с помощью его <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="db0e1-122">The <xref:System.Windows.Controls.InkCanvas> provides support for various input modes through its <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> property.</span></span>

### <a name="manipulate-ink"></a><span data-ttu-id="db0e1-123">Рукописным вводом</span><span class="sxs-lookup"><span data-stu-id="db0e1-123">Manipulate Ink</span></span>

<span data-ttu-id="db0e1-124"><xref:System.Windows.Controls.InkCanvas> Обеспечивает поддержку многих операций редактирования рукописных данных.</span><span class="sxs-lookup"><span data-stu-id="db0e1-124">The <xref:System.Windows.Controls.InkCanvas> provides support for many ink editing operations.</span></span> <span data-ttu-id="db0e1-125">Например <xref:System.Windows.Controls.InkCanvas> стереть поддерживает назад пера, и требуется дополнительный код для добавления функций к элементу.</span><span class="sxs-lookup"><span data-stu-id="db0e1-125">For example, <xref:System.Windows.Controls.InkCanvas> supports back-of-pen erase, and no additional code is needed to add the functionality to the element.</span></span>

#### <a name="selection"></a><span data-ttu-id="db0e1-126">Выбранное</span><span class="sxs-lookup"><span data-stu-id="db0e1-126">Selection</span></span>

<span data-ttu-id="db0e1-127">Установка режима выбора сводится параметр <xref:System.Windows.Controls.InkCanvasEditingMode> свойства **выберите**.</span><span class="sxs-lookup"><span data-stu-id="db0e1-127">Setting selection mode is as simple as setting the <xref:System.Windows.Controls.InkCanvasEditingMode> property to **Select**.</span></span>

<span data-ttu-id="db0e1-128">Следующий код устанавливает режим редактирования на основе значения из <xref:System.Windows.Forms.CheckBox>:</span><span class="sxs-lookup"><span data-stu-id="db0e1-128">The following code sets the editing mode based on the value of a <xref:System.Windows.Forms.CheckBox>:</span></span>

[!code-csharp[DigitalInkTopics#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a><span data-ttu-id="db0e1-129">DrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="db0e1-129">DrawingAttributes</span></span>

<span data-ttu-id="db0e1-130">Используйте <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> свойство для изменения внешнего вида рукописных штрихов.</span><span class="sxs-lookup"><span data-stu-id="db0e1-130">Use the <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> property to change the appearance of ink strokes.</span></span> <span data-ttu-id="db0e1-131">Например <xref:System.Windows.Ink.DrawingAttributes.Color%2A> членом <xref:System.Windows.Ink.DrawingAttributes> задает цвет отображаемого объекта <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="db0e1-131">For instance, the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> member of <xref:System.Windows.Ink.DrawingAttributes> sets the color of the rendered <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="db0e1-132">В следующем примере изменяется цвет выбранных штрихов на красный:</span><span class="sxs-lookup"><span data-stu-id="db0e1-132">The following example changes the color of the selected strokes to red:</span></span>

[!code-csharp[DigitalInkTopics#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a><span data-ttu-id="db0e1-133">DefaultDrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="db0e1-133">DefaultDrawingAttributes</span></span>

<span data-ttu-id="db0e1-134"><xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> Свойство предоставляет доступ к свойствам, например высоту, ширину и цвет штрихов, создаваемых в <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="db0e1-134">The <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property provides access to properties such as the height, width, and color of the strokes to be created in an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="db0e1-135">После перевода <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, все следующие штрихи, введенные в <xref:System.Windows.Controls.InkCanvas> подготавливаются к просмотру с новыми значениями свойства.</span><span class="sxs-lookup"><span data-stu-id="db0e1-135">Once you change the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, all future strokes entered into the <xref:System.Windows.Controls.InkCanvas> are rendered with the new property values.</span></span>

<span data-ttu-id="db0e1-136">А также изменения <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> в файле кода, можно использовать синтаксис XAML для указания <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="db0e1-136">In addition to modifying the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in the code-behind file, you can use XAML syntax for specifying <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties.</span></span>

<span data-ttu-id="db0e1-137">Далее примере показано, как задать <xref:System.Windows.Ink.DrawingAttributes.Color%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="db0e1-137">The next example demonstrates how to set the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> property.</span></span> <span data-ttu-id="db0e1-138">Чтобы использовать этот код, создайте новый проект WPF с именем «HelloInkCanvas» в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="db0e1-138">To use this code, create a new WPF project called "HelloInkCanvas" in Visual Studio.</span></span> <span data-ttu-id="db0e1-139">Замените код в *MainWindow.xaml* файла следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="db0e1-139">Replace the code in the *MainWindow.xaml* file with the following code:</span></span>

[!code-xaml[HelloInkCanvas#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

<span data-ttu-id="db0e1-140">Затем добавьте следующие обработчики событий для кнопки в файл кода программной части, внутри класса MainWindow:</span><span class="sxs-lookup"><span data-stu-id="db0e1-140">Next, add the following button event handlers to the code behind file, inside the MainWindow class:</span></span>

[!code-csharp[HelloInkCanvas#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

<span data-ttu-id="db0e1-141">После копирования этого кода нажмите клавишу **F5** в Visual Studio для запуска программы в отладчике.</span><span class="sxs-lookup"><span data-stu-id="db0e1-141">After copying this code, press **F5** in Visual Studio to run the program in the debugger.</span></span>

<span data-ttu-id="db0e1-142">Обратите внимание, что как <xref:System.Windows.Controls.StackPanel> размещает кнопки вверху <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="db0e1-142">Notice how the <xref:System.Windows.Controls.StackPanel> places the buttons on top of the <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="db0e1-143">При попытке рукописного ввода поверх кнопок, <xref:System.Windows.Controls.InkCanvas> собирает и отображает рукописные данные позади кнопок.</span><span class="sxs-lookup"><span data-stu-id="db0e1-143">If you try to ink over the top of the buttons, the <xref:System.Windows.Controls.InkCanvas> collects and renders the ink behind the buttons.</span></span> <span data-ttu-id="db0e1-144">Это обусловлено кнопок являются одноранговыми с <xref:System.Windows.Controls.InkCanvas> в отличие от дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="db0e1-144">This is because the buttons are siblings of the <xref:System.Windows.Controls.InkCanvas> as opposed to children.</span></span> <span data-ttu-id="db0e1-145">Кроме того, кнопки находятся выше в z-порядке, поэтому рукописные фрагменты отображаются позади них.</span><span class="sxs-lookup"><span data-stu-id="db0e1-145">Also, the buttons are higher in the z-order, so the ink is rendered behind them.</span></span>

## <a name="see-also"></a><span data-ttu-id="db0e1-146">См. также</span><span class="sxs-lookup"><span data-stu-id="db0e1-146">See Also</span></span>

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>