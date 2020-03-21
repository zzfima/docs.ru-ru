---
title: Создание элемента управления рукописным вводом
ms.date: 03/30/2017
helpviewer_keywords:
- ink strokes [WPF], managing
- managing ink strokes [WPF]
- ink input control [WPF]
- input from mouse [WPF], accepting
- mouse input [WPF], accepting
- ink [WPF], rendering
- ink strokes [WPF], collecting
- rendering ink [WPF]
- collecting ink strokes [WPF]
- DynamicRenderer objects [WPF]
- StylusPlugIn objects [WPF]
ms.assetid: c31f3a67-cb3f-4ded-af9e-ed21f6575b26
ms.openlocfilehash: 394318488b0afb8e043389e0abc3f51dce8604c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186285"
---
# <a name="creating-an-ink-input-control"></a>Создание элемента управления рукописным вводом
Можно создать пользовательский элемент управления, который динамически и статично визуалируется чернилами. То есть, визуализировать чернила, как пользователь рисует инсульт, в результате чего чернила, как представляется, "поток" из пера планшета, и отображать чернила после того, как он добавляется в управление, либо через перо планшета, вставленные из Clipboard, или загружены из файла. Для динамической визуализации чернил элемент <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>управления должен использовать. Чтобы статически визуализировать чернила, необходимо переопределить<xref:System.Windows.UIElement.OnStylusDown%2A> <xref:System.Windows.UIElement.OnStylusMove%2A>методы <xref:System.Windows.UIElement.OnStylusUp%2A>события <xref:System.Windows.Input.StylusPoint> стилуса (, и) для <xref:System.Windows.Controls.InkPresenter> сбора данных, создания штрихов и добавления их в (который отображает чернила на элементе управления).  
  
 В этом разделе содержатся следующие подразделы:  
  
