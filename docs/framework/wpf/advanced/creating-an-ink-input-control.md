---
title: "Создание элемента управления рукописным вводом"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7054728e8bf54a7cf7b71ea1224cab6a352176d4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="creating-an-ink-input-control"></a>Создание элемента управления рукописным вводом
Можно создать пользовательский элемент управления, динамически и статически отображающий рукописный ввод. Отображения рукописного ввода, то есть, как пользователь штриха, вызывая рукописный ввод в «поток» из планшетное перо и после него отображается добавляется в элемент управления, либо с помощью пера, вставленный из буфера обмена или загрузке из файла. Для динамического отображения рукописного ввода, необходимо использовать элемент управления <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>. Для статического отображения рукописного ввода, необходимо переопределить методы событий пера (<xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusMove%2A>, и <xref:System.Windows.UIElement.OnStylusUp%2A>) для сбора <xref:System.Windows.Input.StylusPoint> данных, создания штрихов и добавить их к <xref:System.Windows.Controls.InkPresenter> (который отображает рукописного текста на элементе управления).  
  
 В этом разделе содержатся следующие подразделы:  
  
-   [Как: сбора данных точки пера и создания штрихов рукописного ввода](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
-   [Как: разрешить принимать входные данные от мыши элемента управления](#EnablingYourControlToAcceptInputTromTheMouse)  
  
-   [Совместное размещение](#PuttingItTogether)  
  
-   [С помощью дополнительные подключаемые модули и DynamicRenderers](#UsingAdditionalPluginsAndDynamicRenderers)  
  
-   [Заключение](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>   
## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a>Как: сбора данных точки пера и создания штрихов рукописного ввода  
 Чтобы создать элемент управления, который собирает и управляет рукописного ввода штрихов выполните следующее:  
  
1.  Производный класс <xref:System.Windows.Controls.Control> или одного из классов, производный от <xref:System.Windows.Controls.Control>, такие как <xref:System.Windows.Controls.Label>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2.  Добавить <xref:System.Windows.Controls.InkPresenter> класса и установите <xref:System.Windows.Controls.ContentControl.Content%2A> свойство к новому <xref:System.Windows.Controls.InkPresenter>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3.  Присоединение <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> из <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> для <xref:System.Windows.Controls.InkPresenter> путем вызова <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> метода и добавьте <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> для <xref:System.Windows.UIElement.StylusPlugIns%2A> коллекции. Это позволяет <xref:System.Windows.Controls.InkPresenter> для отображения рукописного ввода, так как происходит накопление данных точки пера элементом управления.  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4.  Переопределите метод <xref:System.Windows.UIElement.OnStylusDown%2A>.  В этом методе захвата пера вызовом <xref:System.Windows.Input.Stylus.Capture%2A>. При захвате пера, элемент управления будет продолжать получать <xref:System.Windows.UIElement.StylusMove> и <xref:System.Windows.UIElement.StylusUp> события даже в том случае, если перо покидает границы элемента управления. Это не является строго обязательным, но почти всегда желательно для удобства работы пользователей. Создайте новый <xref:System.Windows.Input.StylusPointCollection> для сбора <xref:System.Windows.Input.StylusPoint> данных. Наконец, добавьте начальный набор <xref:System.Windows.Input.StylusPoint> данные <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5.  Переопределить <xref:System.Windows.UIElement.OnStylusMove%2A> метода и добавьте <xref:System.Windows.Input.StylusPoint> данные <xref:System.Windows.Input.StylusPointCollection> , созданного ранее.  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6.  Переопределить <xref:System.Windows.UIElement.OnStylusUp%2A> метод и создать новую <xref:System.Windows.Ink.Stroke> с <xref:System.Windows.Input.StylusPointCollection> данных. Добавьте новые <xref:System.Windows.Ink.Stroke> созданной вами для <xref:System.Windows.Controls.InkPresenter.Strokes%2A> коллекцию <xref:System.Windows.Controls.InkPresenter> и освободить захват пера.  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>   
## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a>Как: разрешить принимать входные данные от мыши элемента управления  
 Если добавить предыдущий элемент управления в приложение, запустите его и использовать мышь в качестве устройства ввода, можно заметить, что штрихи не сохраняются. Для сохранения штрихов рукописного ввода, когда указатель мыши используется как устройство ввода выполните следующее:  
  
1.  Переопределить <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> и создайте новый <xref:System.Windows.Input.StylusPointCollection> получить позицию указателя мыши в момент возникновения события и создать <xref:System.Windows.Input.StylusPoint> с помощью точки данных и добавьте <xref:System.Windows.Input.StylusPoint> для <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2.  Переопределите метод <xref:System.Windows.UIElement.OnMouseMove%2A>. Получает позицию указателя мыши при возникновении события и создать <xref:System.Windows.Input.StylusPoint> с использованием точки данных.  Добавить <xref:System.Windows.Input.StylusPoint> для <xref:System.Windows.Input.StylusPointCollection> объекта, которое было создано ранее.  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3.  Переопределите метод <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A>.  Создайте новый <xref:System.Windows.Ink.Stroke> с <xref:System.Windows.Input.StylusPointCollection> данных и добавьте новые <xref:System.Windows.Ink.Stroke> созданной вами для <xref:System.Windows.Controls.InkPresenter.Strokes%2A> коллекцию <xref:System.Windows.Controls.InkPresenter>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>   
## <a name="putting-it-together"></a>Совместное размещение  
 Следующий пример является настраиваемым сбора данных рукописного ввода, когда пользователь использует перо или мышь.  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>   
## <a name="using-additional-plug-ins-and-dynamicrenderers"></a>С помощью дополнительные подключаемые модули и DynamicRenderers  
 Как и InkCanvas, пользовательский элемент управления может иметь пользовательские <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> и дополнительные <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> объектов. Добавить их в <xref:System.Windows.UIElement.StylusPlugIns%2A> коллекции. Порядок <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> объекты в <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> влияет на внешний вид рукописного ввода при его отрисовке. Предположим, что имеется <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> вызывается `dynamicRenderer` и пользовательское <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> вызывается `translatePlugin` , смещает рукописный ввод от пера. Если `translatePlugin` является первым <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> в <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, и `dynamicRenderer` — вторым, будет перенесено рукописный ввод «потоки», при перемещении пера. Если `dynamicRenderer` является первым, а `translatePlugin` — вторым, не будет перенесено рукописного ввода, пока пользователь отрывает перо.  
  
<a name="AdvancedInkHandling_Conclusion"></a>   
## <a name="conclusion"></a>Заключение  
 Можно создать элемент управления, который собирает и отображает рукописные данные путем переопределения методов событий пера. Можно создать собственный элемент управления, создания своих собственных производных <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> классы и их вставка в <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, можно реализовать поведение, практически для любых возможное сопоставление с рукописного ввода. У вас есть доступ к <xref:System.Windows.Input.StylusPoint> данных по мере доступными, предоставляя возможность настройки <xref:System.Windows.Input.Stylus> входные данные и отображать его на экране, в зависимости от приложения. Если у вас такого низкоуровневого доступа к <xref:System.Windows.Input.StylusPoint> данных, можно реализовать коллекцию рукописного ввода и отображать ее с оптимальной производительности приложения.  
  
## <a name="see-also"></a>См. также  
 [Дополнительная обработка рукописных фрагментов](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)  
 [Доступ и управление ввода с помощью пера](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
