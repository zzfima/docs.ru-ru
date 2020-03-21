---
title: Общие сведения о декоративных элементах
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
ms.openlocfilehash: b41c1f10f7e1b7c1799fd27270a3eeb9899ceeb6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111183"
---
# <a name="adorners-overview"></a><span data-ttu-id="6d2c1-102">Общие сведения о декоративных элементах</span><span class="sxs-lookup"><span data-stu-id="6d2c1-102">Adorners Overview</span></span>

<span data-ttu-id="6d2c1-103">Adorners являются особым <xref:System.Windows.FrameworkElement>типом, используемым для предоставления визуальных сигналов для пользователя.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-103">Adorners are a special type of <xref:System.Windows.FrameworkElement>, used to provide visual cues to a user.</span></span> <span data-ttu-id="6d2c1-104">Помимо прочего, декоративные элементы можно использовать для добавления функциональных дескрипторов к элементам или предоставления информации о состоянии элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-104">Among other uses, Adorners can be used to add functional handles to elements or provide state information about a control.</span></span>

## <a name="about-adorners"></a><span data-ttu-id="6d2c1-105">Сведения о декоративных элементах</span><span class="sxs-lookup"><span data-stu-id="6d2c1-105">About Adorners</span></span>

<span data-ttu-id="6d2c1-106">An <xref:System.Windows.Documents.Adorner> это <xref:System.Windows.FrameworkElement> обычай, который <xref:System.Windows.UIElement>связан с .</span><span class="sxs-lookup"><span data-stu-id="6d2c1-106">An <xref:System.Windows.Documents.Adorner> is a custom <xref:System.Windows.FrameworkElement> that is bound to a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="6d2c1-107">Украшения отображаются <xref:System.Windows.Documents.AdornerLayer>в , который является рендеринга поверхности, которая всегда находится на вершине украшен элемент амортизированных элементов или коллекция украшенных элементов.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-107">Adorners are rendered in an <xref:System.Windows.Documents.AdornerLayer>, which is a rendering surface that is always on top of the adorned element or a collection of adorned elements.</span></span> <span data-ttu-id="6d2c1-108">Рендеринг оретора не зависит <xref:System.Windows.UIElement> от рендеринга того, к что должен быть привязан акрадер.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-108">Rendering of an adorner is independent from rendering of the <xref:System.Windows.UIElement> that the adorner is bound to.</span></span> <span data-ttu-id="6d2c1-109">Украшения, как правило, расположены по отношению к элементу, к которому он связан, используя стандартные 2D-координаты происхождения, расположенные в верхнем левом углу украшенного элемента.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-109">An adorner is typically positioned relative to the element to which it is bound, using the standard 2D coordinate origin located at the upper-left of the adorned element.</span></span>

<span data-ttu-id="6d2c1-110">Типичные сценарии использования декоративных элементов:</span><span class="sxs-lookup"><span data-stu-id="6d2c1-110">Common applications for adorners include:</span></span>

- <span data-ttu-id="6d2c1-111">Добавление функциональных ручек к элементу, <xref:System.Windows.UIElement> которое позволяет пользователю каким-то образом манипулировать элементом (изменять размер, поворачивать, перепозиционировать и т.д.).</span><span class="sxs-lookup"><span data-stu-id="6d2c1-111">Adding functional handles to a <xref:System.Windows.UIElement> that enable a user to manipulate the element in some way (resize, rotate, reposition, etc.).</span></span>
- <span data-ttu-id="6d2c1-112">Обеспечение визуальной обратной связи для указания различных состояний или в ответ на различные события.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-112">Provide visual feedback to indicate various states, or in response to various events.</span></span>
- <span data-ttu-id="6d2c1-113">Наложение визуальных <xref:System.Windows.UIElement>украшений на .</span><span class="sxs-lookup"><span data-stu-id="6d2c1-113">Overlay visual decorations on a <xref:System.Windows.UIElement>.</span></span>
- <span data-ttu-id="6d2c1-114">Визуально маска или переопределить часть <xref:System.Windows.UIElement>или все .</span><span class="sxs-lookup"><span data-stu-id="6d2c1-114">Visually mask or override part or all of a <xref:System.Windows.UIElement>.</span></span>

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="6d2c1-115">предоставляет базовую среду для декоративных визуальных элементов.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-115">provides a basic framework for adorning visual elements.</span></span> <span data-ttu-id="6d2c1-116">В следующей таблице перечислены основные типы, используемые при настройке объектов, и их назначение.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-116">The following table lists the primary types used when adorning objects, and their purpose.</span></span> <span data-ttu-id="6d2c1-117">Ниже приведены примеры использования:</span><span class="sxs-lookup"><span data-stu-id="6d2c1-117">Several usage examples follow:</span></span>

