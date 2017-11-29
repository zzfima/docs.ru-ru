---
title: "Практическое руководство. Событие ContextMenuOpening"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ContextMenuOpening properties [WPF]
ms.assetid: 789652fb-1951-4217-934a-7843e355adf4
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 61048a8db67986c55e1a1b07d62d5142069dd63e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-the-contextmenuopening-event"></a>Практическое руководство. Событие ContextMenuOpening
<xref:System.Windows.FrameworkElement.ContextMenuOpening> Событие может быть обработано в приложении либо для корректировки существующего контекстного меню перед для отображения или подавления меню, которое будет отображаться в противном случае, задав <xref:System.Windows.RoutedEventArgs.Handled%2A> свойства `true` в данных события. Обычно причиной задания для <xref:System.Windows.RoutedEventArgs.Handled%2A> для `true` событий данных является замена меню полностью новый <xref:System.Windows.Controls.ContextMenu> объекта, который иногда требует отмены операции и запуска нового открытия. При записи дескрипторов для <xref:System.Windows.FrameworkElement.ContextMenuOpening> события, которые необходимо учитывать проблемы синхронизации между <xref:System.Windows.Controls.ContextMenu> управления и службу, которая отвечает за открытие и позиционирование контекстных меню для элементов управления в целом. В этом разделе рассмотрены некоторые способы кода для различных скриптов открытия контекстного меню и демонстрирует ситуацию, где ошибки синхронизации вступает в действие.  
  
 Существует несколько сценариев для обработки <xref:System.Windows.FrameworkElement.ContextMenuOpening> событий:  
  
-   Настройка элементов меню перед отображением.  
  
-   Замена всего меню перед отображением.  
  
-   Полностью подавление любых существующих контекстных меню и отсутствие отображения контекстного меню.  
  
## <a name="example"></a>Пример  
  
