---
title: "Общие сведения об элементе управления ScrollViewer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "элементы управления, ScrollViewer"
  - "ScrollViewer - элемент управления, сведения об элементе управления ScrollViewer"
ms.assetid: 94a13b94-cfdf-4b12-a1aa-90cb50c6e9b9
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Общие сведения об элементе управления ScrollViewer
Часто содержимое в пользовательском интерфейсе занимает больше места, чем вмещает отображаемая область экрана компьютера.  Элемент управления <xref:System.Windows.Controls.ScrollViewer> предоставляет удобный способ включить прокрутку содержимого в приложениях [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  В данном разделе представлены сведения об элементе <xref:System.Windows.Controls.ScrollViewer> и приведены примеры его использования.  
  
 В этом разделе содержатся следующие подразделы.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
-   [Элемент управления ScrollViewer](#what_is_a_scrollviewer_element)  
  
-   [Физическая илогическая прокрутка](#scrollviewer_physical_vs_logical)  
  
-   [Определение и использование элемента ScrollViewer](#scrollviewer_markup_syntax_and_sample)  
  
-   [Стили элемента управления ScrollViewer](#scrollviewer_styling_scrollviewer)  
  
-   [Разбиение документов на страницы](#scrollviewer_scroll_vs_paginate)  
  
-   [Related Topics](#seeAlsoToggle)  
  
<a name="what_is_a_scrollviewer_element"></a>   
## Элемент управления ScrollViewer  
 Существуют два предопределенных элемента управления, обеспечивающих прокрутку в приложениях [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: <xref:System.Windows.Controls.Primitives.ScrollBar> и <xref:System.Windows.Controls.ScrollViewer>.  Элемент управления <xref:System.Windows.Controls.ScrollViewer> включает в себя горизонтальный и вертикальный элементы <xref:System.Windows.Controls.Primitives.ScrollBar> и контейнер содержимого \(например, элемент <xref:System.Windows.Controls.Panel>\) для отображения других видимых элементов в прокручиваемой области.  Чтобы использовать элемент <xref:System.Windows.Controls.Primitives.ScrollBar> для прокрутки содержимого, необходимо предварительно создать пользовательский объект.  Тем не менее, можно непосредственно использовать элемент <xref:System.Windows.Controls.ScrollViewer>, так как это составной элемент управления, включающий в себя функциональные возможности <xref:System.Windows.Controls.Primitives.ScrollBar>.  
  
 Элемент управления <xref:System.Windows.Controls.ScrollViewer> реагирует на команды мыши и клавиатуры и определяет множество методов для прокрутки содержимого на предопределенные значения приращения.  Для обнаружения изменений состояния элемента <xref:System.Windows.Controls.ScrollViewer> можно использовать событие <xref:System.Windows.Controls.ScrollViewer.ScrollChanged>.  
  
 Объект <xref:System.Windows.Controls.ScrollViewer> может иметь только одного потомка, обычно это элемент <xref:System.Windows.Controls.Panel>, в котором может размещаться коллекция элементов <xref:System.Windows.Controls.Panel.Children%2A>.  Свойство <xref:System.Windows.Controls.ContentPresenter.Content%2A> определяет единственного потомка <xref:System.Windows.Controls.ScrollViewer>.  
  
<a name="scrollviewer_physical_vs_logical"></a>   
## Физическая илогическая прокрутка  
 Физическая прокрутка используется для прокрутки на предопределенное приращение, которое обычно является значением, объявленным в пикселях.  Логическая прокрутка используется для прокрутки до следующего элемента в логическом дереве.  Физическая прокрутка является поведением прокрутки по умолчанию для большинства элементов <xref:System.Windows.Controls.Panel>.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает оба типа прокрутки.  
  
#### Интерфейс IScrollInfo  
 Интерфейс <xref:System.Windows.Controls.Primitives.IScrollInfo> представляет основную область прокрутки в <xref:System.Windows.Controls.ScrollViewer> или в производном элементе управления.  Интерфейс определяет свойства и методы прокрутки, которые могут быть реализованы элементами <xref:System.Windows.Controls.Panel>, требующими прокрутки на логическую единицу, а не на физическое приращение.  Приведение экземпляра класса <xref:System.Windows.Controls.Primitives.IScrollInfo> к производному экземпляру класса <xref:System.Windows.Controls.Panel> и последующее использование его методов прокрутки, обеспечивают удобный способ перехода к следующей логической единице в коллекции потомка вместо прокрутки на пиксельное приращение.  По умолчанию элемент управления <xref:System.Windows.Controls.ScrollViewer> поддерживает прокрутку на физические единицы.  
  
 Объекты <xref:System.Windows.Controls.StackPanel> и <xref:System.Windows.Controls.VirtualizingStackPanel> реализуют интерфейс <xref:System.Windows.Controls.Primitives.IScrollInfo> и имеют встроенную поддержку логической прокрутки.  Для элементов управления разметкой, имеющих встроенную поддержку логической прокрутки, можно реализовать физическую прокрутку, поместив хост\-элемент <xref:System.Windows.Controls.Panel> в <xref:System.Windows.Controls.ScrollViewer> и задав для свойства <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> значение `false`.  
  
 В следующем примере кода демонстрируется приведение экземпляра <xref:System.Windows.Controls.Primitives.IScrollInfo> к <xref:System.Windows.Controls.StackPanel> и использование методов прокрутки содержимого \(<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> и <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>\), определенных интерфейсом.  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>   
## Определение и использование элемента ScrollViewer  
 В следующем примере объект <xref:System.Windows.Controls.ScrollViewer> создается в окне, содержащем текст и прямоугольник.  Элементы <xref:System.Windows.Controls.Primitives.ScrollBar> выводятся только в случае необходимости.  При изменении размера окна элементы <xref:System.Windows.Controls.Primitives.ScrollBar> отображаются и исчезают согласно изменению значений свойств <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> и <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A>.  
  
 [!code-cpp[ScrollViewer#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xml[ScrollViewer#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>   
## Стили элемента управления ScrollViewer  
 Как и к остальным элементам управления в Windows Presentation Foundation, к <xref:System.Windows.Controls.ScrollViewer> могут быть применены различные стили для изменения поведения элемента управления при его отрисовки.  Дополнительные сведения о стилях элементов управления см. в разделе [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
<a name="scrollviewer_scroll_vs_paginate"></a>   
## Разбиение документов на страницы  
 Для содержимого документа альтернативой прокрутке является контейнер документа, поддерживающий разбиение на страницы.  Класс <xref:System.Windows.Documents.FlowDocument> предназначен для документов, которые размещаются в элементе управления просмотра, например в <xref:System.Windows.Controls.FlowDocumentPageViewer>, который поддерживает разбиение содержимого на несколько страниц, что устраняет необходимость в прокрутке.  <xref:System.Windows.Controls.DocumentViewer> предоставляет решение для просмотра содержимого <xref:System.Windows.Documents.FixedDocument>, в котором для вывода содержимого вне области отображения применяется традиционная прокрутка.  
  
 Дополнительные сведения о форматах документа и параметрах представления см. в разделе [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
## См. также  
 <xref:System.Windows.Controls.ScrollViewer>   
 <xref:System.Windows.Controls.Primitives.ScrollBar>   
 <xref:System.Windows.Controls.Primitives.IScrollInfo>   
 [Create a Scroll Viewer](http://msdn.microsoft.com/ru-ru/c8e46af7-b417-441b-aa30-791cbdbd43ef)   
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Стили и шаблоны элемента ScrollBar](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)   
 [Элементы управления](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)