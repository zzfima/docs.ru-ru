---
title: "Пользовательская отрисовка рукописных данных | Microsoft Docs"
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
  - "классы, DynamicRenderer"
  - "классы, InkCanvas"
  - "классы, Росчерк"
  - "пользовательская отрисовка рукописных данных"
  - "DynamicRenderer - класс"
  - "рукописный ввод, пользовательская отрисовка"
  - "InkCanvas - класс"
  - "Stroke - класс"
ms.assetid: 65c978a7-0ee0-454f-ac7f-b1bd2efecac5
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Пользовательская отрисовка рукописных данных
Свойство <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> штриха позволяет задавать внешний вид штриха: размер, цвет и очертание, но иногда, чтобы настроить внешний вид, требуется использовать другие возможности, чем предлагает <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A>.  Возможно, потребуется настроить внешний вид рукописных данных с помощью аэрографа, масляной краски и других эффектов.  [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] позволяет настроить отображение настраиваемых рукописных данных путем реализации пользовательских объектов <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> и <xref:System.Windows.Ink.Stroke>.  
  
 В этом разделе содержатся следующие подразделы:  
  
-   [Архитектура](#Architecture)  
  
-   [Реализация динамического обработчика прорисовки](#ImplementingADynamicRenderer)  
  
-   [Implementing a Custom Stroke](#ImplementingACustomStroke)  
  
-   [Реализация пользовательского класса InkCanvas](#ImplementingACustomInkCanvas)  
  
-   [Заключение](#Conclusion)  
  
<a name="Architecture"></a>   
## Архитектура  
 Отрисовка рукописных данных создается в двух случаях: когда пользователь пишет на поверхности рисования и снова после того, как на поверхность для ввода рукописных данных, добавляется штрих.  Объект <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> отображает рукописные данные при перемещении пера планшета по дигитайзеру, а объект <xref:System.Windows.Ink.Stroke> отображает сам себя после его добавления к элементу.  
  
 Существуют три класса для реализации при динамической отрисовке рукописных данных.  
  
1.  **DynamicRenderer**: реализует класс, производный класса <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.  Это специализированный класс <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>, отображающий штрих после его написания.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> осуществляет отрисовку в отдельном потоке, поэтому поверхность для отображения рукописного ввода появляется для сбора рукописных данных даже при блокировке потока пользовательского интерфейса приложения.   Дополнительные сведения о потоковой модели содержатся в разделе [Потоковая модель рукописного ввода](../../../../docs/framework/wpf/advanced/the-ink-threading-model.md).  Чтобы настроить динамическую отрисовку штриха, переопределите метод <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A>.  
  
2.  **Stroke**: реализует класс, производный класса <xref:System.Windows.Ink.Stroke>.  Этот класс отвечает за статическую отрисовку данных <xref:System.Windows.Input.StylusPoint> после преобразования в объект <xref:System.Windows.Ink.Stroke>.  Переопределите метод <xref:System.Windows.Ink.Stroke.DrawCore%2A>, чтобы гарантировать согласованность статической отрисовки штриха с динамическим.  
  
3.  **InkCanvas:** реализует класс, производный класса <xref:System.Windows.Controls.InkCanvas>.  Назначьте пользовательский объект <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> свойству <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>.  Переопределите метод <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> и добавьте пользовательский штрих к свойству <xref:System.Windows.Controls.InkCanvas.Strokes%2A>.  Это гарантирует согласованность внешнего вида рукописных данных.  
  
<a name="ImplementingADynamicRenderer"></a>   
## Реализация динамического обработчика прорисовки  
 Хотя класс <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> является стандартной частью приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], для выполнения специальных задач отрисовки необходимо создать пользовательский динамический обработчик прорисовки, производный объекта <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, и переопределить метод <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A>.  
  
 В следующем примере показан пользовательский объект <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, который отображает рукописные данные, введенные кистью с эффектом линейного градиента.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#1)]
[!code-vb[AdvancedInkTopicsSamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#1)]  
  
<a name="ImplementingCustomStrokes"></a>   
## Реализация пользовательских штрихов  
 Реализуйте класс, производный класса <xref:System.Windows.Ink.Stroke>.  Этот класс отвечает за отрисовку данных <xref:System.Windows.Input.StylusPoint> после преобразования в объект <xref:System.Windows.Ink.Stroke>.  Переопределите класс <xref:System.Windows.Ink.Stroke.DrawCore%2A> для выполнения фактического рисования.  
  
 Класс Stroke может также хранить пользовательские данные с помощью метода <xref:System.Windows.Ink.Stroke.AddPropertyData%2A>.  Эти данные сохраняются с данными штриха при сохранении.  
  
 Класс <xref:System.Windows.Ink.Stroke> может также выполнить проверку попадания курсора мыши.  Можно также реализовать собственный алгоритм проверки попадания путем переопределения метода <xref:System.Windows.Ink.Stroke.HitTest%2A> в текущем классе.  
  
 Следующий код C\# демонстрирует пользовательский класс <xref:System.Windows.Ink.Stroke>, отображающий данные <xref:System.Windows.Input.StylusPoint> в виде трехмерного штриха.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#2)]
[!code-vb[AdvancedInkTopicsSamples#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#2)]  
  
<a name="ImplementingACustomInkCanvas"></a>   
## Реализация пользовательского класса InkCanvas  
 Самым простым способом применения пользовательского класса <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> и штриха является реализация класса, который наследует из класса <xref:System.Windows.Controls.InkCanvas> и использует эти классы.  Класс <xref:System.Windows.Controls.InkCanvas> имеет свойство <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>, указывающее, каким образом отображается штрих, когда пользователь его рисует.  
  
 Для отображения пользовательских штрихов в классе <xref:System.Windows.Controls.InkCanvas> выполните следующие действия:  
  
-   Создайте класс, производный класса <xref:System.Windows.Controls.InkCanvas>.  
  
-   Назначьте пользовательский класс <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> свойству <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=fullName>.  
  
-   Переопределите метод <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A>.  В этом методе удалите исходный штрих, который был добавлен к классу InkCanvas.  Создайте пользовательский штрих, добавьте его к свойству <xref:System.Windows.Controls.InkCanvas.Strokes%2A> и вызовите базовый класс с новым объектом <xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs>, содержащим пользовательский штрих.  
  
 Следующий код C\# демонстрирует пользовательский класс <xref:System.Windows.Controls.InkCanvas>, использующий настраиваемый объект <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> и сохраняющий пользовательские штрихи.  
  
 [!code-csharp[AdvancedInkTopicsSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#9)]  
  
 Класс <xref:System.Windows.Controls.InkCanvas> может содержать несколько объектов <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.  Можно добавить несколько объектов <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> к классу <xref:System.Windows.Controls.InkCanvas>, путем добавления их к свойству <xref:System.Windows.UIElement.StylusPlugIns%2A>.  
  
<a name="Conclusion"></a>   
## Заключение  
 Можно настроить внешний вид рукописных данных путем наследования своих собственных классов <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, <xref:System.Windows.Ink.Stroke> и <xref:System.Windows.Controls.InkCanvas>.  Вместе эти классы гарантируют единообразный внешний вид во время рисования и после сохранения штриха.  
  
## См. также  
 [Дополнительная обработка рукописных данных](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)