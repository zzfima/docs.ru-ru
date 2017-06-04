---
title: "Создание элемента управления рукописным вводом | Microsoft Docs"
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
  - "прием рукописного ввода"
  - "DynamicRenderer - объекты"
  - "элементы управления для рукописного ввода"
  - "рукописный ввод, прием"
  - "рукописный ввод, управление"
  - "рукописный ввод, отрисовка"
  - "ввод с мыши, прием"
  - "управление рукописным вводом"
  - "ввод мыши, прием"
  - "отрисовка рукописных данных"
  - "StylusPlugIn - объекты"
ms.assetid: c31f3a67-cb3f-4ded-af9e-ed21f6575b26
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Создание элемента управления рукописным вводом
Можно создать настраиваемый элемент управления, динамически и статически отображающий рукописный ввод.  То есть рукописные данные отображаются при вводе пользователем штриха, визуально рукописный ввод "выплывает" из\-под пера планшета и отображается после того, как добавляется в элемент управления, либо с помощью пера планшета, из буфер обмена, либо при загрузке из файла.  Для динамического отображения рукописного ввода, элемент управления должен использовать <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.  Для статического отображения рукописных данных необходимо переопределить методы событий пера \(<xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusMove%2A> и <xref:System.Windows.UIElement.OnStylusUp%2A>\) для сбора данных <xref:System.Windows.Input.StylusPoint> и создания штрихов, и добавить их в <xref:System.Windows.Controls.InkPresenter> \(который отображает рукописные данные в элементе управления\).  
  
 В этом разделе содержатся следующие подразделы:  
  
