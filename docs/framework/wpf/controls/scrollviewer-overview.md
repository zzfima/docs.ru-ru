---
title: Общие сведения об элементе управления ScrollViewer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], ScrollViewer
- ScrollViewer control [WPF], about ScrollViewer control
ms.assetid: 94a13b94-cfdf-4b12-a1aa-90cb50c6e9b9
ms.openlocfilehash: 1797f956ec41ba085dee7e1cb11a3129004552b1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="scrollviewer-overview"></a>Общие сведения об элементе управления ScrollViewer
Часто содержимое в пользовательском интерфейсе занимает больше места, чем вмещает область отображения на экране компьютера. <xref:System.Windows.Controls.ScrollViewer> Управления обеспечивает удобный способ прокручивать содержимое в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] приложений. В этом разделе описываются <xref:System.Windows.Controls.ScrollViewer> элемент и предоставляет примеры его использования.  
  
<a name="what_is_a_scrollviewer_element"></a>   
## <a name="the-scrollviewer-control"></a>Элемент управления ScrollViewer  
 Существуют два предварительно определенных элементов, обеспечивающих прокрутку в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложений: <xref:System.Windows.Controls.Primitives.ScrollBar> и <xref:System.Windows.Controls.ScrollViewer>. <xref:System.Windows.Controls.ScrollViewer> Инкапсулирует элемента управления по горизонтали и вертикали <xref:System.Windows.Controls.Primitives.ScrollBar> элементов и контейнер содержимого (например, <xref:System.Windows.Controls.Panel> элемент) для отображения других видимых элементов в прокручиваемой области. Необходимо создать пользовательский объект для использования <xref:System.Windows.Controls.Primitives.ScrollBar> элемент для прокрутки содержимого. Тем не менее, можно использовать <xref:System.Windows.Controls.ScrollViewer> элемент сам по себе, так как это составной элемент управления, который инкапсулирует <xref:System.Windows.Controls.Primitives.ScrollBar> функциональные возможности.  
  
 <xref:System.Windows.Controls.ScrollViewer> Управления реагирует на команды мыши и клавиатуры и определяет множество методов для прокрутки содержимого на предопределенные значения приращения. Можно использовать <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> событий для обнаружения изменений в <xref:System.Windows.Controls.ScrollViewer> состояние.  
  
 Объект <xref:System.Windows.Controls.ScrollViewer> может иметь только один дочерний элемент, обычно <xref:System.Windows.Controls.Panel> элемент, который может содержать <xref:System.Windows.Controls.Panel.Children%2A> коллекции элементов. <xref:System.Windows.Controls.ContentPresenter.Content%2A> Свойство определяет единственного потомка <xref:System.Windows.Controls.ScrollViewer>.  
  
<a name="scrollviewer_physical_vs_logical"></a>   
## <a name="physical-vs-logical-scrolling"></a>Физическая и логическая прокрутка  
 Физическая прокрутка используется для прокрутки на предопределенное приращение, которое обычно является значением, объявленным в пикселях. Логическая прокрутка используется для прокрутки к следующему элементу в логическом дереве. Физическая прокрутка является поведением прокрутки по умолчанию для большинства <xref:System.Windows.Controls.Panel> элементов. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает оба типа прокрутки.  
  
#### <a name="the-iscrollinfo-interface"></a>Интерфейс IScrollInfo  
 <xref:System.Windows.Controls.Primitives.IScrollInfo> Интерфейс представляет основную область прокрутки в <xref:System.Windows.Controls.ScrollViewer> или производного элемента управления. Интерфейс определяет свойства и методы, которые могут быть реализованы прокрутки <xref:System.Windows.Controls.Panel> элементы, которые требуют прокрутки на логическую единицу, а не на физическое приращение. Приведения экземпляра <xref:System.Windows.Controls.Primitives.IScrollInfo> к производному <xref:System.Windows.Controls.Panel> и затем с помощью его методов прокрутки предоставляет удобный способ перейдите к следующей логической единице в дочерней коллекции, а не на шаг пикселей. По умолчанию <xref:System.Windows.Controls.ScrollViewer> элемент управления поддерживает прокрутку на физические единицы.  
  
 <xref:System.Windows.Controls.StackPanel> и <xref:System.Windows.Controls.VirtualizingStackPanel> реализованы <xref:System.Windows.Controls.Primitives.IScrollInfo> и имеют встроенную поддержку логической прокрутки. Для макета элементов управления, встроенную поддержку логической прокрутки, можно реализовать физическую прокрутку, поместив хост <xref:System.Windows.Controls.Panel> элемент в <xref:System.Windows.Controls.ScrollViewer> и параметр <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> свойства `false`.  
  
 В следующем примере кода показано, как привести экземпляр <xref:System.Windows.Controls.Primitives.IScrollInfo> для <xref:System.Windows.Controls.StackPanel> и использование методов прокрутки содержимого (<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> и <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>) определяется интерфейсом.  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>   
## <a name="defining-and-using-a-scrollviewer-element"></a>Определение и использование элемента ScrollViewer  
 В следующем примере создается <xref:System.Windows.Controls.ScrollViewer> в окно, содержащее текст и прямоугольник. <xref:System.Windows.Controls.Primitives.ScrollBar> элементы отображаются, только если они необходимы. При изменении размера окна, <xref:System.Windows.Controls.Primitives.ScrollBar> элементы появляются и исчезают из-за обновленные значения <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> и <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> свойства.  
  
 [!code-cpp[ScrollViewer#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>   
## <a name="styling-a-scrollviewer"></a>Стили элемента управления ScrollViewer  
 Как и все элементы в Windows Presentation Foundation <xref:System.Windows.Controls.ScrollViewer> можно стиль, чтобы изменить поведение по умолчанию отрисовки элемента управления. Дополнительные сведения о стилях элементов управления см. в разделе [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
<a name="scrollviewer_scroll_vs_paginate"></a>   
## <a name="paginating-documents"></a>Разбивка документов на страницы  
 Альтернативой прокрутке содержимого документа является контейнер документа, поддерживающий разбиение на страницы. <xref:System.Windows.Documents.FlowDocument> для документов, должен быть размещен в элементе управления просмотра, например <xref:System.Windows.Controls.FlowDocumentPageViewer>, который поддерживает разбиение содержимого на несколько страниц, что устраняет необходимость в прокрутке. <xref:System.Windows.Controls.DocumentViewer> предоставляет решение для просмотра <xref:System.Windows.Documents.FixedDocument> содержимое, которое использует традиционный прокрутки для отображения содержимого за пределы области отображения.  
  
 Дополнительные сведения о форматах документа и параметрах представления см. в разделе [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.Primitives.ScrollBar>  
 <xref:System.Windows.Controls.Primitives.IScrollInfo>  
 [Создание приложения для просмотра прокрутки](http://msdn.microsoft.com/library/c8e46af7-b417-441b-aa30-791cbdbd43ef)  
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Стили и шаблоны элемента ScrollBar](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)  
 [Элементы управления](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
