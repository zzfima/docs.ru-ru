---
title: "Пошаговое руководство. Создание первого приложения для обработки касаний | Microsoft Docs"
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
  - "создание приложения для сенсорного экрана [WPF]"
  - "создание приложения для экрана, чувствительного к касаниям [WPF]"
  - "приложения для сенсорного экрана [WPF], создание"
  - "приложения для экрана, чувствительного к касаниям [WPF], создание"
ms.assetid: d69e602e-9a25-4e24-950b-e89eaa2a906b
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Пошаговое руководство. Создание первого приложения для обработки касаний
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяет приложениям реагировать на сенсорный ввод.  Например, можно взаимодействовать с приложением, используя пальцы на экране, чувствительном к касаниям, например на сенсорном экране. В данном пошаговом руководстве создается приложение, которое позволяет пользователям перемещать, изменять размеры и выполнять циклический сдвиг одного объекта с использованием касания.  
  
## Предварительные требования  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)].  
  
-   Windows 7.  
  
-   Устройство, принимающее сенсорный ввод, например сенсорный экран с поддержкой технологии касания Windows.  
  
 Кроме того, необходимо иметь базовое понимание процесса создания приложения в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], особенно такие его аспекты, как подписывание и обработка события.  Дополнительные сведения см. в разделе [Пошаговое руководство. Начало работы с WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## Создание приложения  
  
#### Чтобы создать приложение  
  
1.  Создайте в Visual Basic или Visual C\# новый проект приложения WPF с именем `BasicManipulation`.  Дополнительные сведения см. в разделе [Практическое руководство. Создание нового проекта приложения WPF](http://msdn.microsoft.com/ru-ru/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
2.  Замените содержимое файла MainWindow.xaml следующим XAML.  
  
     Разметка создает простое приложение, содержащее красный прямоугольник <xref:System.Windows.Shapes.Rectangle> на канве <xref:System.Windows.Controls.Canvas>.  Свойство <xref:System.Windows.UIElement.IsManipulationEnabled%2A> этого объекта <xref:System.Windows.Shapes.Rectangle> установлено в значение "true", так что он будет получать события манипулирования.  Приложение подписывается на события <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta> и <xref:System.Windows.UIElement.ManipulationInertiaStarting>.  Эти события содержат логику перемещения объекта <xref:System.Windows.Shapes.Rectangle>, когда пользователь им манипулирует.  
  
     [!code-xml[BasicManipulation#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml#ui)]  
  
3.  Если используется Visual Basic, замените `x:Class="BasicManipulation.MainWindow"` в первой строке файла MainWindow.xaml на `x:Class="MainWindow"`.  
  
4.  В класс `MainWindow` добавьте следующий обработчик событий <xref:System.Windows.UIElement.ManipulationStarting>.  
  
     Событие <xref:System.Windows.UIElement.ManipulationStarting> возникает, когда [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обнаруживает, что сенсорный ввод начал манипулирование объектом.  Этот код задает, что положение манипуляции должно быть относительно <xref:System.Windows.Window>, путем установки свойства <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A>.  
  
     [!code-csharp[BasicManipulation#ManipulationStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationstarting)]
     [!code-vb[BasicManipulation#ManipulationStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationstarting)]  
  
5.  В класс `MainWindow` добавьте следующий обработчик событий <xref:System.Windows.Input.ManipulationDelta>.  
  
     Событие <xref:System.Windows.Input.ManipulationDelta> возникает, когда сенсорный ввод изменяет положение, и может возникать несколько раз в течение манипуляции.  Это событие также может возникать после отрыва пальца от экрана.  Например, если пользователь перемещает палец по экрану, событие <xref:System.Windows.Input.ManipulationDelta> возникает несколько раз за время перемещения пальца.  Когда пользователь отрывает палец от экрана, событие <xref:System.Windows.Input.ManipulationDelta> продолжает возникать для имитации инерции.  
  
     Этот код применяет свойство <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> к свойству <xref:System.Windows.UIElement.RenderTransform%2A> объекта <xref:System.Windows.Shapes.Rectangle>, чтобы перемещать его, как пользователь перемещает сенсорный ввод.  Он также выполняет проверку, не находится ли объект <xref:System.Windows.Shapes.Rectangle> за пределами границ окна <xref:System.Windows.Window>, когда событие возникает вследствие инерции.  Если это так, то приложение вызывает метод [имеет значение M:System.Windows.Input.ManipulationDeltaEventArgs.Complete](assetId:///имеет значение M:System.Windows.Input.ManipulationDeltaEventArgs.Complete?qualifyHint=True&autoUpgrade=True), чтобы завершить манипуляцию.  
  
     [!code-csharp[BasicManipulation#ManipulationDelta](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationdelta)]
     [!code-vb[BasicManipulation#ManipulationDelta](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationdelta)]  
  
6.  В класс `MainWindow` добавьте следующий обработчик событий <xref:System.Windows.UIElement.ManipulationInertiaStarting>.  
  
     Событие <xref:System.Windows.UIElement.ManipulationInertiaStarting> возникает, когда пользователь отрывает от экрана все пальцы.  Код устанавливает исходную скорость и замедление для движения, расширения и поворота прямоугольника.  
  
     [!code-csharp[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationinertiastarting)]
     [!code-vb[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationinertiastarting)]  
  
7.  Выполните построение и запуск проекта.  
  
     В окне должен появиться красный квадрат.  
  
## Тестирование приложения  
 Чтобы протестировать приложение, попытайтесь выполнить следующие манипуляции.  Следует отметить, что одновременно можно выполнять несколько приведенных ниже действий.  
  
-   Чтобы переместить объект <xref:System.Windows.Shapes.Rectangle>, поместите палец на <xref:System.Windows.Shapes.Rectangle> и перемещайте его по экрану.  
  
-   Чтобы изменить размер объекта <xref:System.Windows.Shapes.Rectangle>, поместите два пальца на <xref:System.Windows.Shapes.Rectangle> и перемещайте пальцы ближе друг к другу или дальше друг от друга.  
  
-   Чтобы повернуть объект <xref:System.Windows.Shapes.Rectangle>, поместите два пальца на <xref:System.Windows.Shapes.Rectangle> и поворачивайте пальцы друг вокруг друга.  
  
 Чтобы вызвать инерцию, быстро оторвите пальцы от экрана во время выполнения предыдущих манипуляций.  Объект <xref:System.Windows.Shapes.Rectangle> будет продолжать перемещаться, изменять размер или поворачиваться еще несколько секунд, прежде чем остановится.  
  
## См. также  
 <xref:System.Windows.UIElement.ManipulationStarting?displayProperty=fullName>   
 <xref:System.Windows.UIElement.ManipulationDelta?displayProperty=fullName>   
 <xref:System.Windows.UIElement.ManipulationInertiaStarting?displayProperty=fullName>