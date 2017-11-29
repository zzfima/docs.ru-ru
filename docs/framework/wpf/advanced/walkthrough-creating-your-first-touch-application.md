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
ms.openlocfilehash: ee85a5d8764fc27205cf09e1af43069b25096ef1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-your-first-touch-application"></a><span data-ttu-id="9efeb-102">Пошаговое руководство. Создание первого приложения для обработки касаний</span><span class="sxs-lookup"><span data-stu-id="9efeb-102">Walkthrough: Creating Your First Touch Application</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="9efeb-103">позволяет приложениям реагировать на сенсорный ввод.</span><span class="sxs-lookup"><span data-stu-id="9efeb-103"> enables applications to respond to touch.</span></span> <span data-ttu-id="9efeb-104">Например может взаимодействовать с приложением с помощью одного или несколько пальцев на сенсорные устройства, например сенсорный экран, в данном пошаговом руководстве создается приложение, которое позволяет пользователю перемещать, изменять размер или поворот объекта с использованием сенсорного ввода.</span><span class="sxs-lookup"><span data-stu-id="9efeb-104">For example, you can interact with an application by using one or more fingers on a touch-sensitive device, such as a touchscreen This walkthrough creates an application that enables the user to move, resize, or rotate a single object by using touch.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9efeb-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9efeb-105">Prerequisites</span></span>  
 <span data-ttu-id="9efeb-106">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="9efeb-106">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)]<span data-ttu-id="9efeb-107">.</span><span class="sxs-lookup"><span data-stu-id="9efeb-107">.</span></span>  
  
-   <span data-ttu-id="9efeb-108">Windows 7.</span><span class="sxs-lookup"><span data-stu-id="9efeb-108">Windows 7.</span></span>  
  