|||
|-|-|
|<xref:System.Windows.Documents.Adorner>|<span data-ttu-id="6d2c1-118">Абстрактный базовый класс, из которого наследуются все конкретные реализации декоративного элемента.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-118">An abstract base class from which all concrete adorner implementations inherit.</span></span>|
|<xref:System.Windows.Documents.AdornerLayer>|<span data-ttu-id="6d2c1-119">Класс, представляющий слой отрисовки декоративного элемента одного или нескольких настроенных элементов.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-119">A class representing a rendering layer for the adorner(s) of one or more adorned elements.</span></span>|
|<xref:System.Windows.Documents.AdornerDecorator>|<span data-ttu-id="6d2c1-120">Класс, который позволяет ассоциировать слой декоративного элемента с коллекцией элементов.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-120">A class that enables an adorner layer to be associated with a collection of elements.</span></span>|

## <a name="implementing-a-custom-adorner"></a><span data-ttu-id="6d2c1-121">Реализация пользовательского декоративного элемента</span><span class="sxs-lookup"><span data-stu-id="6d2c1-121">Implementing a Custom Adorner</span></span>

<span data-ttu-id="6d2c1-122">Среда декоративных элементов, предоставляемая [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], предназначена в первую очередь для поддержки создания пользовательских декоративных элементов.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-122">The adorners framework provided by [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is intended primarily to support the creation of custom adorners.</span></span> <span data-ttu-id="6d2c1-123">Пользовательский орелер создается путем реализации класса, который наследует от абстрактного <xref:System.Windows.Documents.Adorner> класса.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-123">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>

> [!NOTE]
> <span data-ttu-id="6d2c1-124">Родитель является <xref:System.Windows.Documents.Adorner> то, <xref:System.Windows.Documents.AdornerLayer> что оказывает, а <xref:System.Windows.Documents.Adorner>не элемент украшают.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-124">The parent of an <xref:System.Windows.Documents.Adorner> is the <xref:System.Windows.Documents.AdornerLayer> that renders the <xref:System.Windows.Documents.Adorner>, not the element being adorned.</span></span>

<span data-ttu-id="6d2c1-125">В следующем примере показан класс, который реализует простой декоративный элемент.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-125">The following example shows a class that implements a simple adorner.</span></span> <span data-ttu-id="6d2c1-126">Пример украшения просто украшает углы <xref:System.Windows.UIElement> с кругами.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-126">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles.</span></span>

[!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
[!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]
  
<span data-ttu-id="6d2c1-127">Следующее изображение показывает SimpleCircleAdorner <xref:System.Windows.Controls.TextBox>применяется к:</span><span class="sxs-lookup"><span data-stu-id="6d2c1-127">The following image shows the SimpleCircleAdorner applied to a <xref:System.Windows.Controls.TextBox>:</span></span>

![Скриншот, на который изображен украшенный текстовый ящик.](./media/adorners-overview/simplecircleadorner-textbox.png)

## <a name="rendering-behavior-for-adorners"></a><span data-ttu-id="6d2c1-129">Поведение отрисовки для декоративных элементов</span><span class="sxs-lookup"><span data-stu-id="6d2c1-129">Rendering Behavior for Adorners</span></span>

<span data-ttu-id="6d2c1-130">Важно отметить, что декоративные элементы не включают какое-либо обязательное поведение отрисовки. За результат применения декоративного элемента отвечает его автор.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-130">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span> <span data-ttu-id="6d2c1-131">Распространенным способом реализации поведения рендеринга <xref:System.Windows.UIElement.OnRender%2A> является переопределение метода и использование одного или нескольких <xref:System.Windows.Media.DrawingContext> объектов для визуализации визуальных элементов, приведенных в качестве необходимости (как показано в приведенном выше примере).</span><span class="sxs-lookup"><span data-stu-id="6d2c1-131">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in the example above).</span></span>

> [!NOTE]
> <span data-ttu-id="6d2c1-132">Все, что помещено в слой декоративного элемента, отрисовывается поверх остальных установленных стилей.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-132">Anything placed in the adorner layer is rendered on top of the rest of any styles you have set.</span></span> <span data-ttu-id="6d2c1-133">Другими словами, декоративные элементы всегда визуально находятся сверху и не могут быть переопределены с помощью упорядочения по z-координате.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-133">In other words, adorners are always visually on top and cannot be overridden using z-order.</span></span>

## <a name="events-and-hit-testing"></a><span data-ttu-id="6d2c1-134">События и проверка нажатия</span><span class="sxs-lookup"><span data-stu-id="6d2c1-134">Events and Hit Testing</span></span>

<span data-ttu-id="6d2c1-135">Adorners получают входные события, <xref:System.Windows.FrameworkElement>как и любые другие.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-135">Adorners receive input events just like any other <xref:System.Windows.FrameworkElement>.</span></span>  <span data-ttu-id="6d2c1-136">Поскольку орелит всегда имеет более высокий z-порядок, чем элемент, который <xref:System.Windows.UIElement.Drop> <xref:System.Windows.UIElement.MouseMove>он украшает, ореонер получает входные события (например, или), которые могут быть предназначены для основного элемента, украшенного.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-136">Because an adorner always has a higher z-order than the element it adorns, the adorner receives input events (such as <xref:System.Windows.UIElement.Drop> or <xref:System.Windows.UIElement.MouseMove>) that may be intended for the underlying adorned element.</span></span>  <span data-ttu-id="6d2c1-137">Декоративный элемент может отслеживать определенные события ввода и передавать их в базовый декорированный элемент, повторно запуская событие.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-137">An adorner can listen for certain input events and pass these on to the underlying adorned element by re-raising the event.</span></span>

<span data-ttu-id="6d2c1-138">Для того, чтобы сквозной хит тестирования элементов <xref:System.Windows.UIElement.IsHitTestVisible%2A> под украшением, установить хит тест собственности **на ложные** на украшение.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-138">To enable pass-through hit testing of elements under an adorner, set the hit test <xref:System.Windows.UIElement.IsHitTestVisible%2A> property to **false** on the adorner.</span></span>  <span data-ttu-id="6d2c1-139">Для получения дополнительной информации о тестировании хитов, [см.](../graphics-multimedia/hit-testing-in-the-visual-layer.md)</span><span class="sxs-lookup"><span data-stu-id="6d2c1-139">For more information about hit testing, see [Hit Testing in the Visual Layer](../graphics-multimedia/hit-testing-in-the-visual-layer.md).</span></span>

## <a name="adorning-a-single-uielement"></a><span data-ttu-id="6d2c1-140">Декорирование одного элемента пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="6d2c1-140">Adorning a Single UIElement</span></span>

<span data-ttu-id="6d2c1-141">Чтобы привязать орели <xref:System.Windows.UIElement>к конкретному, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="6d2c1-141">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>

1. <span data-ttu-id="6d2c1-142">Вызов статический <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> метод, <xref:System.Windows.Documents.AdornerLayer> чтобы <xref:System.Windows.UIElement> получить объект для украшения.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-142">Call the static method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="6d2c1-143"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>идет вверх по визуальному дереву, начиная с указанного, <xref:System.Windows.UIElement>и возвращает первый слой украшения он находит.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-143"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified <xref:System.Windows.UIElement>, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="6d2c1-144">(Если слои декоративных элементов не найдены, метод возвращает значение 0.)</span><span class="sxs-lookup"><span data-stu-id="6d2c1-144">(If no adorner layers are found, the method returns null.)</span></span>

2. <span data-ttu-id="6d2c1-145">Вызов <xref:System.Windows.Documents.AdornerLayer.Add%2A> метода, чтобы привязать <xref:System.Windows.UIElement>украшение к цели.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-145">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target <xref:System.Windows.UIElement>.</span></span>

 <span data-ttu-id="6d2c1-146">Следующий пример связывает SimpleCircleAdorner (см. <xref:System.Windows.Controls.TextBox> выше) с именем *myTextBox:*</span><span class="sxs-lookup"><span data-stu-id="6d2c1-146">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*:</span></span>

 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]

