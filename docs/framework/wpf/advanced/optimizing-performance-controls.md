---
title: "Оптимизация производительности: элементы управления | Microsoft Docs"
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
  - "повторное использование контейнера"
  - "элементы управления [WPF], повышение производительности"
  - "визуализация пользовательского интерфейса"
ms.assetid: 45a31c43-ea8a-4546-96c8-0631b9934179
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Оптимизация производительности: элементы управления
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] включает множество общих компонентов интерфейса пользователя, которые используются в большинстве приложений Windows.  В этом разделе содержатся методы повышения производительности пользовательского интерфейса.  
  
   
  
<a name="Displaying"></a>   
## Отображение больших наборов данных  
 Элементы управления WPF, такие как <xref:System.Windows.Controls.ListView> и <xref:System.Windows.Controls.ComboBox>, используются для отображения списков элементов в приложении.  Если список для отображения большой, это может повлиять на производительность приложения.  Это происходит потому, что стандартная система разметки создает контейнер разметки для каждого элемента, связанного с элементом управления в списке, и вычисляет размер и позицию разметки.  Обычно не требуется отображать все элементы одновременно, вместо этого отображается некоторое подмножество, и пользователь прокручивает список.  В этом случае, затрагивается *виртуализация* пользовательского интерфейса, и в результате генерирование контейнера элементов и вычисление связанной разметки замедляется, пока отображается элемент.  
  
 Виртуализация пользовательского интерфейса является важным аспектом элементов управления списка.  Виртуализация пользовательского интерфейса не должна служить помехой виртуализации данных.  Виртуализация пользовательского интерфейса хранит только видимые элементы в памяти, но в скриптах привязки данных в памяти сохраняется вся структура данных.  Наоборот, виртуализация данных сохраняет в памяти только элементы данных, которые отображаются на экране.  
  
 По умолчанию виртуализация пользовательского интерфейса включена для элементов управления <xref:System.Windows.Controls.ListView> и <xref:System.Windows.Controls.ListBox>, если их элементы списка привязаны к данным.  Виртуализацию <xref:System.Windows.Controls.TreeView> можно включить, присвоив вложенному свойству <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=fullName> значение `true`.  Если нужно включить виртуализацию пользовательского интерфейса для настраиваемых элементов управления, производных от класса <xref:System.Windows.Controls.ItemsControl>, или существующих элементов управления, использующих класс <xref:System.Windows.Controls.StackPanel>, таких как <xref:System.Windows.Controls.ComboBox>, можно установить свойство <xref:System.Windows.Controls.ItemsControl.ItemsPanel%2A> для класса <xref:System.Windows.Controls.VirtualizingStackPanel> и задать для свойства <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizing%2A> значение `true`.  К сожалению, можно отключить виртуализацию пользовательского интерфейса, не зная этого.  Далее представлен список условий, отключающих виртуализацию пользовательского интерфейса.  
  
-   Контейнеры элементов добавляются напрямую к элементу управления <xref:System.Windows.Controls.ItemsControl>.  Например, если приложение явно добавляет объекты <xref:System.Windows.Controls.ListBoxItem> к <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ListBox> не будет виртуализировать объекты <xref:System.Windows.Controls.ListBoxItem>.  
  
-   Объект <xref:System.Windows.Controls.ItemsControl> содержит контейнеры элементов различных типов.  Например, объект <xref:System.Windows.Controls.Menu>, использующий объекты <xref:System.Windows.Controls.Separator>, не может реализовать повторное использование элементов, так как <xref:System.Windows.Controls.Menu> содержит объекты типа <xref:System.Windows.Controls.Separator> и <xref:System.Windows.Controls.MenuItem>.  
  
-   Установка для свойства <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> значения `false`.  
  
-   Установка для свойства <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A> значения `false`.  
  
 Важные соображения по virtualize контейнеров элементов имеется дополнительные сведения о состоянии, связанные с контейнером элемента, который принадлежит данному элементу.  В этом случае, необходимо сохранить дополнительное состояние.  Например, элемент может находиться в элементе управления <xref:System.Windows.Controls.Expander>, и состояние <xref:System.Windows.Controls.Expander.IsExpanded%2A> привязано к контейнеру элемента, а не к самому элементу.  Если контейнер повторно используется для нового элемента, текущее значение свойства <xref:System.Windows.Controls.Expander.IsExpanded%2A> используется для нового элемента.  Дополнительно, старый элемент теряет правильное значение <xref:System.Windows.Controls.Expander.IsExpanded%2A>.  
  
 В настоящее время элементы управления WPF не предлагают встроенную поддержку виртуализации данных.  
  