-   <span data-ttu-id="9efeb-109">Устройство, которое принимает сенсорного ввода, например сенсорный экран, который поддерживает технологии касания Windows.</span><span class="sxs-lookup"><span data-stu-id="9efeb-109">A device that accepts touch input, such as a touchscreen, that supports Windows Touch.</span></span>  
  
 <span data-ttu-id="9efeb-110">Кроме того, необходимо иметь базовое представление о том, как создать приложение в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], особенно как подписывание и обработка события.</span><span class="sxs-lookup"><span data-stu-id="9efeb-110">Additionally, you should have a basic understanding of how to create an application in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], especially how to subscribe to and handle an event.</span></span> <span data-ttu-id="9efeb-111">Дополнительные сведения см. в разделе [Пошаговое руководство: My первого классического приложения WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="9efeb-111">For more information, see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>  
  
## <a name="creating-the-application"></a><span data-ttu-id="9efeb-112">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="9efeb-112">Creating the Application</span></span>  
  
#### <a name="to-create-the-application"></a><span data-ttu-id="9efeb-113">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="9efeb-113">To create the application</span></span>  
  
1.  <span data-ttu-id="9efeb-114">Создайте проект приложения WPF на Visual Basic или Visual C# с именем `BasicManipulation`.</span><span class="sxs-lookup"><span data-stu-id="9efeb-114">Create a new WPF Application project in Visual Basic or Visual C# named `BasicManipulation`.</span></span> <span data-ttu-id="9efeb-115">Дополнительные сведения см. в разделе [Практическое руководство. Создание нового проекта приложения WPF](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span><span class="sxs-lookup"><span data-stu-id="9efeb-115">For more information, see [How to: Create a New WPF Application Project](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
2.  <span data-ttu-id="9efeb-116">Замените содержимое файла MainWindow.XAML на следующий код XAML.</span><span class="sxs-lookup"><span data-stu-id="9efeb-116">Replace the contents of MainWindow.xaml with the following XAML.</span></span>  
  
     <span data-ttu-id="9efeb-117">Эта разметка создает простое приложение, которое содержит красной <xref:System.Windows.Shapes.Rectangle> на <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="9efeb-117">This markup creates a simple application that contains a red <xref:System.Windows.Shapes.Rectangle> on a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="9efeb-118"><xref:System.Windows.UIElement.IsManipulationEnabled%2A> Свойство <xref:System.Windows.Shapes.Rectangle> имеет значение true, чтобы он будет получать события манипуляции.</span><span class="sxs-lookup"><span data-stu-id="9efeb-118">The <xref:System.Windows.UIElement.IsManipulationEnabled%2A> property of the <xref:System.Windows.Shapes.Rectangle> is set to true so that it will receive manipulation events.</span></span> <span data-ttu-id="9efeb-119">Приложение подписывается на <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta>, и <xref:System.Windows.UIElement.ManipulationInertiaStarting> события.</span><span class="sxs-lookup"><span data-stu-id="9efeb-119">The application subscribes to the <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta>, and <xref:System.Windows.UIElement.ManipulationInertiaStarting> events.</span></span> <span data-ttu-id="9efeb-120">Эти события содержат логику, чтобы переместить <xref:System.Windows.Shapes.Rectangle> когда пользователь выполняет операции с ним.</span><span class="sxs-lookup"><span data-stu-id="9efeb-120">These events contain the logic to move the <xref:System.Windows.Shapes.Rectangle> when the user manipulates it.</span></span>  
  
     [!code-xaml[BasicManipulation#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml#ui)]  
  
3.  <span data-ttu-id="9efeb-121">При использовании Visual Basic в первой строке файла MainWindow.XAML замените `x:Class="BasicManipulation.MainWindow"` с `x:Class="MainWindow"`.</span><span class="sxs-lookup"><span data-stu-id="9efeb-121">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="BasicManipulation.MainWindow"` with `x:Class="MainWindow"`.</span></span>  
  
4.  <span data-ttu-id="9efeb-122">В `MainWindow` класса, добавьте следующий <xref:System.Windows.UIElement.ManipulationStarting> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="9efeb-122">In the `MainWindow` class, add the following <xref:System.Windows.UIElement.ManipulationStarting> event handler.</span></span>  
  
     <span data-ttu-id="9efeb-123"><xref:System.Windows.UIElement.ManipulationStarting> Событие возникает при [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обнаруживает, что сенсорный ввод начал манипулирование объектом.</span><span class="sxs-lookup"><span data-stu-id="9efeb-123">The <xref:System.Windows.UIElement.ManipulationStarting> event occurs when [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] detects that touch input begins to manipulate an object.</span></span> <span data-ttu-id="9efeb-124">Код указывает, что положение манипуляции должно быть относительно <xref:System.Windows.Window> , установив <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="9efeb-124">The code specifies that the position of the manipulation should be relative to the <xref:System.Windows.Window> by setting the <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> property.</span></span>  
  
     [!code-csharp[BasicManipulation#ManipulationStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationstarting)]
     [!code-vb[BasicManipulation#ManipulationStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationstarting)]  
  
5.  <span data-ttu-id="9efeb-125">В `MainWindow` класса, добавьте следующий <xref:System.Windows.Input.ManipulationDelta> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="9efeb-125">In the `MainWindow` class, add the following <xref:System.Windows.Input.ManipulationDelta> event handler.</span></span>  
  
     <span data-ttu-id="9efeb-126"><xref:System.Windows.Input.ManipulationDelta> Событие возникает, когда сенсорный ввод изменяет положение и может встречаться несколько раз во время обработки.</span><span class="sxs-lookup"><span data-stu-id="9efeb-126">The <xref:System.Windows.Input.ManipulationDelta> event occurs when the touch input changes position and can occur multiple times during a manipulation.</span></span> <span data-ttu-id="9efeb-127">Это событие также может возникать после возникновения палец.</span><span class="sxs-lookup"><span data-stu-id="9efeb-127">The event can also occur after a finger is raised.</span></span> <span data-ttu-id="9efeb-128">Например, если пользователь перетаскивает пальцем по экрану <xref:System.Windows.Input.ManipulationDelta> событие возникает несколько раз за перемещения пальца.</span><span class="sxs-lookup"><span data-stu-id="9efeb-128">For example, if the user drags a finger across a screen, the <xref:System.Windows.Input.ManipulationDelta> event occurs multiple times as the finger moves.</span></span> <span data-ttu-id="9efeb-129">Когда пользователь отрывает палец с экрана, <xref:System.Windows.Input.ManipulationDelta> событие продолжает возникать для имитации инерции.</span><span class="sxs-lookup"><span data-stu-id="9efeb-129">When the user raises a finger from the screen, the <xref:System.Windows.Input.ManipulationDelta> event keeps occurring to simulate inertia.</span></span>  
  
     <span data-ttu-id="9efeb-130">В коде применяется <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> для <xref:System.Windows.UIElement.RenderTransform%2A> из <xref:System.Windows.Shapes.Rectangle> Чтобы переместить его, когда пользователь перемещает сенсорный ввод.</span><span class="sxs-lookup"><span data-stu-id="9efeb-130">The code applies the <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> to the <xref:System.Windows.UIElement.RenderTransform%2A> of the <xref:System.Windows.Shapes.Rectangle> to move it as the user moves the touch input.</span></span> <span data-ttu-id="9efeb-131">Он также проверяет, является ли <xref:System.Windows.Shapes.Rectangle> находится за пределами границ <xref:System.Windows.Window> при возникновении события во время инерции.</span><span class="sxs-lookup"><span data-stu-id="9efeb-131">It also checks whether the <xref:System.Windows.Shapes.Rectangle> is outside the bounds of the <xref:System.Windows.Window> when the event occurs during inertia.</span></span> <span data-ttu-id="9efeb-132">Если Да, приложение вызывает <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> для завершения манипуляции.</span><span class="sxs-lookup"><span data-stu-id="9efeb-132">If so, the application calls the <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> method to end the manipulation.</span></span>  
  
     [!code-csharp[BasicManipulation#ManipulationDelta](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationdelta)]
     [!code-vb[BasicManipulation#ManipulationDelta](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationdelta)]  
  
6.  <span data-ttu-id="9efeb-133">В `MainWindow` класса, добавьте следующий <xref:System.Windows.UIElement.ManipulationInertiaStarting> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="9efeb-133">In the `MainWindow` class, add the following <xref:System.Windows.UIElement.ManipulationInertiaStarting> event handler.</span></span>  
  
     <span data-ttu-id="9efeb-134"><xref:System.Windows.UIElement.ManipulationInertiaStarting> Событие происходит, когда пользователь отрывает все пальца на экране.</span><span class="sxs-lookup"><span data-stu-id="9efeb-134">The <xref:System.Windows.UIElement.ManipulationInertiaStarting> event occurs when the user raises all fingers from the screen.</span></span> <span data-ttu-id="9efeb-135">Код задает начальную скорость и замедление для перемещения, расширения и поворота прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="9efeb-135">The code sets the initial velocity and deceleration for the movement, expansion, and rotation of the rectangle.</span></span>  
  
     [!code-csharp[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationinertiastarting)]
     [!code-vb[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationinertiastarting)]  
  
7.  <span data-ttu-id="9efeb-136">Постройте и запустите проект.</span><span class="sxs-lookup"><span data-stu-id="9efeb-136">Build and run the project.</span></span>  
  
     <span data-ttu-id="9efeb-137">Вы увидите красный квадрат отображаются в окне.</span><span class="sxs-lookup"><span data-stu-id="9efeb-137">You should see a red square appear in the window.</span></span>  
  
## <a name="testing-the-application"></a><span data-ttu-id="9efeb-138">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="9efeb-138">Testing the Application</span></span>  
 <span data-ttu-id="9efeb-139">Чтобы проверить приложение, попробуйте следующие манипуляции.</span><span class="sxs-lookup"><span data-stu-id="9efeb-139">To test the application, try the following manipulations.</span></span> <span data-ttu-id="9efeb-140">Обратите внимание, что можно сделать более одного из следующих действий, в то же время.</span><span class="sxs-lookup"><span data-stu-id="9efeb-140">Note that you can do more than one of the following at the same time.</span></span>  
  
-   <span data-ttu-id="9efeb-141">Чтобы переместить <xref:System.Windows.Shapes.Rectangle>, поместите палец на <xref:System.Windows.Shapes.Rectangle> и перемещайте его по экрану.</span><span class="sxs-lookup"><span data-stu-id="9efeb-141">To move the <xref:System.Windows.Shapes.Rectangle>, put a finger on the <xref:System.Windows.Shapes.Rectangle> and move the finger across the screen.</span></span>  
  
-   <span data-ttu-id="9efeb-142">Чтобы изменить размер <xref:System.Windows.Shapes.Rectangle>, поместите два пальца на <xref:System.Windows.Shapes.Rectangle> и Сведите ближе к другу или дальше отстоят друг от друга.</span><span class="sxs-lookup"><span data-stu-id="9efeb-142">To resize the <xref:System.Windows.Shapes.Rectangle>, put two fingers on the <xref:System.Windows.Shapes.Rectangle> and move the fingers closer together or farther apart from each other.</span></span>  
  
-   <span data-ttu-id="9efeb-143">Значение поворота <xref:System.Windows.Shapes.Rectangle>, поместите два пальца на <xref:System.Windows.Shapes.Rectangle> и Поворачивайте пальцы вокруг друг с другом.</span><span class="sxs-lookup"><span data-stu-id="9efeb-143">To rotate the <xref:System.Windows.Shapes.Rectangle>, put two fingers on the <xref:System.Windows.Shapes.Rectangle> and rotate the fingers around each other.</span></span>  
  
 <span data-ttu-id="9efeb-144">Чтобы вызвать инерцию, быстро вызывать пальцев на экране при выполнении предыдущих манипуляций.</span><span class="sxs-lookup"><span data-stu-id="9efeb-144">To cause inertia, quickly raise your fingers from the screen as you perform the previous manipulations.</span></span> <span data-ttu-id="9efeb-145"><xref:System.Windows.Shapes.Rectangle> Будет продолжать перемещения, размер или поворачивать на несколько секунд, прежде чем остановится.</span><span class="sxs-lookup"><span data-stu-id="9efeb-145">The <xref:System.Windows.Shapes.Rectangle> will continue to move, resize, or rotate for a few seconds before it stops.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9efeb-146">См. также</span><span class="sxs-lookup"><span data-stu-id="9efeb-146">See Also</span></span>  
 <xref:System.Windows.UIElement.ManipulationStarting?displayProperty=nameWithType>  
 <xref:System.Windows.UIElement.ManipulationDelta?displayProperty=nameWithType>  
 <xref:System.Windows.UIElement.ManipulationInertiaStarting?displayProperty=nameWithType>
