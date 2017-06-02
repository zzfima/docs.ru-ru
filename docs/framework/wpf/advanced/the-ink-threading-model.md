---
title: "Потоковая модель рукописного ввода | Microsoft Docs"
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
  - "поток пользовательского интерфейса приложения"
  - "поток динамической отрисовки"
  - "подключаемый модуль приема рукописного ввода"
  - "потоковая модель рукописного ввода"
  - "рукописный ввод, отрисовка"
  - "поток пера"
  - "подключаемые модули, для рукописного ввода"
  - "отрисовка рукописных данных"
  - "подключаемый модуль пера"
  - "потоковая модель"
ms.assetid: c85fcad1-cb50-4431-847c-ac4145a35c89
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Потоковая модель рукописного ввода
Одним из преимуществ рукописного ввода на планшетных ПК является его сходство с письмом обычной ручкой на бумаге.  Чтобы добиться этого, перу планшета приходится получать входные данные гораздо быстрее мыши и отображать рукописные данные как записи пользователя.  Потока пользовательского интерфейса приложения недостаточно для сбора данных пера и отрисовки рукописного ввода, так как он может быть заблокирован.  Чтобы устранить эту проблему, приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует два дополнительных потока, когда пользователь осуществляет рукописный ввод.  
  
 Ниже перечислены потоки, принимающие участие в сборе и отрисовке цифровых рукописных данных:  
  
-   Потоком пера является поток, который принимает ввод от пера.  \(На самом деле, это пул потоков, но в этом разделе он называется потоком пера.\)  
  
-   Потоком пользовательского интерфейса приложения является поток, управляющий пользовательским интерфейсом приложения.  
  
-   Потоком динамической отрисовки является поток, отображающий рукописные данные при вводе пользователем каждого штриха.  Поток динамической отрисовки отличается от потока, отображающего другие элементы пользовательского интерфейса приложения, как указывается в разделе [Модель потоков](../../../../docs/framework/wpf/advanced/threading-model.md) WPF.  
  
 Используется одна и та же модель рукописного ввода, независимо от того, использует приложение <xref:System.Windows.Controls.InkCanvas> или пользовательский элемент управления, аналогичный элементу управления в [Создание элемента управления рукописным вводом](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).  Хотя в этом разделе обсуждаются потоки в терминах <xref:System.Windows.Controls.InkCanvas>, те же принципы применяются для создания пользовательского элемента управления.  
  
## Общие сведения о работе с потоками  
 На следующей схеме показана модель потоков в момент, когда пользователь рисует штрих:  
  
 ![Потоковая модель во время отрисовки мазка.](../../../../docs/framework/wpf/advanced/media/inkthreading-drawingink.png "InkThreading\_DrawingInk")  
  
1.  Действия, происходящие во время рисования пользователем штриха  
  
    1.  Когда пользователь рисует штрих, точки пера поставляются в поток пера.  Подключаемые модули пера, включая <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, принимают точки пера в потоке пера и имеют возможность изменить их, прежде чем их получит <xref:System.Windows.Controls.InkCanvas>.  
  
    2.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> воспроизводит точки пера в потоке динамической отрисовки.  Это происходит одновременно с предыдущим шагом.  
  
    3.  <xref:System.Windows.Controls.InkCanvas> получает точки пера в поток пользовательского интерфейса.  
  
2.  Действия, происходящие после того, как пользователь завершает штрих  
  
    1.  Когда пользователь прекращает рисование штриха, <xref:System.Windows.Controls.InkCanvas> создает объект <xref:System.Windows.Ink.Stroke> и добавляет его к <xref:System.Windows.Controls.InkPresenter>, который статически его отображает.  
  
    2.  Поток пользовательского интерфейса оповещает <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, что штрих отображен статически, поэтому <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> удаляет его визуальное представление.  
  