-   [Практическое руководство. Сбор данных о точках пера и создание росчерков пера](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
-   [Практическое руководство. Включение приема элементом управления ввода при помощи мыши](#EnablingYourControlToAcceptInputTromTheMouse)  
  
-   [Сборка](#PuttingItTogether)  
  
-   [Использование дополнительных подключаемых модулей и DynamicRenderer](#UsingAdditionalPluginsAndDynamicRenderers)  
  
-   [Заключение](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>   
## Практическое руководство. Сбор данных о точках пера и создание росчерков пера  
 Для создания элемента управления, собирающего и управляющего штрихами рукописного ввода выполните следующие действия.  
  
1.  Создайте класс, производный от <xref:System.Windows.Controls.Control> или от одного из классов, производных от <xref:System.Windows.Controls.Control>, например, <xref:System.Windows.Controls.Label>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2.  Добавьте <xref:System.Windows.Controls.InkPresenter> в класс и задайте свойству <xref:System.Windows.Controls.ContentControl.Content%2A> новое значение <xref:System.Windows.Controls.InkPresenter>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3.  Присоедините <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> для <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> к <xref:System.Windows.Controls.InkPresenter>, вызвав метод <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A>, и добавьте <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> в коллекцию <xref:System.Windows.UIElement.StylusPlugIns%2A>.  Это позволит <xref:System.Windows.Controls.InkPresenter> отображать рукописные данные как данные точек пера, собираемые элементом управления.  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4.  Переопределите метод <xref:System.Windows.UIElement.OnStylusDown%2A>.  В этом методе выполните перехват пера, вызвав <xref:System.Windows.Input.Stylus.Capture%2A>.  При перехвате пера элемент управления будет продолжать получать события <xref:System.Windows.UIElement.StylusMove> и <xref:System.Windows.UIElement.StylusUp> даже в том случае, если перо покидает границы элемента управления.  Это не является строго обязательным, но почти всегда желательно для повышения удобства работы пользователя.  Создайте новый объект <xref:System.Windows.Input.StylusPointCollection> для сбора данных <xref:System.Windows.Input.StylusPoint>.  Наконец, добавьте исходный набор данных <xref:System.Windows.Input.StylusPoint> в <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5.  Переопределите метод <xref:System.Windows.UIElement.OnStylusMove%2A> и добавьте данные <xref:System.Windows.Input.StylusPoint> в созданный ранее объект <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6.  Переопределите метод <xref:System.Windows.UIElement.OnStylusUp%2A> и создайте новый <xref:System.Windows.Ink.Stroke> с данными <xref:System.Windows.Input.StylusPointCollection>.  Добавьте новый созданный объект <xref:System.Windows.Ink.Stroke> в коллекцию <xref:System.Windows.Controls.InkPresenter.Strokes%2A> для <xref:System.Windows.Controls.InkPresenter> и освободите перо.  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>   
## Практическое руководство. Включение приема элементом управления ввода при помощи мыши  
 Если добавить предыдущий элемент управления в приложение, запустить его и использовать мышь в качестве устройства ввода, можно заметить, что штрихи не сохраняются.  Для сохранения штрихов при использовании мыши в качестве устройства ввода выполните следующие действия:  
  
1.  Переопределите <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> и создайте новый объект <xref:System.Windows.Input.StylusPointCollection>. Получите координаты указателя мыши в момент возникновения события и создайте <xref:System.Windows.Input.StylusPoint>, используя данные точки, и добавьте <xref:System.Windows.Input.StylusPoint> в <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2.  Переопределите метод <xref:System.Windows.UIElement.OnMouseMove%2A>.  При возникновении события получите положение указателя мыши и создайте <xref:System.Windows.Input.StylusPoint>, используя данные точки.  Добавьте <xref:System.Windows.Input.StylusPoint> в созданный ранее объект <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3.  Переопределите метод <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A>.  Создайте новый объект <xref:System.Windows.Ink.Stroke> с данными <xref:System.Windows.Input.StylusPointCollection> и добавьте новый созданный объект <xref:System.Windows.Ink.Stroke> в коллекцию <xref:System.Windows.Controls.InkPresenter.Strokes%2A> из <xref:System.Windows.Controls.InkPresenter>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>   
## Сборка  
 В следующем примере представлен пользовательский элемент управления, собирающий рукописные данные, если пользователь использует мышь или перо.  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>   
## Использование дополнительных подключаемых модулей и DynamicRenderer  
 Как и InkCanvas, пользовательский элемент управления может иметь пользовательские объекты <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> и дополнительные объекты <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.  Добавьте эти объекты в коллекцию <xref:System.Windows.UIElement.StylusPlugIns%2A>.  Порядок объектов <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> в <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> влияет на внешний вид рукописных данных при их отображении.  Предположим, имеется <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> с именем `dynamicRenderer` и пользовательский <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> с именем `translatePlugin`, который смещает рукописный ввод, поступающий от планшетного пера.  Если `translatePlugin` является первым <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> в <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, а `dynamicRenderer` — вторым, рукописный ввод будет смещаться соответственно перемещениям мыши.  Если `dynamicRenderer` является первым, а `translatePlugin` — вторым, рукописные данные не будут смещаться до тех пор, пока пользователь не поднимет перо.  
  
<a name="AdvancedInkHandling_Conclusion"></a>   
## Заключение  
 Можно создать элемент управления, который собирает и отображает рукописные данные, переопределяя методы событий пера.  Создав собственный элемент управления, собственные производные классы <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> и вставив их в <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, можно виртуально реализовать любую возможную модель поведения цифрового рукописного ввода.  Имеется доступ к данным <xref:System.Windows.Input.StylusPoint> при их создании, благодаря чему приобретается возможность настроить ввод с помощью <xref:System.Windows.Input.Stylus> и отображать вводимые данные на экране так, как нужно в приложении.  Поскольку есть такой доступ низкого уровня к данным <xref:System.Windows.Input.StylusPoint>, можно реализовать коллекцию рукописного ввода и отображать ее с оптимальной для приложения производительностью.  
  
## См. также  
 [Дополнительная обработка рукописных данных](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)   
 [Accessing and Manipulating Pen Input](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)