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
ms.openlocfilehash: 98b2abf813a232e36b80683254174b12b97659bb
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095220"
---
# <a name="creating-an-ink-input-control"></a>Создание элемента управления рукописным вводом
Можно создать пользовательский элемент управления, динамически и статически обрабатывающий рукописный ввод. То есть, прорисовка рукописного ввода в качестве пользователя рисует штрих, что приводит к тому, что рукописный ввод помещается в «Flow» из пера планшета, а после добавления к элементу управления отображается рукописный ввод с помощью пера планшета, вставленного из буфера обмена или загруженного из файла. Для динамического отображения рукописного ввода элемент управления должен использовать <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>. Для статического отображения рукописного ввода необходимо переопределить методы событий пера (<xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusMove%2A>и <xref:System.Windows.UIElement.OnStylusUp%2A>) для получения данных <xref:System.Windows.Input.StylusPoint>, создания штрихов и добавления их в <xref:System.Windows.Controls.InkPresenter> (который визуализирует рукописный ввод в элементе управления).  
  
 В этом разделе содержатся следующие подразделы:  
  
- [Как получить данные точки пера и создать рукописные штрихи](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
- [Как разрешить элементу управления принимать входные данные от мыши](#EnablingYourControlToAcceptInputTromTheMouse)  
  
- [Совместное размещение](#PuttingItTogether)  
  
- [Использование дополнительных подключаемых модулей и Динамикрендерерс](#UsingAdditionalPluginsAndDynamicRenderers)  
  
- [Заключение](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>   
## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a>Как получить данные точки пера и создать рукописные штрихи  
 Чтобы создать элемент управления, собирающий рукописные штрихи и управляющий ими, выполните следующие действия.  
  
1. Создайте производный класс от <xref:System.Windows.Controls.Control> или одного из классов, производных от <xref:System.Windows.Controls.Control>, например <xref:System.Windows.Controls.Label>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2. Добавьте <xref:System.Windows.Controls.InkPresenter> в класс и задайте для свойства <xref:System.Windows.Controls.ContentControl.Content%2A> новое <xref:System.Windows.Controls.InkPresenter>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3. Присоедините <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> к <xref:System.Windows.Controls.InkPresenter>, вызвав метод <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> и добавив <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> в коллекцию <xref:System.Windows.UIElement.StylusPlugIns%2A>. Это позволяет <xref:System.Windows.Controls.InkPresenter> отображать рукописные данные в виде точек пера, собираемых элементом управления.  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4. Переопределите метод <xref:System.Windows.UIElement.OnStylusDown%2A> .  В этом методе запишите перо с помощью вызова <xref:System.Windows.Input.Stylus.Capture%2A>. Записывая перо, элемент управления будет продолжать принимать <xref:System.Windows.UIElement.StylusMove> и <xref:System.Windows.UIElement.StylusUp> события, даже если перо покидает границы элемента управления. Это не является строго обязательным, но почти всегда желательно для удобства пользователя. Создайте новый <xref:System.Windows.Input.StylusPointCollection> для сбора <xref:System.Windows.Input.StylusPoint> данных. Наконец, добавьте исходный набор <xref:System.Windows.Input.StylusPoint> данных в <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5. Переопределите метод <xref:System.Windows.UIElement.OnStylusMove%2A> и добавьте <xref:System.Windows.Input.StylusPoint> данные в созданный ранее объект <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6. Переопределите метод <xref:System.Windows.UIElement.OnStylusUp%2A> и создайте новый <xref:System.Windows.Ink.Stroke> с данными <xref:System.Windows.Input.StylusPointCollection>. Добавьте новую созданную <xref:System.Windows.Ink.Stroke> в коллекцию <xref:System.Windows.Controls.InkPresenter.Strokes%2A> <xref:System.Windows.Controls.InkPresenter> и захват пера выпуска.  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>   
## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a>Как разрешить элементу управления принимать входные данные от мыши  
 Если добавить предыдущий элемент управления в приложение, запустить его и использовать мышь как устройство ввода, вы увидите, что штрихи не сохраняются. Чтобы сохранить штрихи при использовании мыши в качестве устройства ввода, выполните следующие действия.  
  
1. Переопределите <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> и создайте новый <xref:System.Windows.Input.StylusPointCollection> получите позицию мыши при возникновении события и создайте <xref:System.Windows.Input.StylusPoint> с помощью данных Point и добавьте <xref:System.Windows.Input.StylusPoint> в <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2. Переопределите метод <xref:System.Windows.UIElement.OnMouseMove%2A> . Получение позиции мыши при возникновении события и создание <xref:System.Windows.Input.StylusPoint> с помощью данных точки.  Добавьте <xref:System.Windows.Input.StylusPoint> в созданный ранее объект <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3. Переопределите метод <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> .  Создайте новый <xref:System.Windows.Ink.Stroke> с <xref:System.Windows.Input.StylusPointCollection>ными данными и добавьте новое созданное <xref:System.Windows.Ink.Stroke> в коллекцию <xref:System.Windows.Controls.InkPresenter.Strokes%2A> <xref:System.Windows.Controls.InkPresenter>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>   
## <a name="putting-it-together"></a>Совместное размещение  
 В следующем примере показан пользовательский элемент управления, собирающий рукописный ввод, когда пользователь использует мышь или перо.  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>   
## <a name="using-additional-plug-ins-and-dynamicrenderers"></a>Использование дополнительных подключаемых модулей и Динамикрендерерс  
 Как и InkCanvas, Пользовательский элемент управления может иметь пользовательские <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> и дополнительные объекты <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>. Добавьте их в коллекцию <xref:System.Windows.UIElement.StylusPlugIns%2A>. Порядок объектов <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> в <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> влияет на внешний вид рукописного ввода при его отрисовке. Предположим, что имеется <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> с именем `dynamicRenderer` и настраиваемый <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> с именем `translatePlugin`, который смещает рукописный ввод от пера планшета. Если `translatePlugin` является первым <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>ом в <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, а `dynamicRenderer` является вторым, рукописный ввод «Flows» будет смещен по мере того, как пользователь перемещает перо. Если `dynamicRenderer` является первым, а `translatePlugin` — во второй, рукописные данные не будут смещены, пока пользователь не отрывает перо.  
  
<a name="AdvancedInkHandling_Conclusion"></a>   
## <a name="conclusion"></a>Заключение  
 Можно создать элемент управления, собирающий и визуализирующий рукописный ввод, переопределяя методы событий пера. Создавая собственный элемент управления, производя собственные классы <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> и вставляя их в <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, вы можете реализовать практически любое поведение, которое можно представить с помощью цифрового рукописного ввода. У вас есть доступ к <xref:System.Windows.Input.StylusPoint>ным данным по мере их создания, что дает возможность настроить <xref:System.Windows.Input.Stylus> входные данные и отобразить их на экране в соответствии с вашими приложениями. Так как у вас есть низкоуровневый доступ к <xref:System.Windows.Input.StylusPoint>ным данным, вы можете реализовать сбор рукописных данных и визуализировать их с оптимальной производительностью для вашего приложения.  
  
## <a name="see-also"></a>См. также раздел

- [Дополнительная обработка рукописных фрагментов](advanced-ink-handling.md)
- [Доступ к вводу с помощью пера и управление им](https://docs.microsoft.com/previous-versions/ms818317(v=msdn.10))
