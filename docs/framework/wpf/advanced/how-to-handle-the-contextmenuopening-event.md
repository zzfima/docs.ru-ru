---
title: "Практическое руководство. Событие ContextMenuOpening | Microsoft Docs"
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
  - "ContextMenuOpening - событие"
ms.assetid: 789652fb-1951-4217-934a-7843e355adf4
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Событие ContextMenuOpening
Событие <xref:System.Windows.FrameworkElement.ContextMenuOpening> может быть обработано в приложении либо для корректировки существующего контекстного меню перед отображением, либо для подавления меню, которое отображалось бы в противном случае, путем установки для свойства <xref:System.Windows.RoutedEventArgs.Handled%2A> значения `true` в данных события.  Обычно причиной задания для <xref:System.Windows.RoutedEventArgs.Handled%2A> значения `true` в данных события является необходимость полной замены меню новым объектом <xref:System.Windows.Controls.ContextMenu>, который иногда требует отмены операции и запуска нового открытия.  При написании обработчиков для события <xref:System.Windows.FrameworkElement.ContextMenuOpening>, то следует иметь в виду проблемы синхронизации между элементом управления <xref:System.Windows.Controls.ContextMenu> и службой, которая отвечает за открытие и позиционирование контекстных меню для элементов управления в целом.  В этом разделе проиллюстрированы некоторые технические приемы написания кода для различных скриптов открытия контекстного меню, а также случаи, в которых возникают проблемы синхронизации.  
  
 Существует несколько скриптов для обработки события <xref:System.Windows.FrameworkElement.ContextMenuOpening>:  
  
-   Корректировка элементов меню перед отображением.  
  
-   Замена всего меню перед отображением.  
  
-   Полное подавление любых существующих контекстных меню и отсутствие отображения контекстного меню.  
  
## Пример  
  
