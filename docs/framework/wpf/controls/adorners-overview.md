---
title: Общие сведения о декоративных элементах
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
ms.openlocfilehash: d8e6e53edc92a2847c001377706d313cf97cced5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956093"
---
# <a name="adorners-overview"></a><span data-ttu-id="6ba20-102">Общие сведения о декоративных элементах</span><span class="sxs-lookup"><span data-stu-id="6ba20-102">Adorners Overview</span></span>
<span data-ttu-id="6ba20-103">Декораторы — это особый тип <xref:System.Windows.FrameworkElement>, используемый для предоставления визуальных подсказок пользователю.</span><span class="sxs-lookup"><span data-stu-id="6ba20-103">Adorners are a special type of <xref:System.Windows.FrameworkElement>, used to provide visual cues to a user.</span></span> <span data-ttu-id="6ba20-104">Помимо прочего, декоративные элементы можно использовать для добавления функциональных дескрипторов к элементам или предоставления информации о состоянии элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6ba20-104">Among other uses, Adorners can be used to add functional handles to elements or provide state information about a control.</span></span>  

<a name="about_Adorners"></a>   
## <a name="about-adorners"></a><span data-ttu-id="6ba20-105">Сведения о декоративных элементах</span><span class="sxs-lookup"><span data-stu-id="6ba20-105">About Adorners</span></span>  
 <span data-ttu-id="6ba20-106">Является пользовательским <xref:System.Windows.FrameworkElement> , привязанным к. <xref:System.Windows.UIElement> <xref:System.Windows.Documents.Adorner></span><span class="sxs-lookup"><span data-stu-id="6ba20-106">An <xref:System.Windows.Documents.Adorner> is a custom <xref:System.Windows.FrameworkElement> that is bound to a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="6ba20-107">Декораторы подготавливаются к <xref:System.Windows.Documents.AdornerLayer>просмотру в, который представляет собой область отрисовки, которая всегда находится над декоративным элементом или коллекцией декоративных элементов.</span><span class="sxs-lookup"><span data-stu-id="6ba20-107">Adorners are rendered in an <xref:System.Windows.Documents.AdornerLayer>, which is a rendering surface that is always on top of the adorned element or a collection of adorned elements.</span></span> <span data-ttu-id="6ba20-108">Отрисовка декоративного элемента не зависит от отрисовки <xref:System.Windows.UIElement> элемента, к которому привязан декоративный элемент.</span><span class="sxs-lookup"><span data-stu-id="6ba20-108">Rendering of an adorner is independent from rendering of the <xref:System.Windows.UIElement> that the adorner is bound to.</span></span> <span data-ttu-id="6ba20-109">Декоративный элемент обычно располагается относительно элемента, к которому он привязан, с использованием стандартной двухмерной системы координат с началом отсчета в левом верхнем углу графического элемента.</span><span class="sxs-lookup"><span data-stu-id="6ba20-109">An adorner is typically positioned relative to the element to which it is bound, using the standard 2-D coordinate origin located at the upper-left of the adorned element.</span></span>  
  
 <span data-ttu-id="6ba20-110">Типичные сценарии использования декоративных элементов:</span><span class="sxs-lookup"><span data-stu-id="6ba20-110">Common applications for adorners include:</span></span>  
  
- <span data-ttu-id="6ba20-111">Добавление функциональных дескрипторов <xref:System.Windows.UIElement> в, позволяющих пользователю манипулировать элементом каким-либо образом (изменение размера, вращение, перемещение и т. д.).</span><span class="sxs-lookup"><span data-stu-id="6ba20-111">Adding functional handles to a <xref:System.Windows.UIElement> that enable a user to manipulate the element in some way (resize, rotate, reposition, etc.).</span></span>  
  
- <span data-ttu-id="6ba20-112">Обеспечение визуальной обратной связи для указания различных состояний или в ответ на различные события.</span><span class="sxs-lookup"><span data-stu-id="6ba20-112">Provide visual feedback to indicate various states, or in response to various events.</span></span>  
  
- <span data-ttu-id="6ba20-113">Наложение визуальных украшений на <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="6ba20-113">Overlay visual decorations on a <xref:System.Windows.UIElement>.</span></span>  
  
