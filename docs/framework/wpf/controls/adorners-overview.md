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
# <a name="adorners-overview"></a>Общие сведения о декоративных элементах
Декораторы — это особый тип <xref:System.Windows.FrameworkElement>, используемый для предоставления визуальных подсказок пользователю. Помимо прочего, декоративные элементы можно использовать для добавления функциональных дескрипторов к элементам или предоставления информации о состоянии элемента управления.  

<a name="about_Adorners"></a>   
## <a name="about-adorners"></a>Сведения о декоративных элементах  
 Является пользовательским <xref:System.Windows.FrameworkElement> , привязанным к. <xref:System.Windows.UIElement> <xref:System.Windows.Documents.Adorner> Декораторы подготавливаются к <xref:System.Windows.Documents.AdornerLayer>просмотру в, который представляет собой область отрисовки, которая всегда находится над декоративным элементом или коллекцией декоративных элементов. Отрисовка декоративного элемента не зависит от отрисовки <xref:System.Windows.UIElement> элемента, к которому привязан декоративный элемент. Декоративный элемент обычно располагается относительно элемента, к которому он привязан, с использованием стандартной двухмерной системы координат с началом отсчета в левом верхнем углу графического элемента.  
  
 Типичные сценарии использования декоративных элементов:  
  
- Добавление функциональных дескрипторов <xref:System.Windows.UIElement> в, позволяющих пользователю манипулировать элементом каким-либо образом (изменение размера, вращение, перемещение и т. д.).  
  
- Обеспечение визуальной обратной связи для указания различных состояний или в ответ на различные события.  
  
- Наложение визуальных украшений на <xref:System.Windows.UIElement>.  
  
- Визуальная маскировка или переопределение части или <xref:System.Windows.UIElement>всех элементов.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет базовую среду для декоративных визуальных элементов. В следующей таблице перечислены основные типы, используемые при настройке объектов, и их назначение. Ниже приведено несколько примеров использования.  
  
|||  
|-|-|  
|<xref:System.Windows.Documents.Adorner>|Абстрактный базовый класс, из которого наследуются все конкретные реализации декоративного элемента.|  
|<xref:System.Windows.Documents.AdornerLayer>|Класс, представляющий слой отрисовки декоративного элемента одного или нескольких настроенных элементов.|  
|<xref:System.Windows.Documents.AdornerDecorator>|Класс, который позволяет ассоциировать слой декоративного элемента с коллекцией элементов.|  
  
<a name="implement_custom_Adorner"></a>   
## <a name="implementing-a-custom-adorner"></a>Реализация пользовательского декоративного элемента  
 Среда декоративных элементов, предоставляемая [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], предназначена в первую очередь для поддержки создания пользовательских декоративных элементов. Пользовательский декоративный элемент создается путем реализации класса, который наследует от абстрактного <xref:System.Windows.Documents.Adorner> класса.  
  
> [!NOTE]
> Родителем объекта <xref:System.Windows.Documents.Adorner> <xref:System.Windows.Documents.AdornerLayer> является объект, который визуализирует <xref:System.Windows.Documents.Adorner>, а не элемент, декоративный.  
  
 В следующем примере показан класс, который реализует простой декоративный элемент. Пример декоративного элемента просто декоративно углы <xref:System.Windows.UIElement> с круговыми кругами.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
 На следующем рисунке показан SimpleCircleAdorner, применяемый к <xref:System.Windows.Controls.TextBox>.  
  
 ![Снимок экрана, на котором отображается декоративное текстовое поле.](./media/adorners-overview/simplecircleadorner-textbox.png)  
  
<a name="rendering_behavior_for_Adorners"></a>   
## <a name="rendering-behavior-for-adorners"></a>Поведение отрисовки для декоративных элементов  
 Важно отметить, что декоративные элементы не включают какое-либо обязательное поведение отрисовки. За результат применения декоративного элемента отвечает его автор.   Обычным способом реализации поведения при отрисовке является переопределение <xref:System.Windows.UIElement.OnRender%2A> метода и использование одного или нескольких <xref:System.Windows.Media.DrawingContext> объектов для отрисовки визуальных элементов декоративного элемента по мере необходимости (как показано в примере выше).  
  
