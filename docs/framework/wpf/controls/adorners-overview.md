---
title: "Общие сведения о декоративных элементах"
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
helpviewer_keywords: adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
caps.latest.revision: "35"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47b43b1b9848f91e77448d41609d8be5d60ecda5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="adorners-overview"></a><span data-ttu-id="83764-102">Общие сведения о декоративных элементах</span><span class="sxs-lookup"><span data-stu-id="83764-102">Adorners Overview</span></span>
<span data-ttu-id="83764-103">Графические элементы — это специальный тип <xref:System.Windows.FrameworkElement>, использующимся для предоставления пользователю визуальные подсказки.</span><span class="sxs-lookup"><span data-stu-id="83764-103">Adorners are a special type of <xref:System.Windows.FrameworkElement>, used to provide visual cues to a user.</span></span> <span data-ttu-id="83764-104">Помимо прочего, декоративные элементы можно использовать для добавления функциональных дескрипторов к элементам или предоставления информации о состоянии элемента управления.</span><span class="sxs-lookup"><span data-stu-id="83764-104">Among other uses, Adorners can be used to add functional handles to elements or provide state information about a control.</span></span>  
  
  
  
<a name="about_Adorners"></a>   
## <a name="about-adorners"></a><span data-ttu-id="83764-105">Сведения о декоративных элементах</span><span class="sxs-lookup"><span data-stu-id="83764-105">About Adorners</span></span>  
 <span data-ttu-id="83764-106"><xref:System.Windows.Documents.Adorner> Является пользовательским <xref:System.Windows.FrameworkElement> , привязанный к <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="83764-106">An <xref:System.Windows.Documents.Adorner> is a custom <xref:System.Windows.FrameworkElement> that is bound to a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="83764-107">Графические элементы отображаются в <xref:System.Windows.Documents.AdornerLayer>, который является поверхностью отрисовки на самом верху графического элемента или коллекции графических элементов.</span><span class="sxs-lookup"><span data-stu-id="83764-107">Adorners are rendered in an <xref:System.Windows.Documents.AdornerLayer>, which is a rendering surface that is always on top of the adorned element or a collection of adorned elements.</span></span> <span data-ttu-id="83764-108">Отрисовка графического элемента не зависит от отрисовки <xref:System.Windows.UIElement> , к которому привязан графический элемент.</span><span class="sxs-lookup"><span data-stu-id="83764-108">Rendering of an adorner is independent from rendering of the <xref:System.Windows.UIElement> that the adorner is bound to.</span></span> <span data-ttu-id="83764-109">Декоративный элемент обычно располагается относительно элемента, к которому он привязан, с использованием стандартной двухмерной системы координат с началом отсчета в левом верхнем углу графического элемента.</span><span class="sxs-lookup"><span data-stu-id="83764-109">An adorner is typically positioned relative to the element to which it is bound, using the standard 2-D coordinate origin located at the upper-left of the adorned element.</span></span>  
  
 <span data-ttu-id="83764-110">Типичные сценарии использования декоративных элементов:</span><span class="sxs-lookup"><span data-stu-id="83764-110">Common applications for adorners include:</span></span>  
  
-   <span data-ttu-id="83764-111">Добавление функциональных обработчиков <xref:System.Windows.UIElement> , дать пользователю возможность манипулировать элементом иным образом (изменять размеры, вращать, перемещать, и т. д.).</span><span class="sxs-lookup"><span data-stu-id="83764-111">Adding functional handles to a <xref:System.Windows.UIElement> that enable a user to manipulate the element in some way (resize, rotate, reposition, etc.).</span></span>  
  
-   <span data-ttu-id="83764-112">Обеспечение визуальной обратной связи для указания различных состояний или в ответ на различные события.</span><span class="sxs-lookup"><span data-stu-id="83764-112">Provide visual feedback to indicate various states, or in response to various events.</span></span>  
  
-   <span data-ttu-id="83764-113">Наложение визуальных декораторов на <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="83764-113">Overlay visual decorations on a <xref:System.Windows.UIElement>.</span></span>  
  
