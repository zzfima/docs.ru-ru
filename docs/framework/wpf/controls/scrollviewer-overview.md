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
ms.openlocfilehash: 2ff0f134ea3174f7f034d47446aab782e2141916
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186988"
---
# <a name="scrollviewer-overview"></a>Общие сведения об элементе управления ScrollViewer
Часто содержимое в пользовательском интерфейсе занимает больше места, чем вмещает область отображения на экране компьютера. Управление <xref:System.Windows.Controls.ScrollViewer> обеспечивает удобный способ прокрутки [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] содержимого в приложениях. Эта тема представляет <xref:System.Windows.Controls.ScrollViewer> элемент и приводит несколько примеров использования.  
  
<a name="what_is_a_scrollviewer_element"></a>
## <a name="the-scrollviewer-control"></a>Элемент управления ScrollViewer  
 Есть два предопределенных элемента, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] которые <xref:System.Windows.Controls.Primitives.ScrollBar> <xref:System.Windows.Controls.ScrollViewer>позволяют прокрутки в приложениях: и . Элемент <xref:System.Windows.Controls.ScrollViewer> управления инкапсулирует горизонтальные <xref:System.Windows.Controls.Primitives.ScrollBar> и вертикальные элементы <xref:System.Windows.Controls.Panel> и контейнер содержимого (например, элемент) для отображения других видимых элементов в прокрутки области. Необходимо создать пользовательский объект, чтобы <xref:System.Windows.Controls.Primitives.ScrollBar> использовать элемент для прокрутки содержимого. Тем не менее, <xref:System.Windows.Controls.ScrollViewer> элемент можно использовать сам по себе, потому что это композитный элемент, который инкапсулирует <xref:System.Windows.Controls.Primitives.ScrollBar> функциональность.  
  
 Управление <xref:System.Windows.Controls.ScrollViewer> реагирует как на команды мыши, так и клавиатуры, и определяет многочисленные методы, с помощью которых можно прокрутить содержимое заранее определенными шагом. Событие можно <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> использовать для обнаружения изменения <xref:System.Windows.Controls.ScrollViewer> состояния.  
  
 A <xref:System.Windows.Controls.ScrollViewer> может иметь только одного <xref:System.Windows.Controls.Panel> ребенка, <xref:System.Windows.Controls.Panel.Children%2A> как правило, элемент, который может разместить коллекцию элементов. Свойство <xref:System.Windows.Controls.ContentPresenter.Content%2A> определяет единственного <xref:System.Windows.Controls.ScrollViewer>ребенка .  
  
<a name="scrollviewer_physical_vs_logical"></a>
## <a name="physical-vs-logical-scrolling"></a>Физическое против логического прокрутки  
 Физическая прокрутка используется для прокрутки на предопределенное приращение, которое обычно является значением, объявленным в пикселях. Логическая прокрутка используется для прокрутки к следующему элементу в логическом дереве. Физическая прокрутка — это <xref:System.Windows.Controls.Panel> поведение прокрутки по умолчанию для большинства элементов. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает оба типа прокрутки.  
  
#### <a name="the-iscrollinfo-interface"></a>Интерфейс IScrollInfo  
 Интерфейс <xref:System.Windows.Controls.Primitives.IScrollInfo> представляет собой основную область <xref:System.Windows.Controls.ScrollViewer> прокрутки в элементе или производном элементе управления. Интерфейс определяет свойства прокрутки и методы, которые могут быть реализованы элементами, <xref:System.Windows.Controls.Panel> требующими прокрутки логическим блоком, а не физическим шагом. Отливание <xref:System.Windows.Controls.Primitives.IScrollInfo> экземпляра к <xref:System.Windows.Controls.Panel> производному, а затем использование его методов прокрутки обеспечивает полезный способ прокрутки к следующему логическому блоку в детской коллекции, а не пиксельным шагом. По умолчанию <xref:System.Windows.Controls.ScrollViewer> элемент управления поддерживает прокрутку физическими единицами.  
  
 <xref:System.Windows.Controls.StackPanel>и <xref:System.Windows.Controls.VirtualizingStackPanel> как <xref:System.Windows.Controls.Primitives.IScrollInfo> реализовать и родной поддержки логического прокрутки. Для элементов управления макетом, которые по-прежнему поддерживают логическое прокрутку, <xref:System.Windows.Controls.ScrollViewer> вы все <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> равно `false`можете достичь физической прокрутки, обернув элемент узла <xref:System.Windows.Controls.Panel> в элемент а и установив свойство.  
  
 Следующий пример кода демонстрирует, как <xref:System.Windows.Controls.Primitives.IScrollInfo> бросить <xref:System.Windows.Controls.StackPanel> экземпляр и использовать методы<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>прокрутки содержимого (и) определяется интерфейсом.  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>
## <a name="defining-and-using-a-scrollviewer-element"></a>Определение и использование элемента ScrollViewer  
 Следующий пример <xref:System.Windows.Controls.ScrollViewer> создает в окне, содержащем текст и прямоугольник. <xref:System.Windows.Controls.Primitives.ScrollBar>элементы появляются только тогда, когда они необходимы. При повторном размере <xref:System.Windows.Controls.Primitives.ScrollBar> окна элементы отображаются и <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> исчезают из-за обновленных значений и свойств.  
  
 [!code-cpp[ScrollViewer#1](~/samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](~/samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>
## <a name="styling-a-scrollviewer"></a>Стили элемента управления ScrollViewer  
 Как и все элементы <xref:System.Windows.Controls.ScrollViewer> управления в Windows Presentation Foundation, они могут быть стилизованы для изменения поведения элемента управления по умолчанию. Дополнительные сведения о стилях элементов управления см. в разделе [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
<a name="scrollviewer_scroll_vs_paginate"></a>
## <a name="paginating-documents"></a>Разбивка документов на страницы  
 Альтернативой прокрутке содержимого документа является контейнер документа, поддерживающий разбиение на страницы. <xref:System.Windows.Documents.FlowDocument>для документов, предназначенных для размещения в <xref:System.Windows.Controls.FlowDocumentPageViewer>рамках управления просмотром, таких как , что поддерживает paginating содержание на нескольких страницах, предотвращая необходимость прокрутки. <xref:System.Windows.Controls.DocumentViewer>предоставляет решение для <xref:System.Windows.Documents.FixedDocument> просмотра содержимого, которое использует традиционную прокрутку для отображения содержимого за пределами области дисплея.  
  
 Дополнительные сведения о форматах документа и параметрах представления см. в разделе [Документы в WPF](../advanced/documents-in-wpf.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.ScrollBar>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- [Как: Создать просмотр свитка](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752352(v=vs.90))
- [Документы в WPF](../advanced/documents-in-wpf.md)
- [Стили и шаблоны элемента ScrollBar](scrollbar-styles-and-templates.md)
- [Управление](../advanced/optimizing-performance-controls.md)
