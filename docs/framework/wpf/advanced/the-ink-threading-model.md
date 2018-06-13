---
title: Потоковая модель рукописного ввода
ms.date: 03/30/2017
helpviewer_keywords:
- application user interface thread [WPF]
- stylus plug-in
- ink threading model [WPF]
- ink [WPF], rendering
- pen thread [WPF]
- threading model [WPF]
- rendering ink [WPF]
- dynamic rendering thread [WPF]
- ink collection plug-in
- plug-ins [WPF], for ink
ms.assetid: c85fcad1-cb50-4431-847c-ac4145a35c89
ms.openlocfilehash: cc0ff8a2345bd945dd2fffdfda80f00e1ab99c67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547883"
---
# <a name="the-ink-threading-model"></a>Потоковая модель рукописного ввода
Одно из преимуществ рукописного ввода на планшетных ПК — что он сходство с записи с обычной ручкой и документ.  Для этого пера получать входные данные гораздо быстрее мыши и отображает рукописные данные как записи пользователя.  Потока пользовательского интерфейса приложения недостаточно для сбора данных пера и отображения рукописного ввода, так как он может быть заблокирован.  Чтобы устранить эту проблему, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложение использует два дополнительных потока, когда пользователь осуществляет рукописный ввод.  
  
 Ниже перечислены потоки, принимающие участие в сборе и отображении рукописного ввода.  
  
-   Потоком пера потока, который принимает ввод от пера.  (На самом деле это пул потоков, но в этом разделе он называется потоком пера.)  
  
-   Потоком пользовательского интерфейса приложения - поток, который определяет пользовательский интерфейс приложения.  
  
-   Поток динамической отрисовки - поток, который отображает рукописные данные, то время как пользователь штриха. Поток динамической отрисовки отличается от потока, отображающего другие элементы пользовательского интерфейса для приложения, как было сказано в окне WPF [потоковая модель](../../../../docs/framework/wpf/advanced/threading-model.md).  
  
 Модель рукописного ввода совпадает ли приложение использует <xref:System.Windows.Controls.InkCanvas> или пользовательского элемента управления подобное в [создания элемента управления ввода рукописного ввода](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).  Несмотря на то, что в этом разделе обсуждаются потоки в терминах <xref:System.Windows.Controls.InkCanvas>, те же принципы применяются при создании пользовательского элемента управления.  
  
## <a name="threading-overview"></a>Работа с потоками Обзор  
 На следующей схеме показана модель потоков, когда пользователем штриха:  
  
 ![Потоковая модель во время отрисовки мазка. ] (../../../../docs/framework/wpf/advanced/media/inkthreading-drawingink.png "InkThreading_DrawingInk")  
  
1.  Действия, происходящие во время рисования штрих  
  
    1.  Когда пользователь рисует штрих, точки пера поставляются в потоке пера.  Подключаемые модули пера, включая <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, принимают точки пера в потоке пера и иметь возможность изменить их, прежде чем <xref:System.Windows.Controls.InkCanvas> их получает.  
  
    2.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Воспроизводит точки пера в потоке динамической отрисовки. Это происходит в то же время на предыдущем этапе.  
  
    3.  <xref:System.Windows.Controls.InkCanvas> Получает точки пера в потоке пользовательского интерфейса.  
  
2.  Действия, происходящие после пользователь завершает штрих  
  
    1.  Когда пользователь завершает рисование штриха, <xref:System.Windows.Controls.InkCanvas> создает <xref:System.Windows.Ink.Stroke> объекта и добавляет его в <xref:System.Windows.Controls.InkPresenter>, который статически его отображает.  
  
    2.  Поток пользовательского интерфейса оповещает <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> , статически штриха отображается, поэтому <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> удаляет его визуальное представление штриха.  
  