> [!NOTE]
> Все, что помещено в слой декоративного элемента, отрисовывается поверх остальных установленных стилей. Другими словами, декоративные элементы всегда визуально находятся сверху и не могут быть переопределены с помощью упорядочения по z-координате.  
  
<a name="adorner_events_hittest"></a>   
## <a name="events-and-hit-testing"></a>События и проверка нажатия  
 Декораторы получают события ввода так же, как <xref:System.Windows.FrameworkElement>и любые другие.  Поскольку декоративный элемент всегда имеет более высокий z-порядок, чем элемент, на который он оформлен, декоративный элемент получает входные события <xref:System.Windows.UIElement.Drop> ( <xref:System.Windows.UIElement.MouseMove>например, или), которые могут быть предназначены для базового декоративного элемента.  Декоративный элемент может отслеживать определенные события ввода и передавать их в базовый декорированный элемент, повторно запуская событие.  
  
 Чтобы включить проверку попадания для элементов в декоративном элементе, задайте для свойства Проверка <xref:System.Windows.UIElement.IsHitTestVisible%2A> попадания **значение false** в декоративном элементе.  Дополнительные сведения о проверке нажатия см. в разделе  
  
 [Проверка нажатия в визуальном слое](../graphics-multimedia/hit-testing-in-the-visual-layer.md).  
  
<a name="adorn_single_element"></a>   
## <a name="adorning-a-single-uielement"></a>Декорирование одного элемента пользовательского интерфейса  
 Чтобы привязать декоративный элемент к конкретному <xref:System.Windows.UIElement>, выполните следующие действия.  
  
1. Вызовите статический метод <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> , чтобы <xref:System.Windows.Documents.AdornerLayer> получить объект для элемента <xref:System.Windows.UIElement> , который должен быть оформлен. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>переходит вверх по визуальному дереву, начиная с <xref:System.Windows.UIElement>указанного, и возвращает первый найденный слой декоративных элементов. (Если слои декоративных элементов не найдены, метод возвращает значение 0.)  
  
2. Вызовите <xref:System.Windows.UIElement>метод, чтобы привязать декоративный элемент к целевому объекту. <xref:System.Windows.Documents.AdornerLayer.Add%2A>  
  
 В следующем примере показано, как привязать SimpleCircleAdorner (показанный выше <xref:System.Windows.Controls.TextBox> ) к именованной *митекстбокс*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
> Использование [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для привязки декоративного элемента к другому элементу в настоящее время не поддерживается.  
  
<a name="adorn_children_panel"></a>   
## <a name="adorning-the-children-of-a-panel"></a>Декорирование дочерних объектов панели  
 Чтобы привязать декоративный элемент к дочерним <xref:System.Windows.Controls.Panel>элементам, выполните следующие действия.  
  
1. Вызовите <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> метод, чтобы найти слой декоративных элементов для элемента, чьи дочерние элементы должны быть декоративными. `static`  
  
2. Перечислите дочерние элементы родительского элемента и вызовите <xref:System.Windows.Documents.AdornerLayer.Add%2A> метод для привязки декоративного элемента к каждому дочернему элементу.  
  
 В следующем примере показано, как привязать SimpleCircleAdorner (показанный выше) к дочерним элементам <xref:System.Windows.Controls.StackPanel> именованного *мистаккпанел*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.AdornerHitTestResult>
- [Обзор фигур и базовых средств рисования в приложении WPF](../graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [Заполнение с использованием изображений, рисунков и визуальных элементов](../graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [Обзор объектов Drawing](../graphics-multimedia/drawing-objects-overview.md)
- [Разделы практического руководства](adorners-how-to-topics.md)
