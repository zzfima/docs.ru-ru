---
title: Пошаговое руководство. Создание первого приложения для обработки касаний
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating a touch-sensitive application [WPF]
- touchscreen applications [WPF], creating
- touch-sensitive applications [WPF], creating
- creating a touchscreen application [WPF]
ms.assetid: d69e602e-9a25-4e24-950b-e89eaa2a906b
ms.openlocfilehash: ee2eddf0ad0818658920aff19919c4b5fef807b9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43511412"
---
# <a name="walkthrough-creating-your-first-touch-application"></a>Пошаговое руководство. Создание первого приложения для обработки касаний
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяет приложениям реагировать на касание. Например может взаимодействовать с приложением с помощью одного или более пальцами сенсорные устройства, например сенсорный экран, в этом пошаговом руководстве создается приложение, которое позволяет пользователю перемещать, изменять размер или поворот объекта с использованием сенсорного ввода.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)].  
  
-   Windows 7.  
  
-   Устройство, которое принимает сенсорного ввода, например сенсорный экран, который поддерживает Windows Touch.  
  
 Кроме того, должен иметь базовое представление о том, как создать приложение в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], особенно как подписаться на и как обрабатывать событие. Дополнительные сведения см. в разделе [Пошаговое руководство. Создание первого классического приложения WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="creating-the-application"></a>Создание приложения  
  
#### <a name="to-create-the-application"></a>Создание приложения  
  
1.  Создайте проект приложения WPF на Visual Basic или Visual C# с именем `BasicManipulation`. Дополнительные сведения см. в разделе [Практическое руководство. Создание нового проекта приложения WPF](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
2.  Замените содержимое файла MainWindow.XAML на следующий XAML.  
  
     Эта разметка создает простое приложение, содержащей красный <xref:System.Windows.Shapes.Rectangle> на <xref:System.Windows.Controls.Canvas>. <xref:System.Windows.UIElement.IsManipulationEnabled%2A> Свойство <xref:System.Windows.Shapes.Rectangle> имеет значение true, чтобы он будет получать события манипуляции. Приложение подписывается на <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta>, и <xref:System.Windows.UIElement.ManipulationInertiaStarting> события. Эти события содержат логику перемещения <xref:System.Windows.Shapes.Rectangle> когда пользователь выполняет операции с ним.  
  
     [!code-xaml[BasicManipulation#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml#ui)]  
  
3.  Если вы используете Visual Basic, в первой строке файла MainWindow.XAML, замените `x:Class="BasicManipulation.MainWindow"` с `x:Class="MainWindow"`.  
  
4.  В `MainWindow` класса, добавьте следующий <xref:System.Windows.UIElement.ManipulationStarting> обработчик событий.  
  
     <xref:System.Windows.UIElement.ManipulationStarting> Событие возникает при [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обнаруживает, что сенсорный ввод начал доступ к объекту. Код указывает, что позиция манипуляции относительно <xref:System.Windows.Window> , задав <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> свойство.  
  
     [!code-csharp[BasicManipulation#ManipulationStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationstarting)]
     [!code-vb[BasicManipulation#ManipulationStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationstarting)]  
  
5.  В `MainWindow` класса, добавьте следующий <xref:System.Windows.Input.ManipulationDelta> обработчик событий.  
  
     <xref:System.Windows.Input.ManipulationDelta> Событие возникает, когда сенсорный ввод изменяет положение и может встречаться несколько раз во время манипуляции. Это событие также может возникать после возникновения палец. Например, если пользователь перемещает палец по экрану <xref:System.Windows.Input.ManipulationDelta> событие возникает несколько раз как перемещения пальца. Когда пользователь отрывает палец с экрана, <xref:System.Windows.Input.ManipulationDelta> событие продолжает возникать для имитации инерции.  
  
     Код применяет <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> для <xref:System.Windows.UIElement.RenderTransform%2A> из <xref:System.Windows.Shapes.Rectangle> Чтобы переместить его, как пользователь перемещает сенсорный ввод. Он также проверяет ли <xref:System.Windows.Shapes.Rectangle> выходит за границы <xref:System.Windows.Window> при возникновении события во время инерции. Если таким образом, приложение вызывает <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> для завершения манипуляции.  
  
     [!code-csharp[BasicManipulation#ManipulationDelta](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationdelta)]
     [!code-vb[BasicManipulation#ManipulationDelta](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationdelta)]  
  
6.  В `MainWindow` класса, добавьте следующий <xref:System.Windows.UIElement.ManipulationInertiaStarting> обработчик событий.  
  
     <xref:System.Windows.UIElement.ManipulationInertiaStarting> Событие происходит, когда пользователь вызывает все пальцы на экране. Код задает начальную скорость и замедление для перемещения, расширения и поворота прямоугольника.  
  
     [!code-csharp[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationinertiastarting)]
     [!code-vb[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationinertiastarting)]  
  
7.  Постройте и запустите проект.  
  
     Вы увидите красный квадрат в окне.  
  
## <a name="testing-the-application"></a>Тестирование приложения  
 Чтобы протестировать приложение, попробуйте следующие манипуляции. Обратите внимание на то, что можно сделать более одного из указанных ниже, в то же время.  
  
-   Чтобы переместить <xref:System.Windows.Shapes.Rectangle>, поместите палец на <xref:System.Windows.Shapes.Rectangle> и переместите палец по экрану.  
  
-   Чтобы изменить размер <xref:System.Windows.Shapes.Rectangle>, поместите два пальца на <xref:System.Windows.Shapes.Rectangle> и Сведите Сведите или разведите их друг с другом.  
  
-   Для поворота <xref:System.Windows.Shapes.Rectangle>, поместите два пальца на <xref:System.Windows.Shapes.Rectangle> и Поворачивайте их вокруг друг с другом.  
  
 Чтобы вызвать инерцию, быстро повысить пальца на экране при выполнении предыдущих манипуляций. <xref:System.Windows.Shapes.Rectangle> Будет продолжать перемещения, размер или поворачивать на несколько секунд, прежде чем остановится.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.UIElement.ManipulationStarting?displayProperty=nameWithType>  
 <xref:System.Windows.UIElement.ManipulationDelta?displayProperty=nameWithType>  
 <xref:System.Windows.UIElement.ManipulationInertiaStarting?displayProperty=nameWithType>
