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
ms.openlocfilehash: 993f3c861cbead88df3503eb01f18e5d1f69e2d8
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458434"
---
# <a name="scrollviewer-overview"></a>Общие сведения об элементе управления ScrollViewer
Часто содержимое в пользовательском интерфейсе занимает больше места, чем вмещает область отображения на экране компьютера. Элемент управления <xref:System.Windows.Controls.ScrollViewer> предоставляет удобный способ для включения прокрутки содержимого в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] приложениях. В этом разделе описывается элемент <xref:System.Windows.Controls.ScrollViewer> и приводится несколько примеров использования.  
  
<a name="what_is_a_scrollviewer_element"></a>   
## <a name="the-scrollviewer-control"></a>Элемент управления ScrollViewer  
 Есть два предопределенных элемента, которые позволяют выполнять прокрутку в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложениях: <xref:System.Windows.Controls.Primitives.ScrollBar> и <xref:System.Windows.Controls.ScrollViewer>. Элемент управления <xref:System.Windows.Controls.ScrollViewer> инкапсулирует горизонтальные и вертикальные <xref:System.Windows.Controls.Primitives.ScrollBar> элементы и контейнер содержимого (например, элемент <xref:System.Windows.Controls.Panel>) для отображения других видимых элементов в прокручиваемой области. Чтобы использовать элемент <xref:System.Windows.Controls.Primitives.ScrollBar> для прокрутки содержимого, необходимо создать пользовательский объект. Однако можно использовать элемент <xref:System.Windows.Controls.ScrollViewer> сам по себе, так как он является составным элементом управления, который инкапсулирует функциональные возможности <xref:System.Windows.Controls.Primitives.ScrollBar>.  
  
 Элемент управления <xref:System.Windows.Controls.ScrollViewer> реагирует на команды мыши и клавиатуры и определяет многочисленные методы, с помощью которых прокрутка содержимого осуществляется с помощью заранее заданных приращений. Для обнаружения изменений в <xref:System.Windows.Controls.ScrollViewer> состоянии можно использовать событие <xref:System.Windows.Controls.ScrollViewer.ScrollChanged>.  
  
 <xref:System.Windows.Controls.ScrollViewer> может иметь только один дочерний элемент, обычно <xref:System.Windows.Controls.Panel>, который может размещать <xref:System.Windows.Controls.Panel.Children%2A> коллекцию элементов. Свойство <xref:System.Windows.Controls.ContentPresenter.Content%2A> определяет единственного потомка <xref:System.Windows.Controls.ScrollViewer>.  
  
<a name="scrollviewer_physical_vs_logical"></a>   
## <a name="physical-vs-logical-scrolling"></a>Физическая и Логическая прокрутка  
 Физическая прокрутка используется для прокрутки на предопределенное приращение, которое обычно является значением, объявленным в пикселях. Логическая прокрутка используется для прокрутки к следующему элементу в логическом дереве. Физическая прокрутка — это поведение прокрутки по умолчанию для большинства элементов <xref:System.Windows.Controls.Panel>. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает оба типа прокрутки.  
  
#### <a name="the-iscrollinfo-interface"></a>Интерфейс IScrollInfo  
 Интерфейс <xref:System.Windows.Controls.Primitives.IScrollInfo> представляет главную область прокрутки внутри <xref:System.Windows.Controls.ScrollViewer> или производного элемента управления. Интерфейс определяет свойства прокрутки и методы, которые могут быть реализованы <xref:System.Windows.Controls.Panel> элементами, требующими прокрутки логическим устройством, а не физическим инкрементом. Приведение экземпляра <xref:System.Windows.Controls.Primitives.IScrollInfo> к производному <xref:System.Windows.Controls.Panel>, а затем использование его методов прокрутки предоставляет удобный способ прокрутки к следующему логическому блоку в дочерней коллекции, а не к инкременту в пикселях. По умолчанию элемент управления <xref:System.Windows.Controls.ScrollViewer> поддерживает прокрутку по физическим единицам.  
  
 <xref:System.Windows.Controls.StackPanel> и <xref:System.Windows.Controls.VirtualizingStackPanel> реализуют <xref:System.Windows.Controls.Primitives.IScrollInfo> и изначально поддерживают логическую прокрутку. Для элементов управления макета, которые изначально поддерживают логическую прокрутку, можно обеспечить физическую прокрутку, заключив элемент <xref:System.Windows.Controls.Panel> узла в <xref:System.Windows.Controls.ScrollViewer> и установив для свойства <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> значение `false`.  
  
 В следующем примере кода показано, как привести экземпляр <xref:System.Windows.Controls.Primitives.IScrollInfo> к <xref:System.Windows.Controls.StackPanel> и использовать методы прокрутки содержимого (<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> и <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>), определенные интерфейсом.  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>   
## <a name="defining-and-using-a-scrollviewer-element"></a>Определение и использование элемента ScrollViewer  
 В следующем примере создается <xref:System.Windows.Controls.ScrollViewer> в окне, содержащем некоторый текст и прямоугольник. <xref:System.Windows.Controls.Primitives.ScrollBar> элементы отображаются только в том случае, если они необходимы. При изменении размера окна элементы <xref:System.Windows.Controls.Primitives.ScrollBar> отображаются и исчезают из-за обновленных значений свойств <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> и <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A>.  
  
 [!code-cpp[ScrollViewer#1](~/samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](~/samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>   
## <a name="styling-a-scrollviewer"></a>Стили элемента управления ScrollViewer  
 Как и все элементы управления в Windows Presentation Foundation, <xref:System.Windows.Controls.ScrollViewer> можно присвоить стилю, чтобы изменить поведение отрисовки элемента управления по умолчанию. Дополнительные сведения о стилях элементов управления см. в разделе [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
<a name="scrollviewer_scroll_vs_paginate"></a>   
## <a name="paginating-documents"></a>Разбивка документов на страницы  
 Альтернативой прокрутке содержимого документа является контейнер документа, поддерживающий разбиение на страницы. <xref:System.Windows.Documents.FlowDocument> предназначен для документов, предназначенных для размещения в элементе управления просмотром, например <xref:System.Windows.Controls.FlowDocumentPageViewer>, который поддерживает содержимое разбивка на нескольких страницах, предотвращая необходимость прокрутки. <xref:System.Windows.Controls.DocumentViewer> предоставляет решение для просмотра содержимого <xref:System.Windows.Documents.FixedDocument>, которое использует традиционную прокрутку для отображения содержимого вне области отображения.  
  
 Дополнительные сведения о форматах документа и параметрах представления см. в разделе [Документы в WPF](../advanced/documents-in-wpf.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.ScrollBar>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- [Как создать средство просмотра прокрутки](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752352(v=vs.90))
- [Документы в WPF](../advanced/documents-in-wpf.md)
- [Стили и шаблоны элемента ScrollBar](scrollbar-styles-and-templates.md)
- [Элементы управления](../advanced/optimizing-performance-controls.md)