## Корректировка элементов меню перед отображением  
 Корректировка существующих элементов меню достаточно проста и является, вероятно, наиболее распространенным скриптом.  Корректировка может выполняться для добавления или удаления команд контекстного меню в соответствии с информацией о текущем состоянии приложения или конкретном состоянии, которая доступна как свойство объекта, для которого запрашивается контекстное меню.  
  
 Основным методом является получение источника события, то есть определенного элемента управления, на котором был произведен щелчок правой кнопкой мыши, и получение его свойства <xref:System.Windows.FrameworkElement.ContextMenu%2A>.  Как правило, требуется проверить коллекцию <xref:System.Windows.Controls.ItemsControl.Items%2A> для просмотра уже существующих в меню элементов контекстного меню, а затем добавить в коллекцию или удалить из нее соответствующие новые элементы <xref:System.Windows.Controls.MenuItem>.  
  
 [!code-csharp[ContextMenuOpeningHandlers#AddItemNoHandle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#additemnohandle)]  
  
## Замена всего меню перед отображением  
 В некоторых случаях требуется заменить контекстное меню целиком.  Разумеется, здесь также можно использовать вариант предыдущего кода для удаления каждого элемента существующего контекстного меню и добавления новых, начиная с нулевого элемента.  Но более естественным подходом для замены всех элементов в контекстном меню является создание нового <xref:System.Windows.Controls.ContextMenu>, заполнение его элементами и последующая установка свойства <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=fullName> элемента управления для нового <xref:System.Windows.Controls.ContextMenu>.  
  
 Ниже приведен код простого обработчика для замены <xref:System.Windows.Controls.ContextMenu>.  Код ссылается на пользовательский метод `BuildMenu`, который обособлен, поскольку вызывается несколькими обработчиками примера.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceNoReopen](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacenoreopen)]  
  
 [!code-csharp[ContextMenuOpeningHandlers#BuildMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#buildmenu)]  
  
 Однако при использовании этого стиля обработчика для <xref:System.Windows.FrameworkElement.ContextMenuOpening> есть вероятность возникновения проблем синхронизации, если объект, в котором задано свойство <xref:System.Windows.Controls.ContextMenu>, не имеет уже существующего контекстного меню.  При щелчке элемента управления правой кнопкой мыши событие <xref:System.Windows.FrameworkElement.ContextMenuOpening> возникает даже в том случае, если существующее <xref:System.Windows.Controls.ContextMenu> пусто или имеет значение null.  Но в этом случае любое новое <xref:System.Windows.Controls.ContextMenu>, установленное на исходном элементе, поступает слишком поздно для отображения.  Кроме того, если пользователь щелкнет правой кнопкой мыши второй раз, то появится новое <xref:System.Windows.Controls.ContextMenu>, с отличным от null значением, и при повторном выполнении обработчика замена и отображение меню будут выполнены правильно.  Это предполагает два возможных способа решения проблемы:  
  
1.  Убедитесь, что обработчики <xref:System.Windows.FrameworkElement.ContextMenuOpening> всегда запускаются для элементов управления, имеющих хотя бы местозаполнитель <xref:System.Windows.Controls.ContextMenu>, предназначенный для замены кодом обработчика.  В этом случае можно по\-прежнему использовать обработчик из предыдущего примера, но обычно требуется назначить местозаполнитель <xref:System.Windows.Controls.ContextMenu> в первоначальном макете:  
  
     [!code-xml[ContextMenuOpeningHandlers#XAMLWithInitCM](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml#xamlwithinitcm)]  
  
2.  Предположим, что исходным значением <xref:System.Windows.Controls.ContextMenu> может быть null по некоторой предварительной логике.  Можно либо проверить <xref:System.Windows.Controls.ContextMenu> на null, либо использовать флаг в коде для проверки, был ли обработчик запущен хоть раз.  Поскольку предполагается, что <xref:System.Windows.Controls.ContextMenu> будет отображаться, то обработчик задает для <xref:System.Windows.RoutedEventArgs.Handled%2A> значение `true` в данных события.  Для <xref:System.Windows.Controls.ContextMenuService>, отвечающего за отображение контекстного меню, значение `true` для <xref:System.Windows.RoutedEventArgs.Handled%2A> в данных события представляет собой запрос отмены отображения для сочетания контекстного меню и элемента управления, вызвавшего событие.  
  
 После подавления возможного появления контекстного меню следующим шагом является предоставление нового контекстного меню и его отображение.  Настройка нового меню выполняется в общем так же, как для предыдущего обработчика: строится новый объект <xref:System.Windows.Controls.ContextMenu>, который указывается в качестве значения свойства <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=fullName> источника элемента управления.  Дополнительным шагом является принудительное отображение контекстного меню, поскольку первая попытка подавляется.  Для принудительного отображения присвойте свойству <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A?displayProperty=fullName> значение `true` внутри обработчика.  Будьте внимательны при этом, так как открытие контекстного меню в обработчике снова вызывает событие <xref:System.Windows.FrameworkElement.ContextMenuOpening>.  В случае повторного входа в обработчик это приведет к бесконечной рекурсии.  Поэтому необходимо всегда выполнять проверку на `null` или использовать флаг, если контекстное меню открывается из обработчика событий <xref:System.Windows.FrameworkElement.ContextMenuOpening>.  
  
## Полное подавление любых существующих контекстных меню и отсутствие отображения контекстного меню  
 Последний скрипт — написание обработчика, который полностью подавляет меню, — является редким.  Если отображение контекстного меню для данного элемента управления не требуется, вероятно, существуют более подходящие способы обеспечить это, чем подавление меню при его запросе пользователем.  Но если необходимо использовать обработчик для подавления контекстного меню без отображения, обработчик просто должен задавать для <xref:System.Windows.RoutedEventArgs.Handled%2A> значение `true` в данных события.  <xref:System.Windows.Controls.ContextMenuService>, который отвечает за отображение контекстного меню, будет проверять данные события, возникшего в элементе управления.  Если событие было помечено как <xref:System.Windows.RoutedEventArgs.Handled%2A> где\-либо вдоль маршрута, то действие по открытию контекстного меню, инициирующее данное событие, будет подавляться.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceReopen](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacereopen)]  
  
## См. также  
 <xref:System.Windows.Controls.ContextMenu>   
 <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=fullName>   
 [Общие сведения о базовых элементах](../../../../docs/framework/wpf/advanced/base-elements-overview.md)   
 [Общие сведения о ContextMenu](../../../../docs/framework/wpf/controls/contextmenu-overview.md)