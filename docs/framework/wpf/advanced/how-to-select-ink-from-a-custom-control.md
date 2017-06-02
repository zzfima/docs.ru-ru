---
title: "Практическое руководство. Выбор рукописного ввода из пользовательского элемента управления | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "элементы управления, выбор рукописного ввода"
  - "пользовательские элементы управления, выбор рукописного ввода"
  - "рукописный ввод, выбор в пользовательском элементе управления"
ms.assetid: 5f3a45c6-6d40-4017-9b47-933f134ceba3
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Выбор рукописного ввода из пользовательского элемента управления
Добавляя <xref:System.Windows.Ink.IncrementalLassoHitTester> в пользовательский элементу управления, можно включить элемент управления, так что пользователь сможет выбрать рукописные данные с помощью инструмента лассо так же, как <xref:System.Windows.Controls.InkCanvas> выделяет рукописные данные с помощью лассо.  
  
 В этом примере требуется знакомство с процессом создания пользовательского элемента управления, поддерживающего рукописный ввод.  О создании пользовательского элемента управления, который принимает рукописный ввод, см. в разделе [Создание элемента управления рукописным вводом](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).  
  
## Пример  
 Когда пользователь рисует лассо, <xref:System.Windows.Ink.IncrementalLassoHitTester> прогнозирует какие штрихи будут в пределах границы контура лассо после того, как пользователь завершит лассо.  Штрихи, которые находятся в пределах границы контура лассо, могут быть рассмотрены как выбранные.  С выбранных штрихов также можно снять выделение.  Например, если пользователь изменяет направление во время рисования лассо, <xref:System.Windows.Ink.IncrementalLassoHitTester> может снять выделение некоторых штрихов.  
  
 <xref:System.Windows.Ink.IncrementalLassoHitTester> вызывает событие <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged>, которое включает реагирование пользовательского элемента управления, пока пользователь рисует лассо.  Например, можно изменить внешний вид штрихов, когда пользователь выделяет и снимает выделение с них.  
  
## Управление режимом рукописного ввода  
 Для пользователей удобнее, если лассо отображается иначе, чем рукописные данные элемента управления.  Чтобы выполнить это, пользовательский элемент управления должен следить за тем, пишет ли пользователь или выбирает рукописный ввод.  Простейший способ сделать это состоит в том, чтобы объявить перечисление с двумя значениями, одно будет указывать, что пользователь записывает рукописные данные, а второе ― что пользователь выделяет их.  
  
 [!code-csharp[HowToSelectInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#2)]
 [!code-vb[HowToSelectInk#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#2)]  
  
 Далее, добавить два <xref:System.Windows.Ink.DrawingAttributes> в класс: один для использования при записи пользователем рукописного ввода, другой ― при выборе пользователем рукописного ввода.  В конструкторе инициализируйте <xref:System.Windows.Ink.DrawingAttributes> и присоедините оба события <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> к одному и тому же обработчику событий.  Затем установите свойство <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> в атрибут рукописного ввода <xref:System.Windows.Ink.DrawingAttributes>.  
  
 [!code-csharp[HowToSelectInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#3)]
 [!code-vb[HowToSelectInk#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#3)]  
[!code-csharp[HowToSelectInk#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#4)]
[!code-vb[HowToSelectInk#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#4)]  
  
 Добавьте свойство, которое предоставляет режим выделения.  Когда пользователь изменяет режим выделения, установите свойство <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> в соответствующий объект <xref:System.Windows.Ink.DrawingAttributes>, и затем повторно присоедините свойство <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> к <xref:System.Windows.Controls.InkPresenter>.  
  
 [!code-csharp[HowToSelectInk#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#5)]
 [!code-vb[HowToSelectInk#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#5)]  
  
 Предоставьте <xref:System.Windows.Ink.DrawingAttributes> в качестве свойств, чтобы приложения могли определить внешний вид рукописных штрихов и штрихов выделенного фрагмента.  
  
 [!code-csharp[HowToSelectInk#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#6)]
 [!code-vb[HowToSelectInk#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#6)]  
  
 Когда свойство объекта <xref:System.Windows.Ink.DrawingAttributes> изменяется, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> должен быть повторно присоединен к <xref:System.Windows.Controls.InkPresenter>.  В обработчике событий для события <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> повторно присоедините <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> к  <xref:System.Windows.Controls.InkPresenter>.  
  
 [!code-csharp[HowToSelectInk#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#7)]
 [!code-vb[HowToSelectInk#7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#7)]  
  
## Использование IncrementalLassoHitTester  
 Создайте и инициализируйте <xref:System.Windows.Ink.StrokeCollection>, содержащую выбранные штрихи.  
  
 [!code-csharp[HowToSelectInk#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#8)]
 [!code-vb[HowToSelectInk#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#8)]  
  
 Когда пользователь начинает рисовать штрих, рукописный текст или лассо, снимите выделение со всех выделенных штрихов.  Затем, если пользователь рисует лассо, создайте <xref:System.Windows.Ink.IncrementalLassoHitTester>с помощью вызова <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>, подпишитесь на событие <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> и вызовите <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>.  Этот код может быть отдельным методом и вызваться из методов <xref:System.Windows.UIElement.OnStylusDown%2A> и <xref:System.Windows.UIElement.OnMouseDown%2A>.  
  
 [!code-csharp[HowToSelectInk#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#9)]
 [!code-vb[HowToSelectInk#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#9)]  
  
 Добавляйте точки пера к <xref:System.Windows.Ink.IncrementalLassoHitTester>, пока пользователь рисует лассо.  Вызовите следующий метод у методов <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A> <xref:System.Windows.UIElement.OnMouseMove%2A> и <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A>.  
  
 [!code-csharp[HowToSelectInk#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#10)]
 [!code-vb[HowToSelectInk#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#10)]  
  
 Обработайте событие <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=fullName> для реагирования на то, когда пользователь выделяет и снимает выделение с штрихов.  Класс <xref:System.Windows.Ink.LassoSelectionChangedEventArgs> имеет <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> и <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> свойства, получающие штрихи, которые были выделены и сняты с выделения, соответственно.  
  
 [!code-csharp[HowToSelectInk#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#11)]
 [!code-vb[HowToSelectInk#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#11)]  
  
 Когда пользователь завершает рисование лассо, откажитесь от подписки события <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> и вызовите <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>.  
  
 [!code-csharp[HowToSelectInk#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#12)]
 [!code-vb[HowToSelectInk#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#12)]  
  
## Объединение частей приложения  
 Следующий пример представляет пользовательский элемент управления, дающий пользователю возможность выбрать рукописный ввод с помощью лассо.  
  
 [!code-csharp[HowToSelectInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#1)]
 [!code-vb[HowToSelectInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#1)]  
  
## См. также  
 <xref:System.Windows.Ink.IncrementalLassoHitTester>   
 <xref:System.Windows.Ink.StrokeCollection>   
 <xref:System.Windows.Input.StylusPointCollection>   
 [Создание элемента управления рукописным вводом](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md)