<a name="Container"></a>   
## Повторное использование контейнера  
 В пакет обновления 1 \(SP1\) для платформы .NET Framework 3.5 добавлена оптимизация виртуализации пользовательского интерфейса для элементов управления, наследующих от класса <xref:System.Windows.Controls.ItemsControl>, — *повторное использование контейнера*, также это может повысить быстродействие прокрутки.  Когда объект <xref:System.Windows.Controls.ItemsControl>, использующий виртуализацию пользовательского интерфейса, заполняется, создается контейнер элементов для каждого отображаемого при прокрутке элемента, и контейнер элементов удаляется, когда элемент в результате прокрутки не отображается.  *Повторное использование контейнера* позволяет элементу управления повторно использовать существующие контейнеры элементов для различных элементов данных, чтобы контейнеры элементов не создавались и не удалялись постоянно при прокрутке пользователем объекта <xref:System.Windows.Controls.ItemsControl>.  Можно выбрать включение элемент рециркулируя установкой <xref:System.Windows.Controls.VirtualizingPanel.VirtualizationMode%2A> присоединенное свойство  <xref:System.Windows.Controls.VirtualizationMode>.  
  
 Любой объект <xref:System.Windows.Controls.ItemsControl>, поддерживающий виртуализацию, может повторно использовать контейнер.  Пример, как включить повторное использование контейнера для <xref:System.Windows.Controls.ListBox>, см. в разделе [Улучшение производительности прокрутки ListBox](../../../../docs/framework/wpf/controls/how-to-improve-the-scrolling-performance-of-a-listbox.md).  
  
<a name="Supporting"></a>   
## Поддержка двунаправленной виртуализации  
 <xref:System.Windows.Controls.VirtualizingStackPanel> предлагает встроенную поддержку виртуализации пользовательского интерфейса в одном направлении — горизонтально или вертикально.  Если нужно использовать двунаправленную виртуализацию для элементов управления, необходимо реализовать настраиваемую панель, расширяющую класс <xref:System.Windows.Controls.VirtualizingStackPanel>.  Класс <xref:System.Windows.Controls.VirtualizingStackPanel> предоставляет виртуальные методы, такие как <xref:System.Windows.Controls.VirtualizingStackPanel.OnViewportSizeChanged%2A>, <xref:System.Windows.Controls.VirtualizingStackPanel.LineUp%2A>, <xref:System.Windows.Controls.VirtualizingStackPanel.PageUp%2A> и <xref:System.Windows.Controls.VirtualizingStackPanel.MouseWheelUp%2A>.Эти виртуальные методы позволяют обнаружить изменение в видимой части списка и соответственно его обработать.  
  
<a name="Optimizing"></a>   
## Оптимизация шаблонов  
 Визуальное дерево содержит все визуальные элементы в приложении.  Дополнительно к непосредственно созданным объектам оно также содержит объекты для возможного расширения шаблона.  Например, при создании объекта <xref:System.Windows.Controls.Button> в визуальном дереве также создаются объекты <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> и <xref:System.Windows.Controls.ContentPresenter>.  Без оптимизации шаблонов элементов управления в визуальном дереве может быть создано большое число дополнительных ненужных объектов.  Дополнительные сведения о визуальном дереве см. в разделе [Общие сведения об отрисовке графики в WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
<a name="Deferred"></a>   
## Отложенная прокрутка  
 По умолчанию, когда пользователь перетаскивает бегунок в полосе прокрутки, представление содержимого постоянно обновляется.  Если скорость прокрутки в элементе управления низкая, рассмотрите возможность использования отложенной прокрутки.  При отложенной прокрутке содержимое обновляется, только когда пользователь отпускает бегунок.  
  
 Чтобы реализовать отложенную прокрутку, задайте для свойства <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A> значение `true`.  <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A> является вложенным свойством и может быть задано в объекте <xref:System.Windows.Controls.ScrollViewer> и в любом элементе управления с <xref:System.Windows.Controls.ScrollViewer> в его шаблоне элементов управления.  
  
<a name="Controls"></a>   
## Элементы управления, реализующие настройку производительности  
 В следующей таблице перечислены общие элементы управления для отображения данных и их поддержка настройки производительности.  Сведения о том, как включить эти настройки, см. в предыдущих разделах.  
  
|Элемент управления|Виртуализация|Повторное использование контейнера|Отложенная прокрутка|  
|------------------------|-------------------|----------------------------------------|--------------------------|  
|<xref:System.Windows.Controls.ComboBox>|Можно включить|Можно включить|Можно включить|  
|<xref:System.Windows.Controls.ContextMenu>|Можно включить|Можно включить|Можно включить|  
|<xref:System.Windows.Controls.DocumentViewer>|Недоступно|Недоступно|Можно включить|  
|<xref:System.Windows.Controls.ListBox>|Default|Можно включить|Можно включить|  
|<xref:System.Windows.Controls.ListView>|Default|Можно включить|Можно включить|  
|<xref:System.Windows.Controls.TreeView>|Можно включить|Можно включить|Можно включить|  
|<xref:System.Windows.Controls.ToolBar>|Недоступно|Недоступно|Можно включить|  
  
> [!NOTE]
>  Пример, как включить виртуализацию и повторное использование контейнера для <xref:System.Windows.Controls.TreeView>, см. в разделе [Повышение производительности элемента управления TreeView](../../../../docs/framework/wpf/controls/how-to-improve-the-performance-of-a-treeview.md).  
  
## См. также  
 [Макет](../../../../docs/framework/wpf/advanced/layout.md)   
 [Разметка и разработка](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [Привязка данных](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Элементы управления](../../../../docs/framework/wpf/controls/index.md)   
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Пошаговое руководство. Кэширование данных приложения WPF](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)