> [!NOTE]
> <span data-ttu-id="6d2c1-147">Использование [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для привязки декоративного элемента к другому элементу в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-147">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>

## <a name="adorning-the-children-of-a-panel"></a><span data-ttu-id="6d2c1-148">Декорирование дочерних объектов панели</span><span class="sxs-lookup"><span data-stu-id="6d2c1-148">Adorning the Children of a Panel</span></span>

<span data-ttu-id="6d2c1-149">Чтобы связать украшение с <xref:System.Windows.Controls.Panel>детьми, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="6d2c1-149">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>

1. <span data-ttu-id="6d2c1-150">`static` Вызовите <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> метод, чтобы найти слой украшения для элемента, дети которого должны быть украшены.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-150">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to find an adorner layer for the element whose children are to be adorned.</span></span>

2. <span data-ttu-id="6d2c1-151">Перечислите через детей родительского элемента и <xref:System.Windows.Documents.AdornerLayer.Add%2A> вызовите метод, чтобы связать оредета к каждому элементу ребенка.</span><span class="sxs-lookup"><span data-stu-id="6d2c1-151">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>

<span data-ttu-id="6d2c1-152">Следующий пример связывает SimpleCircleAdorner (см. выше) <xref:System.Windows.Controls.StackPanel> к детям имени *myStackPanel*:</span><span class="sxs-lookup"><span data-stu-id="6d2c1-152">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*:</span></span>

[!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
[!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]

## <a name="see-also"></a><span data-ttu-id="6d2c1-153">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6d2c1-153">See also</span></span>

- <xref:System.Windows.Media.AdornerHitTestResult>
- [<span data-ttu-id="6d2c1-154">Общие сведения о фигурах и базовых средствах рисования в WPF</span><span class="sxs-lookup"><span data-stu-id="6d2c1-154">Shapes and Basic Drawing in WPF Overview</span></span>](../graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="6d2c1-155">Заполнение с использованием изображений, рисунков и визуальных элементов</span><span class="sxs-lookup"><span data-stu-id="6d2c1-155">Painting with Images, Drawings, and Visuals</span></span>](../graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="6d2c1-156">Общие сведения об объектах Drawing</span><span class="sxs-lookup"><span data-stu-id="6d2c1-156">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="6d2c1-157">Как-к темам</span><span class="sxs-lookup"><span data-stu-id="6d2c1-157">How-to Topics</span></span>](adorners-how-to-topics.md)