## <a name="adjusting-the-menu-items-before-display"></a>Корректировка элементов меню перед отображением.  
 Настройка существующих элементов меню достаточно проста и, вероятно, является наиболее распространенным сценарием. Это нужно для добавления и удаления команд контекстного меню в ответ сведения о текущем состоянии приложения или определенного состояния информацию, которая доступна как свойство объекта, когда запрашиваются в контекстном меню.  
  
 Основным методом является источник события, который является конкретного элемента управления, который был правой кнопкой мыши, и получите <xref:System.Windows.FrameworkElement.ContextMenu%2A> свойство из него. Обычно требуется проверить <xref:System.Windows.Controls.ItemsControl.Items%2A> коллекцию позволяет определить, какие элементы контекстного меню уже существует в меню и затем добавить или удалить соответствующие новые <xref:System.Windows.Controls.MenuItem> элементы или из коллекции.  
  
 [!code-csharp[ContextMenuOpeningHandlers#AddItemNoHandle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#additemnohandle)]  
  
## <a name="replacing-the-entire-menu-before-display"></a>Замена всего меню перед отображением.  
 Альтернативного сценария является то, следует ли заменить контекстное меню целиком. Конечно может также использовать вариант предыдущего кода для удаления каждого элемента существующего контекстного меню и добавления новых, начиная с нулевого элемента. Но более естественным подходом для замены всех элементов в контекстном меню для создания нового <xref:System.Windows.Controls.ContextMenu>, заполнение ее элементов и установите <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType> свойства элемента управления для нового <xref:System.Windows.Controls.ContextMenu>.  
  
 Ниже приведен код простого обработчика для замены <xref:System.Windows.Controls.ContextMenu>. Код ссылается на пользовательское `BuildMenu` метод, который отделяется out, так как он вызывается более одного обработчиками примера.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceNoReopen](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacenoreopen)]  
  
 [!code-csharp[ContextMenuOpeningHandlers#BuildMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#buildmenu)]  
  
 Тем не менее при использовании этого стиля обработчика для <xref:System.Windows.FrameworkElement.ContextMenuOpening>, потенциально возникновения проблем синхронизации, если объект, где вы настраиваете <xref:System.Windows.Controls.ContextMenu> имеет уже существующего контекстного меню. При щелчке элемента управления <xref:System.Windows.FrameworkElement.ContextMenuOpening> возникает даже в том случае, если существующий <xref:System.Windows.Controls.ContextMenu> пустой или имеет значение null. Но в этом случае любое новое <xref:System.Windows.Controls.ContextMenu> установленное на исходном элементе, поступает слишком поздно для отображения. Кроме того, если пользователь щелкнет правой кнопкой мыши второй раз, это время ваш новый <xref:System.Windows.Controls.ContextMenu> , это значение равно null, не являющихся и отображается обработчиком правильно заменит и отобразить меню при выполнении обработчика еще раз. Это предлагает два способа решения:  
  
1.  Убедитесь, что <xref:System.Windows.FrameworkElement.ContextMenuOpening> всегда запускаются для элементов управления, имеющих хотя бы местозаполнитель обработчики <xref:System.Windows.Controls.ContextMenu> доступно, предназначенный для замены кодом обработчика. В этом случае можно по-прежнему использовать обработчик, показанный в предыдущем примере, но обычно требуется назначить местозаполнитель <xref:System.Windows.Controls.ContextMenu> в первоначальном макете:  
  
     [!code-xaml[ContextMenuOpeningHandlers#XAMLWithInitCM](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml#xamlwithinitcm)]  
  
2.  Предполагается, что начальный <xref:System.Windows.Controls.ContextMenu> может иметь значение null, на основе некоторые предварительные логики. Можно либо проверить <xref:System.Windows.Controls.ContextMenu> на null, либо использовать флаг в коде, чтобы проверить, был ли ваш обработчик запустить по крайней мере один раз. Так как предполагается, что <xref:System.Windows.Controls.ContextMenu> о будет отображаться, ваш обработчик затем задает <xref:System.Windows.RoutedEventArgs.Handled%2A> для `true` в данных события. Чтобы <xref:System.Windows.Controls.ContextMenuService> , отвечает за отображение контекстного меню, `true` значение для <xref:System.Windows.RoutedEventArgs.Handled%2A> событий данных представляет собой запрос отмены отображения для контекстного меню или управлять сочетания, создавший событие.  
  
 Теперь, когда вы отменили потенциально подозрительные контекстного меню, следующим шагом является предоставление нового, затем отобразить ее. Настройка нового один существенно не отличается от предыдущего обработчика: выполняется построение новой <xref:System.Windows.Controls.ContextMenu> и задать источник управления <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType> свойство с ним. Дополнительным шагом является, принудительное отображение контекстного меню, поскольку первая попытка подавляется. Для принудительного отображения, задать <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A?displayProperty=nameWithType> свойства `true` обработчика. Будьте внимательны, когда это сделать, так как Открытие контекстного меню в обработчике вызывает <xref:System.Windows.FrameworkElement.ContextMenuOpening> событий еще раз. Если вы повторного входа в обработчик, он бесконечной рекурсии. Поэтому всегда необходимо выполнять поиск `null` или использовать флаг, если открыть контекстное меню внутри <xref:System.Windows.FrameworkElement.ContextMenuOpening> обработчика событий.  
  
## <a name="suppressing-any-existing-context-menu-and-displaying-no-context-menu"></a>Подавление любых существующих контекстных меню и отсутствие отображения контекстного меню  
 Последний сценарий — написание обработчика, который полностью, подавляет меню редко. Если данный элемент управления не предназначен для вызова контекстного меню, существует, возможно, более подходящие способы обеспечить это, чем подавление меню только в том случае, когда пользователь запрашивает ее. Но если вы хотите использовать обработчик для подавления контекстного меню без отображения, то обработчик просто должен задавать <xref:System.Windows.RoutedEventArgs.Handled%2A> для `true` в данных события. <xref:System.Windows.Controls.ContextMenuService> , Отвечает за отображение контекстного меню будет проверять данные события, возникшего в элементе управления. Если событие было помечено как <xref:System.Windows.RoutedEventArgs.Handled%2A> в любом месте на маршруте, то действие по открытию контекстного меню, инициировавшего событие будет подавляться.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceReopen](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacereopen)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.ContextMenu>  
 <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType>  
 [Общие сведения о базовых элементах](../../../../docs/framework/wpf/advanced/base-elements-overview.md)  
 [Общие сведения об элементе ContextMenu](../../../../docs/framework/wpf/controls/contextmenu-overview.md)