-   <span data-ttu-id="83764-114">Визуально маскировать или переопределять частично или полностью <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="83764-114">Visually mask or override part or all of a <xref:System.Windows.UIElement>.</span></span>  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="83764-115"> предоставляет базовую среду для декоративных визуальных элементов.</span><span class="sxs-lookup"><span data-stu-id="83764-115"> provides a basic framework for adorning visual elements.</span></span> <span data-ttu-id="83764-116">В следующей таблице перечислены основные типы, используемые при настройке объектов, и их назначение.</span><span class="sxs-lookup"><span data-stu-id="83764-116">The following table lists the primary types used when adorning objects, and their purpose.</span></span> <span data-ttu-id="83764-117">Ниже приведено несколько примеров использования.</span><span class="sxs-lookup"><span data-stu-id="83764-117">Several usage examples follow.</span></span>  
  
|||  
|-|-|  
|<xref:System.Windows.Documents.Adorner>|<span data-ttu-id="83764-118">Абстрактный базовый класс, из которого наследуются все конкретные реализации декоративного элемента.</span><span class="sxs-lookup"><span data-stu-id="83764-118">An abstract base class from which all concrete adorner implementations inherit.</span></span>|  
|<xref:System.Windows.Documents.AdornerLayer>|<span data-ttu-id="83764-119">Класс, представляющий слой отрисовки декоративного элемента одного или нескольких настроенных элементов.</span><span class="sxs-lookup"><span data-stu-id="83764-119">A class representing a rendering layer for the adorner(s) of one or more adorned elements.</span></span>|  
|<xref:System.Windows.Documents.AdornerDecorator>|<span data-ttu-id="83764-120">Класс, который позволяет ассоциировать слой декоративного элемента с коллекцией элементов.</span><span class="sxs-lookup"><span data-stu-id="83764-120">A class that enables an adorner layer to be associated with a collection of elements.</span></span>|  
  
<a name="implement_custom_Adorner"></a>   
## <a name="implementing-a-custom-adorner"></a><span data-ttu-id="83764-121">Реализация пользовательского декоративного элемента</span><span class="sxs-lookup"><span data-stu-id="83764-121">Implementing a Custom Adorner</span></span>  
 <span data-ttu-id="83764-122">Среда декоративных элементов, предоставляемая [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], предназначена в первую очередь для поддержки создания пользовательских декоративных элементов.</span><span class="sxs-lookup"><span data-stu-id="83764-122">The adorners framework provided by [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is intended primarily to support the creation of custom adorners.</span></span> <span data-ttu-id="83764-123">Пользовательский графический элемент создается путем реализации класса, который наследует от абстрактного <xref:System.Windows.Documents.Adorner> класса.</span><span class="sxs-lookup"><span data-stu-id="83764-123">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83764-124">Родительский <xref:System.Windows.Documents.Adorner> — <xref:System.Windows.Documents.AdornerLayer> , выводящий <xref:System.Windows.Documents.Adorner>, не являющийся графическим элементом.</span><span class="sxs-lookup"><span data-stu-id="83764-124">The parent of an <xref:System.Windows.Documents.Adorner> is the <xref:System.Windows.Documents.AdornerLayer> that renders the <xref:System.Windows.Documents.Adorner>, not the element being adorned.</span></span>  
  
 <span data-ttu-id="83764-125">В следующем примере показан класс, который реализует простой декоративный элемент.</span><span class="sxs-lookup"><span data-stu-id="83764-125">The following example shows a class that implements a simple adorner.</span></span> <span data-ttu-id="83764-126">В примере декоративный элемент просто украшает углы <xref:System.Windows.UIElement> окружностями.</span><span class="sxs-lookup"><span data-stu-id="83764-126">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
 <span data-ttu-id="83764-127">На следующем рисунке показана SimpleCircleAdorner, применить к <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="83764-127">The following image shows the SimpleCircleAdorner applied to a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 <span data-ttu-id="83764-128">![Пример декоративных элементов — настроенное текстовое поле](../../../../docs/framework/wpf/controls/media/adornedtextbox.png "AdornedTextBox")</span><span class="sxs-lookup"><span data-stu-id="83764-128">![Adorners Example: An adorned TextBox](../../../../docs/framework/wpf/controls/media/adornedtextbox.png "AdornedTextBox")</span></span>  
  
<a name="rendering_behavior_for_Adorners"></a>   
## <a name="rendering-behavior-for-adorners"></a><span data-ttu-id="83764-129">Поведение отрисовки для декоративных элементов</span><span class="sxs-lookup"><span data-stu-id="83764-129">Rendering Behavior for Adorners</span></span>  
 <span data-ttu-id="83764-130">Важно отметить, что декоративные элементы не включают какое-либо обязательное поведение отрисовки. За результат применения декоративного элемента отвечает его автор.</span><span class="sxs-lookup"><span data-stu-id="83764-130">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span>   <span data-ttu-id="83764-131">Распространенным способом реализации поведения визуализации является переопределение <xref:System.Windows.UIElement.OnRender%2A> метод и использование одного или нескольких <xref:System.Windows.Media.DrawingContext> объектов для подготовки к просмотру декоратора по мере необходимости (как показано в примере выше).</span><span class="sxs-lookup"><span data-stu-id="83764-131">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in the example above).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83764-132">Все, что помещено в слой декоративного элемента, отрисовывается поверх остальных установленных стилей.</span><span class="sxs-lookup"><span data-stu-id="83764-132">Anything placed in the adorner layer is rendered on top of the rest of any styles you have set.</span></span> <span data-ttu-id="83764-133">Другими словами, декоративные элементы всегда визуально находятся сверху и не могут быть переопределены с помощью упорядочения по z-координате.</span><span class="sxs-lookup"><span data-stu-id="83764-133">In other words, adorners are always visually on top and cannot be overridden using z-order.</span></span>  
  
