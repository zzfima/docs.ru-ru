---
title: Пользовательская отрисовка рукописных данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom-rendering ink
- ink [WPF], custom-rendering
- classes [WPF], InkCanvas
ms.assetid: 65c978a7-0ee0-454f-ac7f-b1bd2efecac5
ms.openlocfilehash: 0ceb831057a9a92aa7319d2004f04d7cf5ac820e
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111833"
---
# <a name="custom-rendering-ink"></a>Пользовательская отрисовка рукописных данных
Свойство <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> штриха позволяет указать внешний вид штриха, например его размер, цвет и форму, но могут быть <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> моменты, которые вы хотите настроить внешний вид сверх того, что позволяет. Может потребоваться настроить отображение рукописного фрагмента с эффектом аэрографа, масляной живописи и т. д. Фонд презентации Windows (WPF) позволяет пользовательские чернила, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> <xref:System.Windows.Ink.Stroke> реализуя пользовательские и объекты.  
  
 В этом разделе содержатся следующие подразделы:  
  
- [Архитектура](#Architecture)  
  
- [Реализация динамического отрисовщика](#ImplementingADynamicRenderer)  
  
- [Реализация пользовательских штрихов](#ImplementingCustomStrokes)  
  
- [Реализация пользовательского объекта InkCanvas](#ImplementingACustomInkCanvas)  
  
- [Заключение](#Conclusion)  
  
<a name="Architecture"></a>
## <a name="architecture"></a>Architecture  
 Отрисовка рукописных фрагментов происходит два раза: когда пользователь осуществляет рукописный ввод на поверхности рукописного ввода, а затем еще раз после добавления штриха в область с поддержкой рукописного ввода. Отображает <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> чернила, когда пользователь перемещает перо планшета на дигитайзер, и <xref:System.Windows.Ink.Stroke> рендеры себя, как только он добавляется к элементу.  
  
 Предусмотрено три класса для реализации динамической отрисовки рукописных фрагментов.  
  
1. **DynamicRenderer**: Реализация класса, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>который происходит от . Этот класс является <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> специализированным, который отображает штрих по мере его нарисованного. Рендеринг <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> делается на отдельном потоке, поэтому поверхность чернил, как представляется, собирает чернила, даже когда поток пользовательского интерфейса приложения (UI) заблокирован. Дополнительные сведения о потоковой модели см. в статье [Потоковая модель рукописного ввода](the-ink-threading-model.md). Чтобы настроить динамически рендеринг штриха, переопределить <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> метод.  
  
2. **Инсульт**: Реализация класса, <xref:System.Windows.Ink.Stroke>который происходит от . Этот класс отвечает за статическое <xref:System.Windows.Input.StylusPoint> рендеринг данных <xref:System.Windows.Ink.Stroke> после их преобразования в объект. Переопределить <xref:System.Windows.Ink.Stroke.DrawCore%2A> метод, чтобы обеспечить, чтобы статическое рендеринг штриха соответствовал динамическому рендеризму.  
  
3. **InkCanvas:** Реализация класса, который <xref:System.Windows.Controls.InkCanvas>происходит от . Назначайте <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> настроенное свойство. <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> Переопределить <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> метод и добавить пользовательский штрих к свойству. <xref:System.Windows.Controls.InkCanvas.Strokes%2A> Это гарантирует согласованность внешнего вида рукописных фрагментов.  
  
<a name="ImplementingADynamicRenderer"></a>
## <a name="implementing-a-dynamic-renderer"></a>Реализация динамического отрисовщика  
 Хотя <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> класс является стандартной [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]частью, для выполнения более специализированной визуализации, необходимо создать <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> настраиваемый <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> динамический рендерер, который вытекает из метода и переопределить его.  
  
 Следующий пример демонстрирует настраиваемую <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> чернила с линейным эффектом градиентной кисти.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#1](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#1)]
[!code-vb[AdvancedInkTopicsSamples#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#1)]  
  
<a name="ImplementingCustomStrokes"></a>
## <a name="implementing-custom-strokes"></a>Реализация пользовательских штрихов  
 Реализация класса, унаследованного от класса <xref:System.Windows.Ink.Stroke>. Этот класс отвечает за <xref:System.Windows.Input.StylusPoint> визуализацию данных после <xref:System.Windows.Ink.Stroke> их преобразования в объект. Переопределить <xref:System.Windows.Ink.Stroke.DrawCore%2A> класс, чтобы сделать фактический рисунок.  
  
 Класс Stroke также может хранить пользовательские данные с помощью метода. <xref:System.Windows.Ink.Stroke.AddPropertyData%2A> Эти данные хранятся с данными штриха при сохранении.  
  
 Класс <xref:System.Windows.Ink.Stroke> также может выполнять тестирование хитов. Вы также можете реализовать свой собственный <xref:System.Windows.Ink.Stroke.HitTest%2A> алгоритм тестирования хитов, переопределив метод в текущем классе.  
  
 Следующий код C's <xref:System.Windows.Ink.Stroke> демонстрирует пользовательский <xref:System.Windows.Input.StylusPoint> класс, который отображает данные как 3D-инсульт.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#2](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#2)]
[!code-vb[AdvancedInkTopicsSamples#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#2)]  
  
<a name="ImplementingACustomInkCanvas"></a>
## <a name="implementing-a-custom-inkcanvas"></a>Реализация пользовательского объекта InkCanvas  
 Самый простой способ <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> использовать настраиваемый и штрих <xref:System.Windows.Controls.InkCanvas> — реализовать класс, который вытекает из этих классов и использует их. Свойство <xref:System.Windows.Controls.InkCanvas> <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> имеет свойство, которое определяет, как отображается штрих при его рисовании.  
  
 Для пользовательских штрихов <xref:System.Windows.Controls.InkCanvas> рендеринга на сделать следующее:  
  
- Создайте класс, который <xref:System.Windows.Controls.InkCanvas>вытекает из .  
  
- Назначьте настроенную <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=nameWithType> на свойство.  
  
- Переопределите метод <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> . В этом методе удалите исходный штрих, который был добавлен в InkCanvas. Затем создайте пользовательский штрих, <xref:System.Windows.Controls.InkCanvas.Strokes%2A> добавьте его в свойство <xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs> и позвоните в базовый класс с новым, содержащим пользовательский штрих.  
  
 Следующий код C's <xref:System.Windows.Controls.InkCanvas> демонстрирует пользовательский класс, который использует настраиваемые <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> и собирает пользовательские штрихи.  
  
 [!code-csharp[AdvancedInkTopicsSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#9)]  
  
 В <xref:System.Windows.Controls.InkCanvas> можете иметь <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>более одного . Вы можете <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> добавить <xref:System.Windows.Controls.InkCanvas> несколько объектов <xref:System.Windows.UIElement.StylusPlugIns%2A> в свойство, добавив их в свойство.  
  
<a name="Conclusion"></a>
## <a name="conclusion"></a>Заключение  
 Вы можете настроить внешний вид чернил, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>производные свои собственные, <xref:System.Windows.Ink.Stroke>и <xref:System.Windows.Controls.InkCanvas> классы. Вместе эти классы гарантируют согласованность внешнего вида штриха в момент, когда пользователь рисует штрих, и после его сбора.  
  
## <a name="see-also"></a>См. также раздел

- [Дополнительная обработка рукописных данных](advanced-ink-handling.md)
