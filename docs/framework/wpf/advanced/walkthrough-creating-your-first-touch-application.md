---
title: "Пошаговое руководство. Создание первого приложения для обработки касаний"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating a touch-sensitive application [WPF]
- touchscreen applications [WPF], creating
- touch-sensitive applications [WPF], creating
- creating a touchscreen application [WPF]
ms.assetid: d69e602e-9a25-4e24-950b-e89eaa2a906b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 08f4004329d15b527a889cd7b437a7f18278fc79
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-creating-your-first-touch-application"></a>Пошаговое руководство. Создание первого приложения для обработки касаний
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]позволяет приложениям реагировать на сенсорный ввод. Например может взаимодействовать с приложением с помощью одного или несколько пальцев на сенсорные устройства, например сенсорный экран, в данном пошаговом руководстве создается приложение, которое позволяет пользователю перемещать, изменять размер или поворот объекта с использованием сенсорного ввода.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)].  
  
-   Windows 7.  
  
-   Устройство, которое принимает сенсорного ввода, например сенсорный экран, который поддерживает технологии касания Windows.  
  
 Кроме того, необходимо иметь базовое представление о том, как создать приложение в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], особенно как подписывание и обработка события. Дополнительные сведения см. в разделе [Пошаговое руководство: My первого классического приложения WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="creating-the-application"></a>Создание приложения  
  
#### <a name="to-create-the-application"></a>Создание приложения  
  
1.  Создайте проект приложения WPF на Visual Basic или Visual C# с именем `BasicManipulation`. Дополнительные сведения см. в разделе [Практическое руководство. Создание нового проекта приложения WPF](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
2.  Замените содержимое файла MainWindow.XAML на следующий код XAML.  
  
     Эта разметка создает простое приложение, которое содержит красной <xref:System.Windows.Shapes.Rectangle> на <xref:System.Windows.Controls.Canvas>. <xref:System.Windows.UIElement.IsManipulationEnabled%2A> Свойство <xref:System.Windows.Shapes.Rectangle> имеет значение true, чтобы он будет получать события манипуляции. Приложение подписывается на <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta>, и <xref:System.Windows.UIElement.ManipulationInertiaStarting> события. Эти события содержат логику, чтобы переместить <xref:System.Windows.Shapes.Rectangle> когда пользователь выполняет операции с ним.  
  
     [!code-xaml[BasicManipulation#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml#ui)]  
  
3.  При использовании Visual Basic в первой строке файла MainWindow.XAML замените `x:Class="BasicManipulation.MainWindow"` с `x:Class="MainWindow"`.  
  
4.  В `MainWindow` класса, добавьте следующий <xref:System.Windows.UIElement.ManipulationStarting> обработчика событий.  
  
     <xref:System.Windows.UIElement.ManipulationStarting> Событие возникает при [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обнаруживает, что сенсорный ввод начал манипулирование объектом. Код указывает, что положение манипуляции должно быть относительно <xref:System.Windows.Window> , установив <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> свойство.  
  
     [!code-csharp[BasicManipulation#ManipulationStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationstarting)]
     [!code-vb[BasicManipulation#ManipulationStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationstarting)]  
  
5.  В `MainWindow` класса, добавьте следующий <xref:System.Windows.Input.ManipulationDelta> обработчика событий.  
  
     <xref:System.Windows.Input.ManipulationDelta> Событие возникает, когда сенсорный ввод изменяет положение и может встречаться несколько раз во время обработки. Это событие также может возникать после возникновения палец. Например, если пользователь перетаскивает пальцем по экрану <xref:System.Windows.Input.ManipulationDelta> событие возникает несколько раз за перемещения пальца. Когда пользователь отрывает палец с экрана, <xref:System.Windows.Input.ManipulationDelta> событие продолжает возникать для имитации инерции.  
  
     В коде применяется <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> для <xref:System.Windows.UIElement.RenderTransform%2A> из <xref:System.Windows.Shapes.Rectangle> Чтобы переместить его, когда пользователь перемещает сенсорный ввод. Он также проверяет, является ли <xref:System.Windows.Shapes.Rectangle> находится за пределами границ <xref:System.Windows.Window> при возникновении события во время инерции. Если Да, приложение вызывает <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> для завершения манипуляции.  
  
     [!code-csharp[BasicManipulation#ManipulationDelta](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationdelta)]
     [!code-vb[BasicManipulation#ManipulationDelta](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationdelta)]  
  
6.  В `MainWindow` класса, добавьте следующий <xref:System.Windows.UIElement.ManipulationInertiaStarting> обработчика событий.  
  
     <xref:System.Windows.UIElement.ManipulationInertiaStarting> Событие происходит, когда пользователь отрывает все пальца на экране. Код задает начальную скорость и замедление для перемещения, расширения и поворота прямоугольника.  
  
     [!code-csharp[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationinertiastarting)]
     [!code-vb[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationinertiastarting)]  
  
7.  Постройте и запустите проект.  
  
     Вы увидите красный квадрат отображаются в окне.  
  
## <a name="testing-the-application"></a>Тестирование приложения  
 Чтобы проверить приложение, попробуйте следующие манипуляции. Обратите внимание, что можно сделать более одного из следующих действий, в то же время.  
  
-   Чтобы переместить <xref:System.Windows.Shapes.Rectangle>, поместите палец на <xref:System.Windows.Shapes.Rectangle> и перемещайте его по экрану.  
  
-   Чтобы изменить размер <xref:System.Windows.Shapes.Rectangle>, поместите два пальца на <xref:System.Windows.Shapes.Rectangle> и Сведите ближе к другу или дальше отстоят друг от друга.  
  
-   Значение поворота <xref:System.Windows.Shapes.Rectangle>, поместите два пальца на <xref:System.Windows.Shapes.Rectangle> и Поворачивайте пальцы вокруг друг с другом.  
  
 Чтобы вызвать инерцию, быстро вызывать пальцев на экране при выполнении предыдущих манипуляций. <xref:System.Windows.Shapes.Rectangle> Будет продолжать перемещения, размер или поворачивать на несколько секунд, прежде чем остановится.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.UIElement.ManipulationStarting?displayProperty=nameWithType>  
 <xref:System.Windows.UIElement.ManipulationDelta?displayProperty=nameWithType>  
 <xref:System.Windows.UIElement.ManipulationInertiaStarting?displayProperty=nameWithType>