<a name="adorner_events_hittest"></a>   
## <a name="events-and-hit-testing"></a><span data-ttu-id="83764-134">События и проверка нажатия</span><span class="sxs-lookup"><span data-stu-id="83764-134">Events and Hit Testing</span></span>  
 <span data-ttu-id="83764-135">Декораторы получают события ввода так же, как и любой другой <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="83764-135">Adorners receive input events just like any other <xref:System.Windows.FrameworkElement>.</span></span>  <span data-ttu-id="83764-136">Так как графический элемент всегда имеет более высоким z порядком чем элемент, используемая для его оформления, декоративный элемент принимает входные события (такие как <xref:System.Windows.UIElement.Drop> или <xref:System.Windows.UIElement.MouseMove>), может быть предназначено для базового оформить элемент.</span><span class="sxs-lookup"><span data-stu-id="83764-136">Because an adorner always has a higher z-order than the element it adorns, the adorner receives input events (such as <xref:System.Windows.UIElement.Drop> or <xref:System.Windows.UIElement.MouseMove>) that may be intended for the underlying adorned element.</span></span>  <span data-ttu-id="83764-137">Декоративный элемент может отслеживать определенные события ввода и передавать их в базовый декорированный элемент, повторно запуская событие.</span><span class="sxs-lookup"><span data-stu-id="83764-137">An adorner can listen for certain input events and pass these on to the underlying adorned element by re-raising the event.</span></span>  
  
 <span data-ttu-id="83764-138">Чтобы включить передачу проверки попадания элементов под графический элемент, задайте нажатия <xref:System.Windows.UIElement.IsHitTestVisible%2A> свойства **false** декоративного элемента.</span><span class="sxs-lookup"><span data-stu-id="83764-138">To enable pass-through hit testing of elements under an adorner, set the hit test <xref:System.Windows.UIElement.IsHitTestVisible%2A> property to **false** on the adorner.</span></span>  <span data-ttu-id="83764-139">Дополнительные сведения о проверке нажатия см. в разделе</span><span class="sxs-lookup"><span data-stu-id="83764-139">For more information about hit testing, see</span></span>  
  
 <span data-ttu-id="83764-140">[Проверка нажатия в визуальном слое](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md).</span><span class="sxs-lookup"><span data-stu-id="83764-140">[Hit Testing in the Visual Layer](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md).</span></span>  
  