## Коллекция рукописного ввода и подключаемые модули пера  
 Каждый <xref:System.Windows.UIElement> имеет <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.  Объекты в <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> получают точки пера и могут изменять их в потоке пера.  Объекты <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> получают точки пера согласно их порядку в <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.  
  
 Следующая диаграмма иллюстрирует гипотетическую ситуацию, когда коллекция <xref:System.Windows.UIElement.StylusPlugIns%2A> элементов <xref:System.Windows.UIElement> содержит `stylusPlugin1`, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> и `stylusPlugin2` в указанном порядке.  
  
 ![Порядок вывода подключаемых модулей пера.](../../../../docs/framework/wpf/advanced/media/inkthreading-pluginorder.png "InkThreading\_PluginOrder")  
  
 На предыдущей иллюстрации имеет место следующая ситуация:  
  
1.  `StylusPlugin1` изменяет значения x и y.  
  
2.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> получает измененные точки пера и помещает их в поток динамической отрисовки.  
  
3.  `StylusPlugin2` получает измененные точки пера и выполняет дальнейшие изменения значений x и y.  
  
4.  Приложение собирает точки пера и статически отображает штрих, когда пользователь завершает штрих.  
  
 Предположим, что `stylusPlugin1` ограничивает точки пера прямоугольной областью, а `stylusPlugin2` переносит точки пера вправо.  В предыдущем сценарии <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> получает ограниченные, но не перенесенные точки пера.  Во время рисования штрих отображается в пределах прямоугольной области, но он не доступен для переноса до тех пор, пока пользователь не оторвет от планшета перо.  
  
### Выполнение операций с подключаемым модулем пера в потоке пользовательского интерфейса  
 Так как в потоке пера не может быть выполнена точная проверка нахождения пера в пределах элемента, некоторые элементы могут иногда получать ввод от пера, предназначенный для других элементов.  Если перед выполнением операции необходимо убедиться, что входные данные было правильно направлены, выполните подписку и воспользуйтесь одним из следующих методов: <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusDownProcessed%2A>, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusMoveProcessed%2A> или <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusUpProcessed%2A>.  Эти методы вызываются потоком приложения после того, как была проведена точная проверка расположения пера.  Для подписки на эти методы вызовите метод <xref:System.Windows.Input.StylusPlugIns.RawStylusInput.NotifyWhenProcessed%2A> в методе, выполняющемся в потоке пера.  
  
 На следующей диаграмме показана связь между потоком пера и потоком пользовательского интерфейса по отношению к событиям пера <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>.  
  
 ![Потоковые модели рукописного ввода &#40;пользовательский интерфейс и перо&#41;](../../../../docs/framework/wpf/advanced/media/inkthreading-plugincallbacks.png "InkThreading\_PluginCallbacks")  
  
## Отрисовка рукописных данных  
 Когда пользователь рисует штрих, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> отображает рукописные данные в отдельном потоке, поэтому данные «идут» от пера в поток, даже когда поток пользовательского интерфейса занят.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> строит визуальное дерево потока динамической отрисовки, который получает точки пера.  Когда пользователь заканчивает рисование штриха, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> запрашивает уведомление о том, что приложение выполняет следующий шаг генерации изображения.  После того как приложение завершит следующий этап отрисовки, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> очистит свое визуальное дерево.  Этот процесс показан на следующей схеме.  
  
 ![Схема обработки рукописного ввода](../../../../docs/framework/wpf/advanced/media/inkthreading-visualtree.png "InkThreading\_VisualTree")  
  
1.  Пользователь начинает рисовать штрих.  
  
    1.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> создает визуальное дерево.  
  
2.  Пользователь рисует штрих.  
  
    1.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> строит визуальное дерево.  
  
3.  Пользователь завершает рисование штриха.  
  
    1.  <xref:System.Windows.Controls.InkPresenter> добавляет штрих в визуальное дерево.  
  
    2.  MIL статически отображает штрихи.  
  
    3.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> очищает визуальные элементы.