- <span data-ttu-id="6ba20-114">Визуальная маскировка или переопределение части или <xref:System.Windows.UIElement>всех элементов.</span><span class="sxs-lookup"><span data-stu-id="6ba20-114">Visually mask or override part or all of a <xref:System.Windows.UIElement>.</span></span>  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="6ba20-115">предоставляет базовую среду для декоративных визуальных элементов.</span><span class="sxs-lookup"><span data-stu-id="6ba20-115">provides a basic framework for adorning visual elements.</span></span> <span data-ttu-id="6ba20-116">В следующей таблице перечислены основные типы, используемые при настройке объектов, и их назначение.</span><span class="sxs-lookup"><span data-stu-id="6ba20-116">The following table lists the primary types used when adorning objects, and their purpose.</span></span> <span data-ttu-id="6ba20-117">Ниже приведено несколько примеров использования.</span><span class="sxs-lookup"><span data-stu-id="6ba20-117">Several usage examples follow.</span></span>  
  
|||  
|-|-|  
|<xref:System.Windows.Documents.Adorner>|<span data-ttu-id="6ba20-118">Абстрактный базовый класс, из которого наследуются все конкретные реализации декоративного элемента.</span><span class="sxs-lookup"><span data-stu-id="6ba20-118">An abstract base class from which all concrete adorner implementations inherit.</span></span>|  
|<xref:System.Windows.Documents.AdornerLayer>|<span data-ttu-id="6ba20-119">Класс, представляющий слой отрисовки декоративного элемента одного или нескольких настроенных элементов.</span><span class="sxs-lookup"><span data-stu-id="6ba20-119">A class representing a rendering layer for the adorner(s) of one or more adorned elements.</span></span>|  
|<xref:System.Windows.Documents.AdornerDecorator>|<span data-ttu-id="6ba20-120">Класс, который позволяет ассоциировать слой декоративного элемента с коллекцией элементов.</span><span class="sxs-lookup"><span data-stu-id="6ba20-120">A class that enables an adorner layer to be associated with a collection of elements.</span></span>|  
  
<a name="implement_custom_Adorner"></a>   
## <a name="implementing-a-custom-adorner"></a><span data-ttu-id="6ba20-121">Реализация пользовательского декоративного элемента</span><span class="sxs-lookup"><span data-stu-id="6ba20-121">Implementing a Custom Adorner</span></span>  
 <span data-ttu-id="6ba20-122">Среда декоративных элементов, предоставляемая [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], предназначена в первую очередь для поддержки создания пользовательских декоративных элементов.</span><span class="sxs-lookup"><span data-stu-id="6ba20-122">The adorners framework provided by [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is intended primarily to support the creation of custom adorners.</span></span> <span data-ttu-id="6ba20-123">Пользовательский декоративный элемент создается путем реализации класса, который наследует от абстрактного <xref:System.Windows.Documents.Adorner> класса.</span><span class="sxs-lookup"><span data-stu-id="6ba20-123">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6ba20-124">Родителем объекта <xref:System.Windows.Documents.Adorner> <xref:System.Windows.Documents.AdornerLayer> является объект, который визуализирует <xref:System.Windows.Documents.Adorner>, а не элемент, декоративный.</span><span class="sxs-lookup"><span data-stu-id="6ba20-124">The parent of an <xref:System.Windows.Documents.Adorner> is the <xref:System.Windows.Documents.AdornerLayer> that renders the <xref:System.Windows.Documents.Adorner>, not the element being adorned.</span></span>  
  
 <span data-ttu-id="6ba20-125">В следующем примере показан класс, который реализует простой декоративный элемент.</span><span class="sxs-lookup"><span data-stu-id="6ba20-125">The following example shows a class that implements a simple adorner.</span></span> <span data-ttu-id="6ba20-126">Пример декоративного элемента просто декоративно углы <xref:System.Windows.UIElement> с круговыми кругами.</span><span class="sxs-lookup"><span data-stu-id="6ba20-126">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
 <span data-ttu-id="6ba20-127">На следующем рисунке показан SimpleCircleAdorner, применяемый к <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="6ba20-127">The following image shows the SimpleCircleAdorner applied to a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 ![Снимок экрана, на котором отображается декоративное текстовое поле.](./media/adorners-overview/simplecircleadorner-textbox.png)  
  
<a name="rendering_behavior_for_Adorners"></a>   
## <a name="rendering-behavior-for-adorners"></a><span data-ttu-id="6ba20-129">Поведение отрисовки для декоративных элементов</span><span class="sxs-lookup"><span data-stu-id="6ba20-129">Rendering Behavior for Adorners</span></span>  
 <span data-ttu-id="6ba20-130">Важно отметить, что декоративные элементы не включают какое-либо обязательное поведение отрисовки. За результат применения декоративного элемента отвечает его автор.</span><span class="sxs-lookup"><span data-stu-id="6ba20-130">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span>   <span data-ttu-id="6ba20-131">Обычным способом реализации поведения при отрисовке является переопределение <xref:System.Windows.UIElement.OnRender%2A> метода и использование одного или нескольких <xref:System.Windows.Media.DrawingContext> объектов для отрисовки визуальных элементов декоративного элемента по мере необходимости (как показано в примере выше).</span><span class="sxs-lookup"><span data-stu-id="6ba20-131">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in the example above).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6ba20-132">Все, что помещено в слой декоративного элемента, отрисовывается поверх остальных установленных стилей.</span><span class="sxs-lookup"><span data-stu-id="6ba20-132">Anything placed in the adorner layer is rendered on top of the rest of any styles you have set.</span></span> <span data-ttu-id="6ba20-133">Другими словами, декоративные элементы всегда визуально находятся сверху и не могут быть переопределены с помощью упорядочения по z-координате.</span><span class="sxs-lookup"><span data-stu-id="6ba20-133">In other words, adorners are always visually on top and cannot be overridden using z-order.</span></span>  
  
