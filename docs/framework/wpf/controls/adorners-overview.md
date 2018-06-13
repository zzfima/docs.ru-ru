---
title: Общие сведения о декоративных элементах
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
ms.openlocfilehash: 6dd38b9e24b42de8945c0e9729f8f30cf901fc3a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557125"
---
# <a name="adorners-overview"></a>Общие сведения о декоративных элементах
Графические элементы — это специальный тип <xref:System.Windows.FrameworkElement>, использующимся для предоставления пользователю визуальные подсказки. Помимо прочего, декоративные элементы можно использовать для добавления функциональных дескрипторов к элементам или предоставления информации о состоянии элемента управления.  
  
  
  
<a name="about_Adorners"></a>   
## <a name="about-adorners"></a>Сведения о декоративных элементах  
 <xref:System.Windows.Documents.Adorner> Является пользовательским <xref:System.Windows.FrameworkElement> , привязанный к <xref:System.Windows.UIElement>. Графические элементы отображаются в <xref:System.Windows.Documents.AdornerLayer>, который является поверхностью отрисовки на самом верху графического элемента или коллекции графических элементов. Отрисовка графического элемента не зависит от отрисовки <xref:System.Windows.UIElement> , к которому привязан графический элемент. Декоративный элемент обычно располагается относительно элемента, к которому он привязан, с использованием стандартной двухмерной системы координат с началом отсчета в левом верхнем углу графического элемента.  
  
 Типичные сценарии использования декоративных элементов:  
  
-   Добавление функциональных обработчиков <xref:System.Windows.UIElement> , дать пользователю возможность манипулировать элементом иным образом (изменять размеры, вращать, перемещать, и т. д.).  
  
-   Обеспечение визуальной обратной связи для указания различных состояний или в ответ на различные события.  
  
-   Наложение визуальных декораторов на <xref:System.Windows.UIElement>.  
  
-   Визуально маскировать или переопределять частично или полностью <xref:System.Windows.UIElement>.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет базовую среду для декоративных визуальных элементов. В следующей таблице перечислены основные типы, используемые при настройке объектов, и их назначение. Ниже приведено несколько примеров использования.  
  
|||  
|-|-|  
|<xref:System.Windows.Documents.Adorner>|Абстрактный базовый класс, из которого наследуются все конкретные реализации декоративного элемента.|  
|<xref:System.Windows.Documents.AdornerLayer>|Класс, представляющий слой отрисовки декоративного элемента одного или нескольких настроенных элементов.|  
|<xref:System.Windows.Documents.AdornerDecorator>|Класс, который позволяет ассоциировать слой декоративного элемента с коллекцией элементов.|  
  
<a name="implement_custom_Adorner"></a>   
## <a name="implementing-a-custom-adorner"></a>Реализация пользовательского декоративного элемента  
 Среда декоративных элементов, предоставляемая [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], предназначена в первую очередь для поддержки создания пользовательских декоративных элементов. Пользовательский графический элемент создается путем реализации класса, который наследует от абстрактного <xref:System.Windows.Documents.Adorner> класса.  
  
> [!NOTE]
>  Родительский <xref:System.Windows.Documents.Adorner> — <xref:System.Windows.Documents.AdornerLayer> , выводящий <xref:System.Windows.Documents.Adorner>, не являющийся графическим элементом.  
  
 В следующем примере показан класс, который реализует простой декоративный элемент. В примере декоративный элемент просто украшает углы <xref:System.Windows.UIElement> окружностями.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
 На следующем рисунке показана SimpleCircleAdorner, применить к <xref:System.Windows.Controls.TextBox>.  
  
 ![Пример декоративных элементов — настроенное текстовое поле](../../../../docs/framework/wpf/controls/media/adornedtextbox.png "AdornedTextBox")  
  
<a name="rendering_behavior_for_Adorners"></a>   
## <a name="rendering-behavior-for-adorners"></a>Поведение отрисовки для декоративных элементов  
 Важно отметить, что декоративные элементы не включают какое-либо обязательное поведение отрисовки. За результат применения декоративного элемента отвечает его автор.   Распространенным способом реализации поведения визуализации является переопределение <xref:System.Windows.UIElement.OnRender%2A> метод и использование одного или нескольких <xref:System.Windows.Media.DrawingContext> объектов для подготовки к просмотру декоратора по мере необходимости (как показано в примере выше).  
  
> [!NOTE]
>  Все, что помещено в слой декоративного элемента, отрисовывается поверх остальных установленных стилей. Другими словами, декоративные элементы всегда визуально находятся сверху и не могут быть переопределены с помощью упорядочения по z-координате.  
  
<a name="adorner_events_hittest"></a>   
## <a name="events-and-hit-testing"></a>События и проверка нажатия  
 Декораторы получают события ввода так же, как и любой другой <xref:System.Windows.FrameworkElement>.  Так как графический элемент всегда имеет более высоким z порядком чем элемент, используемая для его оформления, декоративный элемент принимает входные события (такие как <xref:System.Windows.UIElement.Drop> или <xref:System.Windows.UIElement.MouseMove>), может быть предназначено для базового оформить элемент.  Декоративный элемент может отслеживать определенные события ввода и передавать их в базовый декорированный элемент, повторно запуская событие.  
  
 Чтобы включить передачу проверки попадания элементов под графический элемент, задайте нажатия <xref:System.Windows.UIElement.IsHitTestVisible%2A> свойства **false** декоративного элемента.  Дополнительные сведения о проверке нажатия см. в разделе  
  
 [Проверка нажатия в визуальном слое](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md).  
  
<a name="adorn_single_element"></a>   
## <a name="adorning-a-single-uielement"></a>Декорирование одного элемента пользовательского интерфейса  
 Для привязки к конкретному графический элемент <xref:System.Windows.UIElement>, выполните следующие действия:  
  
1.  Вызовите статический метод <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> для получения <xref:System.Windows.Documents.AdornerLayer> для объекта <xref:System.Windows.UIElement> оформляемого. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> перемещается вверх по дереву visual, начиная с указанного <xref:System.Windows.UIElement>и возвращает первый слой графических элементов, которые найдет. (Если слои декоративных элементов не найдены, метод возвращает значение 0.)  
  
2.  Вызовите <xref:System.Windows.Documents.AdornerLayer.Add%2A> метода для привязки к целевому декоратора <xref:System.Windows.UIElement>.  
  
 Следующий пример привязывает (показано выше) для SimpleCircleAdorner <xref:System.Windows.Controls.TextBox> с именем *myTextBox*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  Использование [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для привязки декоративного элемента к другому элементу в настоящее время не поддерживается.  
  
<a name="adorn_children_panel"></a>   
## <a name="adorning-the-children-of-a-panel"></a>Декорирование дочерних объектов панели  
 Для привязки элемента оформления к дочерним элементам <xref:System.Windows.Controls.Panel>, выполните следующие действия:  
  
1.  Вызовите `static` метод <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> найти слой графических элементов, дочерние элементы которого являются оформляемого элемента.  
  
2.  Перечисление дочерних элементов родительского элемента и вызовите <xref:System.Windows.Documents.AdornerLayer.Add%2A> метода для привязки элемента оформления к каждому дочернему элементу.  
  
 Следующий пример привязывает (показано выше) к дочерним элементам SimpleCircleAdorner <xref:System.Windows.Controls.StackPanel> с именем *myStackPanel*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.AdornerHitTestResult>  
 [Обзор фигур и базовых средств рисования в приложении WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [Заполнение с использованием изображений, рисунков и визуальных элементов](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/adorners-how-to-topics.md)
