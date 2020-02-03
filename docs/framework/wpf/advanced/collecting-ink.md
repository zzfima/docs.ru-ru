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
# <a name="collect-ink"></a>Собирайте рукописные данные

Платформа [Windows Presentation Foundation](../index.md) выполняет сбор цифровых рукописных фрагментов, что является одной из основных ее функций. В этом разделе обсуждаются методы сбора рукописного ввода в Windows Presentation Foundation (WPF).

## <a name="prerequisites"></a>предварительные требования

Чтобы использовать следующие примеры, необходимо сначала установить Visual Studio и Windows SDK. Следует также понимать, как писать приложения для WPF. Дополнительные сведения о начале работы с WPF см. в разделе [Пошаговое руководство. мое первое классическое приложение WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).

## <a name="use-the-inkcanvas-element"></a>Использование элемента InkCanvas

Элемент <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> предоставляет самый простой способ собираются рукописный ввод в WPF. Используйте элемент <xref:System.Windows.Controls.InkCanvas> для получения и вывода рукописных данных. Рукописный ввод, как правило, осуществляется с помощью пера, которое взаимодействует с дигитайзером для создания рукописных штрихов. Кроме того, вместо пера можно использовать мышь. Созданные штрихи представляются как <xref:System.Windows.Ink.Stroke> объекты, и их можно манипулировать как программно, так и с помощью пользовательского ввода. <xref:System.Windows.Controls.InkCanvas> позволяет пользователям выбирать, изменять или удалять существующие <xref:System.Windows.Ink.Stroke>.

С помощью XAML можно настроить сбор рукописных данных так же легко, как добавить элемент **InkCanvas** в дерево. В следующем примере добавляется <xref:System.Windows.Controls.InkCanvas> в проект WPF по умолчанию, созданный в Visual Studio.

[!code-xaml[DigitalInkTopics#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

Элемент **InkCanvas** также может содержать дочерние элементы, что позволяет добавлять возможности рукописных заметок практически к любому типу элемента XAML. Например, чтобы добавить возможности рукописного ввода в текстовый элемент, просто сделайте его дочерним элементом <xref:System.Windows.Controls.InkCanvas>:

[!code-xaml[DigitalInkTopics#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

Добавление поддержки пометки изображения с помощью рукописного ввода — это так же просто:

[!code-xaml[DigitalInkTopics#7](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a>Режимы InkCollection

<xref:System.Windows.Controls.InkCanvas> обеспечивает поддержку различных режимов ввода с помощью свойства <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>.

### <a name="manipulate-ink"></a>Работа с рукописными данными

<xref:System.Windows.Controls.InkCanvas> обеспечивает поддержку многих операций редактирования рукописных данных. Например, <xref:System.Windows.Controls.InkCanvas> поддерживает стирание в обратном пера, а дополнительный код не требуется для добавления функциональности в элемент.

#### <a name="selection"></a>Выбор

Настройка режима выделения так же проста, как установка свойства <xref:System.Windows.Controls.InkCanvasEditingMode> для **выбора**.

Следующий код задает режим редактирования на основе значения <xref:System.Windows.Forms.CheckBox>:

[!code-csharp[DigitalInkTopics#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a>DrawingAttributes

Используйте свойство <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A>, чтобы изменить внешний вид рукописных штрихов. Например, элемент <xref:System.Windows.Ink.DrawingAttributes.Color%2A> <xref:System.Windows.Ink.DrawingAttributes> задает цвет отображаемого <xref:System.Windows.Ink.Stroke>.

В следующем примере цвет выбранных штрихов меняется на красный:

[!code-csharp[DigitalInkTopics#9](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a>DefaultDrawingAttributes

Свойство <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> предоставляет доступ к свойствам, таким как высота, ширина и цвет штрихов, создаваемых в <xref:System.Windows.Controls.InkCanvas>. После изменения <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>все будущие штрихи, введенные в <xref:System.Windows.Controls.InkCanvas>, подготавливаются к просмотру новыми значениями свойств.

В дополнение к изменению <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> в файле кода программной части можно использовать синтаксис XAML для указания свойств <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>.

В следующем примере показано, как задать свойство <xref:System.Windows.Ink.DrawingAttributes.Color%2A>. Чтобы использовать этот код, создайте новый проект WPF с именем "Хеллоинкканвас" в Visual Studio. Замените код в файле *MainWindow. XAML* следующим кодом:

[!code-xaml[HelloInkCanvas#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

Затем добавьте следующие обработчики событий кнопок в файл кода программной части внутри класса MainWindow:

[!code-csharp[HelloInkCanvas#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

После копирования этого кода нажмите клавишу **F5** в Visual Studio, чтобы запустить программу в отладчике.

Обратите внимание на то, как <xref:System.Windows.Controls.StackPanel> помещает кнопки поверх <xref:System.Windows.Controls.InkCanvas>. При попытке рукописного ввода в верхней части кнопок <xref:System.Windows.Controls.InkCanvas> собирает и отображает рукописные данные позади кнопок. Это связано с тем, что кнопки являются одноуровневыми элементами <xref:System.Windows.Controls.InkCanvas>, а не дочерними. Кроме того, кнопки находятся выше в z-порядке, поэтому рукописные фрагменты отображаются позади них.

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>