<a name="adorner_events_hittest"></a>   
## <a name="events-and-hit-testing"></a><span data-ttu-id="6ba20-134">События и проверка нажатия</span><span class="sxs-lookup"><span data-stu-id="6ba20-134">Events and Hit Testing</span></span>  
 <span data-ttu-id="6ba20-135">Декораторы получают события ввода так же, как <xref:System.Windows.FrameworkElement>и любые другие.</span><span class="sxs-lookup"><span data-stu-id="6ba20-135">Adorners receive input events just like any other <xref:System.Windows.FrameworkElement>.</span></span>  <span data-ttu-id="6ba20-136">Поскольку декоративный элемент всегда имеет более высокий z-порядок, чем элемент, на который он оформлен, декоративный элемент получает входные события <xref:System.Windows.UIElement.Drop> ( <xref:System.Windows.UIElement.MouseMove>например, или), которые могут быть предназначены для базового декоративного элемента.</span><span class="sxs-lookup"><span data-stu-id="6ba20-136">Because an adorner always has a higher z-order than the element it adorns, the adorner receives input events (such as <xref:System.Windows.UIElement.Drop> or <xref:System.Windows.UIElement.MouseMove>) that may be intended for the underlying adorned element.</span></span>  <span data-ttu-id="6ba20-137">Декоративный элемент может отслеживать определенные события ввода и передавать их в базовый декорированный элемент, повторно запуская событие.</span><span class="sxs-lookup"><span data-stu-id="6ba20-137">An adorner can listen for certain input events and pass these on to the underlying adorned element by re-raising the event.</span></span>  
  
 <span data-ttu-id="6ba20-138">Чтобы включить проверку попадания для элементов в декоративном элементе, задайте для свойства Проверка <xref:System.Windows.UIElement.IsHitTestVisible%2A> попадания **значение false** в декоративном элементе.</span><span class="sxs-lookup"><span data-stu-id="6ba20-138">To enable pass-through hit testing of elements under an adorner, set the hit test <xref:System.Windows.UIElement.IsHitTestVisible%2A> property to **false** on the adorner.</span></span>  <span data-ttu-id="6ba20-139">Дополнительные сведения о проверке нажатия см. в разделе</span><span class="sxs-lookup"><span data-stu-id="6ba20-139">For more information about hit testing, see</span></span>  
  
 <span data-ttu-id="6ba20-140">[Проверка нажатия в визуальном слое](../graphics-multimedia/hit-testing-in-the-visual-layer.md).</span><span class="sxs-lookup"><span data-stu-id="6ba20-140">[Hit Testing in the Visual Layer](../graphics-multimedia/hit-testing-in-the-visual-layer.md).</span></span>  
  