<a name="adorn_single_element"></a>   
## <a name="adorning-a-single-uielement"></a><span data-ttu-id="83764-141">Декорирование одного элемента пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="83764-141">Adorning a Single UIElement</span></span>  
 <span data-ttu-id="83764-142">Для привязки к конкретному графический элемент <xref:System.Windows.UIElement>, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="83764-142">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="83764-143">Вызовите статический метод <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> для получения <xref:System.Windows.Documents.AdornerLayer> для объекта <xref:System.Windows.UIElement> оформляемого.</span><span class="sxs-lookup"><span data-stu-id="83764-143">Call the static method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="83764-144"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>перемещается вверх по дереву visual, начиная с указанного <xref:System.Windows.UIElement>и возвращает первый слой графических элементов, которые найдет.</span><span class="sxs-lookup"><span data-stu-id="83764-144"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified <xref:System.Windows.UIElement>, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="83764-145">(Если слои декоративных элементов не найдены, метод возвращает значение 0.)</span><span class="sxs-lookup"><span data-stu-id="83764-145">(If no adorner layers are found, the method returns null.)</span></span>  
  
2.  <span data-ttu-id="83764-146">Вызовите <xref:System.Windows.Documents.AdornerLayer.Add%2A> метода для привязки к целевому декоратора <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="83764-146">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target <xref:System.Windows.UIElement>.</span></span>  
  
 <span data-ttu-id="83764-147">Следующий пример привязывает (показано выше) для SimpleCircleAdorner <xref:System.Windows.Controls.TextBox> с именем *myTextBox*.</span><span class="sxs-lookup"><span data-stu-id="83764-147">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  <span data-ttu-id="83764-148">Использование [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для привязки декоративного элемента к другому элементу в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="83764-148">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
<a name="adorn_children_panel"></a>   
## <a name="adorning-the-children-of-a-panel"></a><span data-ttu-id="83764-149">Декорирование дочерних объектов панели</span><span class="sxs-lookup"><span data-stu-id="83764-149">Adorning the Children of a Panel</span></span>  
 <span data-ttu-id="83764-150">Для привязки элемента оформления к дочерним элементам <xref:System.Windows.Controls.Panel>, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="83764-150">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="83764-151">Вызовите `static` метод <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> найти слой графических элементов, дочерние элементы которого являются оформляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="83764-151">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to find an adorner layer for the element whose children are to be adorned.</span></span>  
  
2.  <span data-ttu-id="83764-152">Перечисление дочерних элементов родительского элемента и вызовите <xref:System.Windows.Documents.AdornerLayer.Add%2A> метода для привязки элемента оформления к каждому дочернему элементу.</span><span class="sxs-lookup"><span data-stu-id="83764-152">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>  
  
 <span data-ttu-id="83764-153">Следующий пример привязывает (показано выше) к дочерним элементам SimpleCircleAdorner <xref:System.Windows.Controls.StackPanel> с именем *myStackPanel*.</span><span class="sxs-lookup"><span data-stu-id="83764-153">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
## <a name="see-also"></a><span data-ttu-id="83764-154">См. также</span><span class="sxs-lookup"><span data-stu-id="83764-154">See Also</span></span>  
 <xref:System.Windows.Media.AdornerHitTestResult>  
 [<span data-ttu-id="83764-155">Обзор фигур и базовых средств рисования в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="83764-155">Shapes and Basic Drawing in WPF Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [<span data-ttu-id="83764-156">Заполнение с использованием изображений, рисунков и визуальных элементов</span><span class="sxs-lookup"><span data-stu-id="83764-156">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [<span data-ttu-id="83764-157">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="83764-157">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="83764-158">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="83764-158">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/adorners-how-to-topics.md)
