---
title: "Перехват ввода, осуществляемого пером | Microsoft Docs"
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
  - "архитектура, System.Windows.Input.StylusPlugIns"
  - "InkCanvas, добавление подключаемых модулей"
  - "подключаемые модули, перо"
  - "StylusPlugIns - архитектура"
  - "System.Windows.Input.StylusPlugIns - архитектура"
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Перехват ввода, осуществляемого пером
Архитектура <xref:System.Windows.Input.StylusPlugIns> предоставляет механизм реализации низкоуровнего управления входными данными <xref:System.Windows.Input.Stylus> и создания объектов цифровых рукописных данных <xref:System.Windows.Ink.Stroke>.  Класс <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> предоставляет механизм реализации пользовательского поведения и применения его к потоку данных, поступающих от устройства пера, для обеспечения оптимальной производительности.  
  
 В этом разделе содержатся следующие подразделы:  
  
-   [Архитектура](#Architecture)  
  
-   [Реализация подключаемых модулей пера](#ImplementingStylusPlugins)  
  
-   [Добавление подключаемого модуля к InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
-   [Заключение](#Conclusion)  
  
<a name="Architecture"></a>   
## Архитектура  
 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> является развитием технологии API [StylusInput](http://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409), описанной в [Осуществление доступа и управления перьевым вводом](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409), в [Microsoft Windows XP Tablet PC Edition Software Development Kit 1.7](http://go.microsoft.com/fwlink/?LinkId=11782&clcid=0x409).  
  
 Каждый <xref:System.Windows.UIElement> имеет свойство <xref:System.Windows.UIElement.StylusPlugIns%2A>, представляющее собой <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.  Можно добавить <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> в свойство <xref:System.Windows.UIElement.StylusPlugIns%2A> элемента для обработки данных <xref:System.Windows.Input.StylusPoint> при их создании.  Данные <xref:System.Windows.Input.StylusPoint> состоят из всех свойств, поддерживаемых системным дигитайзером, включая данные точки <xref:System.Windows.Input.StylusPoint.X%2A> и <xref:System.Windows.Input.StylusPoint.Y%2A>, а также данные <xref:System.Windows.Input.StylusPoint.PressureFactor%2A>.  
  
 Объекты <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> вставляются непосредственно в поток данных, поступающих от устройства <xref:System.Windows.Input.Stylus>, при добавлении свойства <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> к свойству <xref:System.Windows.UIElement.StylusPlugIns%2A>.  Порядок добавления подключаемых модулей к коллекции <xref:System.Windows.UIElement.StylusPlugIns%2A> определяет порядок, в котором они будут получать данные <xref:System.Windows.Input.StylusPoint>.  Например, если добавить подключаемый модуль фильтра, ограничивающий входные данные определенной областью, а затем добавить подключаемый модуль, который распознает жесты, то последний будет получать отфильтрованные данные <xref:System.Windows.Input.StylusPoint>.  
  
<a name="ImplementingStylusPlugins"></a>   
## Реализация подключаемых модулей пера  
 Чтобы реализовать подключаемый модуль, создайте производный класс от <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>.  Этот класс применяется к потоку данных, поступающему из <xref:System.Windows.Input.Stylus>.  В этом классе можно изменять значения данных <xref:System.Windows.Input.StylusPoint>.  
  
> [!CAUTION]
>  Если <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> создает или вызывает исключение, приложение будет закрыто.  Необходимо тщательно протестировать элементы управления, которые потребляют <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>, и использовать их только в случае уверенности, что <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> не создаст исключение.  
  
 В следующем примере показан подключаемый модуль, который ограничивает входные данные пера путем изменения значений <xref:System.Windows.Input.StylusPoint.X%2A> и <xref:System.Windows.Input.StylusPoint.Y%2A> в данных <xref:System.Windows.Input.StylusPoint> при их поступлении от устройства <xref:System.Windows.Input.Stylus>.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## Добавление подключаемого модуля к InkCanvas  
 Самым простым способом использовать пользовательский подключаемый модуль является реализация класса, производного от InkCanvas, и добавление его к свойству <xref:System.Windows.UIElement.StylusPlugIns%2A>.  
  
 В следующем примере показан пользовательский <xref:System.Windows.Controls.InkCanvas>, который фильтрует рукописные данные.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 Если добавить `FilterInkCanvas` к приложению и запустить его, то можно заметить, что рукописные данные не ограничены областью, пока пользователь не завершит штрих.  Это происходит потому, что <xref:System.Windows.Controls.InkCanvas> имеет свойство <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>, которое представляет собой <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> и уже является элементом коллекции <xref:System.Windows.UIElement.StylusPlugIns%2A>.  Пользовательские <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>, добавляемые в коллекцию <xref:System.Windows.UIElement.StylusPlugIns%2A>, получают данные <xref:System.Windows.Input.StylusPoint> после получения данных <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.  В результате данные <xref:System.Windows.Input.StylusPoint> не будут фильтроваться, пока пользователь не поднимет перо, чтобы завершить штрих.  Для фильтрации рукописных данных, рисуемых пользователем, необходимо вставить `FilterPlugin` перед <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.  
  
 Следующий код C\# демонстрирует пользовательский <xref:System.Windows.Controls.InkCanvas>, который фильтрует рукописные данные по мере их написания.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## Заключение  
 Путем создания своих собственных производных классов <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> и вставки их в коллекции <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> можно значительно улучшить обработку цифровых рукописных данных.  После создания данных <xref:System.Windows.Input.StylusPoint> они становятся доступными, предоставляя возможность настройки ввода <xref:System.Windows.Input.Stylus>.  Наличие такого низкоуровневого доступа к данным <xref:System.Windows.Input.StylusPoint>, позволяет реализовать сбор и отрисовку рукописного ввода с оптимальной для приложения производительностью.  
  
## См. также  
 [Дополнительная обработка рукописных данных](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)   
 [Accessing and Manipulating Pen Input](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)