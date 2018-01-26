---
title: "Практическое руководство. Выбор рукописного ввода из пользовательского элемента управления"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ink selection
- ink [WPF], selecting from custom control
- custom controls [WPF], ink selection
ms.assetid: 5f3a45c6-6d40-4017-9b47-933f134ceba3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 972ece6964d1f3cc42c6221c3b18336e3353bc18
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-select-ink-from-a-custom-control"></a>Практическое руководство. Выбор рукописного ввода из пользовательского элемента управления
Добавив <xref:System.Windows.Ink.IncrementalLassoHitTester> в элемент управления, можно включить элемент управления, чтобы пользователь мог выбрать рукописного ввода с помощью инструмента Лассо, аналогично тому, как <xref:System.Windows.Controls.InkCanvas> выборе рукописного ввода с помощью лассо.  
  
 В этом примере предполагается, что вы знакомы с созданием пользовательский элемент управления, поддержка рукописного ввода.  Создание пользовательского элемента управления, который принимает рукописный ввод — [Создание элемента управления вводом рукописного ввода](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).  
  
## <a name="example"></a>Пример  
 Когда пользователь рисует лассо, <xref:System.Windows.Ink.IncrementalLassoHitTester> прогнозирует какие штрихи будут в пределах границы контура лассо пользователь не завершит лассо.  Штрихов, которые перестанут быть в пределах границы контура лассо может рассматриваться как выбранные.  Выбранных штрихов можно также снимается.  Например, если пользователь меняет направление при рисовании лассо <xref:System.Windows.Ink.IncrementalLassoHitTester> может отменить выбор некоторых штрихов рукописного ввода.  
  
 <xref:System.Windows.Ink.IncrementalLassoHitTester> Вызывает <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> событие, которое позволяет реагировать, пока пользователь рисует лассо пользовательского элемента управления.  Например можно изменить внешний вид штрихов, пользователь выбирает и приводит к отмене выбора их.  
  
## <a name="managing-the-ink-mode"></a>Управление режимом рукописного ввода  
 Бывает полезно для пользователя, если лассо отображается иначе, чем рукописного текста на элементе управления. Для этого пользовательского элемента управления необходимо хранить список ли пользователь записи или выбирает рукописный ввод. Самый простой способ сделать это — объявить перечисление с двумя значениями: один для указания, что пользователь пишет рукописного ввода, а второй — для указания, что пользователь выбирает рукописного ввода.  
  
 [!code-csharp[HowToSelectInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#2)]
 [!code-vb[HowToSelectInk#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#2)]  
  
 Добавьте два <xref:System.Windows.Ink.DrawingAttributes> в класс: один для использования при записи пользователем рукописного ввода, при выборе пользователем рукописного ввода.  В конструкторе, инициализировать <xref:System.Windows.Ink.DrawingAttributes> и присоедините оба <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> события, чтобы один и тот же обработчик событий. Затем установите <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> свойство <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> для заметки рукописного ввода <xref:System.Windows.Ink.DrawingAttributes>.  
  
 [!code-csharp[HowToSelectInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#3)]
 [!code-vb[HowToSelectInk#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#3)]  
[!code-csharp[HowToSelectInk#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#4)]
[!code-vb[HowToSelectInk#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#4)]  
  
 Добавьте свойство, которое предоставляет режим выделения. Когда пользователь изменяет режим выделения, задайте <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> свойство <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> к соответствующему <xref:System.Windows.Ink.DrawingAttributes> объекта и присоедините <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> свойства <xref:System.Windows.Controls.InkPresenter>.  
  
 [!code-csharp[HowToSelectInk#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#5)]
 [!code-vb[HowToSelectInk#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#5)]  
  
 Предоставлять <xref:System.Windows.Ink.DrawingAttributes> как свойства, чтобы приложения могли определить внешний вид штрихов и штрихов выделенного фрагмента.  
  
 [!code-csharp[HowToSelectInk#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#6)]
 [!code-vb[HowToSelectInk#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#6)]  
  
 Когда свойство <xref:System.Windows.Ink.DrawingAttributes> изменяется, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> необходимо повторно подключить <xref:System.Windows.Controls.InkPresenter>.  В обработчике событий для <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> событий, снова присоедините <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> для <xref:System.Windows.Controls.InkPresenter>.  
  
 [!code-csharp[HowToSelectInk#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#7)]
 [!code-vb[HowToSelectInk#7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#7)]  
  
## <a name="using-the-incrementallassohittester"></a>С помощью IncrementalLassoHitTester  
 Создание и инициализация <xref:System.Windows.Ink.StrokeCollection> , содержащий выбранных штрихов.  
  
 [!code-csharp[HowToSelectInk#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#8)]
 [!code-vb[HowToSelectInk#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#8)]  
  
 Когда пользователь начинает рисовать штрих, рукописного ввода или Лассо, снимите флажки для всех выделенных штрихов. Затем, если пользователь рисует лассо, создайте <xref:System.Windows.Ink.IncrementalLassoHitTester> путем вызова <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>, Подпишитесь на <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> событий и вызовов <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>. Этот код может быть отдельный метод и вызывать из <xref:System.Windows.UIElement.OnStylusDown%2A> и <xref:System.Windows.UIElement.OnMouseDown%2A> методы.  
  
 [!code-csharp[HowToSelectInk#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#9)]
 [!code-vb[HowToSelectInk#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#9)]  
  
 Добавление точки пера <xref:System.Windows.Ink.IncrementalLassoHitTester> пока пользователь рисует лассо.  Вызовите следующий метод из <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, <xref:System.Windows.UIElement.OnMouseMove%2A>, и <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> методы.  
  
 [!code-csharp[HowToSelectInk#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#10)]
 [!code-vb[HowToSelectInk#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#10)]  
  
 Обрабатывать <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> событий, чтобы ответить, когда пользователь выделяет и снимает выделение штрихов рукописного ввода.  <xref:System.Windows.Ink.LassoSelectionChangedEventArgs> Класс имеет <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> и <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> свойства, получающие штрихи, которые были выбраны и не выбрано, соответственно.  
  
 [!code-csharp[HowToSelectInk#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#11)]
 [!code-vb[HowToSelectInk#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#11)]  
  
 Когда пользователь завершает Рисование лассо, отказаться от подписки <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> событий и вызовов <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>.  
  
 [!code-csharp[HowToSelectInk#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#12)]
 [!code-vb[HowToSelectInk#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#12)]  
  
## <a name="putting-it-all-together"></a>Объединение.  
 Ниже приведен пользовательский элемент управления, позволяющий пользователю выбрать рукописный ввод с помощью лассо.  
  
 [!code-csharp[HowToSelectInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#1)]
 [!code-vb[HowToSelectInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Ink.IncrementalLassoHitTester>  
 <xref:System.Windows.Ink.StrokeCollection>  
 <xref:System.Windows.Input.StylusPointCollection>  
 [Создание элемента управления рукописным вводом](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md)