- [Как: Собирать данные Stylus Point и создавать чернила Инсульты](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
- [Как: Включить ваш контроль, чтобы принять вход от мыши](#EnablingYourControlToAcceptInputTromTheMouse)  
  
- [Подведем итог](#PuttingItTogether)  
  
- [Использование дополнительных плагинов и динамических рендереров](#UsingAdditionalPluginsAndDynamicRenderers)  
  
- [Заключение](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>
## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a>Как: Собирать данные Stylus Point и создавать чернила Инсульты  
 Для создания элемента управления, который собирает и управляет штрихами чернил, сделайте следующее:  
  
1. Выизвените класс из <xref:System.Windows.Controls.Control> или <xref:System.Windows.Controls.Control>один <xref:System.Windows.Controls.Label>из классов, полученных из, таких как .  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2. Добавьте <xref:System.Windows.Controls.InkPresenter> в класс и <xref:System.Windows.Controls.ContentControl.Content%2A> установите <xref:System.Windows.Controls.InkPresenter>свойство к новому .  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3. <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> Прикрепите <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> к <xref:System.Windows.Controls.InkPresenter> методу, <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> позвонив <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> по <xref:System.Windows.UIElement.StylusPlugIns%2A> методу, и добавьте в коллекцию. Это позволяет <xref:System.Windows.Controls.InkPresenter> отображать чернила, как стилус точки данных собирается вашим контролем.  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4. Переопределите метод <xref:System.Windows.UIElement.OnStylusDown%2A> .  В этом методе, захват стилус <xref:System.Windows.Input.Stylus.Capture%2A>с призывом к . Захватив стилус, ваш контроль будет <xref:System.Windows.UIElement.StylusMove> продолжать <xref:System.Windows.UIElement.StylusUp> получать и события, даже если стилус выходит из границ управления. Это не является строго обязательным, но почти всегда хотел для хорошего пользовательского опыта. Создайте <xref:System.Windows.Input.StylusPointCollection> новый <xref:System.Windows.Input.StylusPoint> для сбора данных. Наконец, добавьте <xref:System.Windows.Input.StylusPoint> исходный <xref:System.Windows.Input.StylusPointCollection>набор данных в .  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5. Переопределить <xref:System.Windows.UIElement.OnStylusMove%2A> метод и <xref:System.Windows.Input.StylusPoint> добавить <xref:System.Windows.Input.StylusPointCollection> данные к объекту, созданного ранее.  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6. Переопределить <xref:System.Windows.UIElement.OnStylusUp%2A> метод и создать <xref:System.Windows.Ink.Stroke> новый с данными. <xref:System.Windows.Input.StylusPointCollection> Добавьте <xref:System.Windows.Ink.Stroke> новое, созданное в коллекцию <xref:System.Windows.Controls.InkPresenter.Strokes%2A> захвата стилуса <xref:System.Windows.Controls.InkPresenter> и выпустите его.  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>
## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a>Как: Включить ваш контроль, чтобы принять вход от мыши  
 Если вы добавите предыдущий элемент управления в приложение, запустите его и используете мышь в качестве устройства ввода, вы заметите, что штрихи не сохраняются. Для сохранения штрихов при использовании мыши в качестве вхотвора устройства делают следующее:  
  
1. Переопределить <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> и создать <xref:System.Windows.Input.StylusPointCollection> новое Получить положение мыши, когда произошло <xref:System.Windows.Input.StylusPoint> событие и создать <xref:System.Windows.Input.StylusPoint> использование <xref:System.Windows.Input.StylusPointCollection>точечных данных и добавить в .  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2. Переопределите метод <xref:System.Windows.UIElement.OnMouseMove%2A> . Получите положение мыши, когда произошло <xref:System.Windows.Input.StylusPoint> событие, создайте с помощью точечных данных.  Добавьте <xref:System.Windows.Input.StylusPoint> объект, созданный <xref:System.Windows.Input.StylusPointCollection> ранее.  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3. Переопределите метод <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> .  Создайте <xref:System.Windows.Ink.Stroke> новый <xref:System.Windows.Input.StylusPointCollection> с данными <xref:System.Windows.Ink.Stroke> и добавьте <xref:System.Windows.Controls.InkPresenter.Strokes%2A> новый <xref:System.Windows.Controls.InkPresenter>созданный в коллекцию .  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>
## <a name="putting-it-together"></a>Подведем итог  
 Следующим примером является пользовательский элемент управления, который собирает чернила, когда пользователь использует либо мышь, либо ручку.  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>
## <a name="using-additional-plug-ins-and-dynamicrenderers"></a>Использование дополнительных плагинов и динамических рендереров  
 Как и InkCanvas, пользовательский <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> элемент <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> управления может иметь пользовательские и дополнительные объекты. Добавьте их <xref:System.Windows.UIElement.StylusPlugIns%2A> в коллекцию. Порядок объектов <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> в <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> типе влияет на внешний вид чернил при их визуализации. Предположим, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> у `dynamicRenderer` вас <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> есть `translatePlugin` называется и обычай называется, что компенсирует чернила из пера планшета. Если `translatePlugin` это <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> первый <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>в `dynamicRenderer` , и второй, чернила, что "потоки" будут компенсированы, как пользователь перемещает перо. Если `dynamicRenderer` он первый, а `translatePlugin` второй, чернила не будут смещены до тех пор, пока пользователь не поднимет ручку.  
  
<a name="AdvancedInkHandling_Conclusion"></a>
## <a name="conclusion"></a>Заключение  
 Можно создать элемент управления, который собирает и визуалирует чернила, переопределяя методы события стилуса. Создавая свой собственный контроль, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> производные свои собственные <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>классы, и вставив их в , вы можете реализовать практически любое поведение можно себе представить с цифровыми чернилами. У вас есть <xref:System.Windows.Input.StylusPoint> доступ к данным по мере их <xref:System.Windows.Input.Stylus> создания, что дает вам возможность настроить входные данные и сделать его на экране по мере необходимости для вашего приложения. Поскольку у вас такой низкоуровневый доступ к <xref:System.Windows.Input.StylusPoint> данным, вы можете реализовать сбор чернил и сделать его с оптимальной производительностью для вашего приложения.  
  
## <a name="see-also"></a>См. также раздел

- [Дополнительная обработка рукописных данных](advanced-ink-handling.md)
- [Доступ и манипулирование ввозами пера](https://docs.microsoft.com/previous-versions/ms818317(v=msdn.10))