## <a name="ink-collection-and-stylus-plug-ins"></a>Коллекция рукописного ввода и подключаемых модулей пера  
 Каждый <xref:System.Windows.UIElement> имеет <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.  <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Объекты в <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> получать и изменять точки пера в потоке пера. <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Объекты получают точки пера согласно порядку их следования в <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.  
  
 На следующей схеме показана гипотетическая ситуация где <xref:System.Windows.UIElement.StylusPlugIns%2A> коллекцию <xref:System.Windows.UIElement> содержит `stylusPlugin1`, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, и `stylusPlugin2`в этом порядке.  
  
 ![Порядок модулей пера влияет на выходные данные. ] (../../../../docs/framework/wpf/advanced/media/inkthreading-pluginorder.png "InkThreading_PluginOrder")  
  
 На предыдущей диаграмме выполняется следующим образом:  
  
1.  `StylusPlugin1` изменяет значения x и y.  
  
2.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Получает измененные точки пера и помещает их в поток динамической отрисовки.  
  
3.  `StylusPlugin2` Получает измененные точки пера и выполняет дальнейшие изменения значений x и y.  
  
4.  Приложение собирает точки пера и, когда пользователь завершает штрих статически отображает штриха.  
  
 Предположим, что `stylusPlugin1` ограничивает точки пера в прямоугольник и `stylusPlugin2` переносит точки пера вправо.  В приведенном выше сценарии <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> принимает ограниченные, но не перенесенные точки пера.  Когда пользователь рисует обводку, штриха отображается в пределах границ прямоугольника, но он не доступен для перевода, пока пользователь отрывает перо.  
  
### <a name="performing-operations-with-a-stylus-plug-in-on-the-ui-thread"></a>Выполнение операций с подключаемым модулем в потоке пользовательского интерфейса пера  
 Поскольку точные попадания не может выполняться в потоке пера, некоторые элементы могут иногда получать ввод от пера предназначен для других элементов. Если требуется, чтобы убедиться, что входные данные было правильно направлены до выполнения операции, подписаться и выполнить операцию в <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusDownProcessed%2A>, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusMoveProcessed%2A>, или <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusUpProcessed%2A> метод. Эти методы вызываются потоком приложения после завершения проверки актуальности проверки нажатия. Для подписки на эти методы вызовите <xref:System.Windows.Input.StylusPlugIns.RawStylusInput.NotifyWhenProcessed%2A> в методе, который выполняется в потоке пера.  
  
 На следующей схеме показана связь между потоком пера и потоком пользовательского интерфейса по отношению к событиям пера <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>.  
  
 ![Потоковые модели рукописного ввода &#40;пользовательский Интерфейс и перо&#41;](../../../../docs/framework/wpf/advanced/media/inkthreading-plugincallbacks.png "InkThreading_PluginCallbacks")  
  
## <a name="rendering-ink"></a>Подготовка к просмотру рукописного ввода  
 Как пользователь штриха, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> отображает рукописные данные в отдельном потоке, поэтому данные «идут» от пера даже в том случае, если поток пользовательского интерфейса занят.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Строит визуальное дерево в потоке динамической отрисовки, который получает точки пера.  Когда пользователь завершает штрих <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> запросом получать уведомления, когда приложение выполняет следующий этап отрисовки.  После завершения работы приложения следующего прохода отрисовки <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> очищает его визуального дерева.  Этот процесс показан на следующей схеме.  
  
 ![Работа с потоками схема рукописного ввода](../../../../docs/framework/wpf/advanced/media/inkthreading-visualtree.png "InkThreading_VisualTree")  
  
1.  Пользователь начинает штриха.  
  
    1.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Создает визуальное дерево.  
  
2.  Пользователь рисует штриха.  
  
    1.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Строит визуальное дерево.  
  
3.  Пользователь завершает штриха.  
  
    1.  <xref:System.Windows.Controls.InkPresenter> Добавляет штрих в визуальном дереве.  
  
    2.  Уровень интеграции носителя (MIL) статически отображает штрихи.  
  
    3.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Очищает визуальные элементы.