<a name="adorn_single_element"></a>   
## <a name="adorning-a-single-uielement"></a><span data-ttu-id="6ba20-141">Декорирование одного элемента пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="6ba20-141">Adorning a Single UIElement</span></span>  
 <span data-ttu-id="6ba20-142">Чтобы привязать декоративный элемент к конкретному <xref:System.Windows.UIElement>, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6ba20-142">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>  
  
1. <span data-ttu-id="6ba20-143">Вызовите статический метод <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> , чтобы <xref:System.Windows.Documents.AdornerLayer> получить объект для элемента <xref:System.Windows.UIElement> , который должен быть оформлен.</span><span class="sxs-lookup"><span data-stu-id="6ba20-143">Call the static method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="6ba20-144"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>переходит вверх по визуальному дереву, начиная с <xref:System.Windows.UIElement>указанного, и возвращает первый найденный слой декоративных элементов.</span><span class="sxs-lookup"><span data-stu-id="6ba20-144"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified <xref:System.Windows.UIElement>, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="6ba20-145">(Если слои декоративных элементов не найдены, метод возвращает значение 0.)</span><span class="sxs-lookup"><span data-stu-id="6ba20-145">(If no adorner layers are found, the method returns null.)</span></span>  
  
2. <span data-ttu-id="6ba20-146">Вызовите <xref:System.Windows.UIElement>метод, чтобы привязать декоративный элемент к целевому объекту. <xref:System.Windows.Documents.AdornerLayer.Add%2A></span><span class="sxs-lookup"><span data-stu-id="6ba20-146">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target <xref:System.Windows.UIElement>.</span></span>  
  
 <span data-ttu-id="6ba20-147">В следующем примере показано, как привязать SimpleCircleAdorner (показанный выше <xref:System.Windows.Controls.TextBox> ) к именованной *митекстбокс*.</span><span class="sxs-lookup"><span data-stu-id="6ba20-147">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
> <span data-ttu-id="6ba20-148">Использование [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для привязки декоративного элемента к другому элементу в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="6ba20-148">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
<a name="adorn_children_panel"></a>   
## <a name="adorning-the-children-of-a-panel"></a><span data-ttu-id="6ba20-149">Декорирование дочерних объектов панели</span><span class="sxs-lookup"><span data-stu-id="6ba20-149">Adorning the Children of a Panel</span></span>  
 <span data-ttu-id="6ba20-150">Чтобы привязать декоративный элемент к дочерним <xref:System.Windows.Controls.Panel>элементам, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6ba20-150">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>  
  
1. <span data-ttu-id="6ba20-151">Вызовите <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> метод, чтобы найти слой декоративных элементов для элемента, чьи дочерние элементы должны быть декоративными. `static`</span><span class="sxs-lookup"><span data-stu-id="6ba20-151">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to find an adorner layer for the element whose children are to be adorned.</span></span>  
  
2. <span data-ttu-id="6ba20-152">Перечислите дочерние элементы родительского элемента и вызовите <xref:System.Windows.Documents.AdornerLayer.Add%2A> метод для привязки декоративного элемента к каждому дочернему элементу.</span><span class="sxs-lookup"><span data-stu-id="6ba20-152">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>  
  
 <span data-ttu-id="6ba20-153">В следующем примере показано, как привязать SimpleCircleAdorner (показанный выше) к дочерним элементам <xref:System.Windows.Controls.StackPanel> именованного *мистаккпанел*.</span><span class="sxs-lookup"><span data-stu-id="6ba20-153">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
## <a name="see-also"></a><span data-ttu-id="6ba20-154">См. также</span><span class="sxs-lookup"><span data-stu-id="6ba20-154">See also</span></span>

- <xref:System.Windows.Media.AdornerHitTestResult>
- [<span data-ttu-id="6ba20-155">Обзор фигур и базовых средств рисования в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="6ba20-155">Shapes and Basic Drawing in WPF Overview</span></span>](../graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="6ba20-156">Заполнение с использованием изображений, рисунков и визуальных элементов</span><span class="sxs-lookup"><span data-stu-id="6ba20-156">Painting with Images, Drawings, and Visuals</span></span>](../graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="6ba20-157">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="6ba20-157">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="6ba20-158">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="6ba20-158">How-to Topics</span></span>](adorners-how-to-topics.md)
