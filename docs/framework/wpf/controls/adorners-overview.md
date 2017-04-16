---
title: "Общие сведения о декоративных элементах | Microsoft Docs"
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
  - "декоративные элементы [WPF], сведения о декоративных элементах"
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
caps.latest.revision: 35
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 34
---
# Общие сведения о декоративных элементах
Декораторы являются специальным типом <xref:System.Windows.FrameworkElement>, использующимся для предоставления пользователю визуальных подсказок.  Среди других применений, декораторы могут быть использованы для добавления функциональных обработчиков в элементы или для предоставления сведений о состоянии об элементе управления.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="about_Adorners"></a>   
## О Декораторах  
 <xref:System.Windows.Documents.Adorner> является пользовательским <xref:System.Windows.FrameworkElement>, который привязан к <xref:System.Windows.UIElement>.  Декораторы отображаются в <xref:System.Windows.Documents.AdornerLayer>, который является поверхностью отрисовки на самом верху графического элемента или коллекции графических элементов.  Отрисовка декоратора не зависит от отрисовки <xref:System.Windows.UIElement>, с которым связан декоратор.  Декоратор обычно располагается относительно элемента, к которому он привязан, при помощи стандартных двухмерных координат, отсчитываемых от левого верхнего угла декоративного элемента.  
  
 Обычные приложения для декораторов включают:  
  
-   Добавление функциональных обработчиков в <xref:System.Windows.UIElement>, которые позволяют пользователю в некотором роде манипулировать элементом \(изменять размеры, вращать, перемещать и т.д.\).  
  
-   Предоставление визуальной обратной связи для показа различных состояний или в ответ на различные события.  
  
-   Наложение визуальных декораторов на <xref:System.Windows.UIElement>.  
  
-   Визуально маскировать или переопределять часть или весь <xref:System.Windows.UIElement>.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет базовую оболочку для декоративных визуальных элементов.  В таблице ниже перечислены основные типы, используемые при декорировании объектов, и их назначение.  Несколько примеров использования.  
  
|||  
|-|-|  
|<xref:System.Windows.Documents.Adorner>|Абстрактный базовый класс, из которого наследуются все конкретные реализации декораторов.|  
|<xref:System.Windows.Documents.AdornerLayer>|Класс, представляющий уровень отрисовки для декораторов одного или нескольких графических элементов.|  
|<xref:System.Windows.Documents.AdornerDecorator>|Класс, который позволяет графическому уровню ассоциироваться с коллекцией элементов.|  
  
<a name="implement_custom_Adorner"></a>   
## Реализация пользовательского декоративного элемента  
 Оболочка декораторов, предоставляемая [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], предназначена главным образом для поддержки создания пользовательских декораторов.  Пользовательский декоратор создается путем реализации класса, который наследуется от абстрактного класса <xref:System.Windows.Documents.Adorner>.  
  
> [!NOTE]
>  Родителем <xref:System.Windows.Documents.Adorner> является <xref:System.Windows.Documents.AdornerLayer>, который отображает <xref:System.Windows.Documents.Adorner>, не являющийся графическим элементом.  
  
 Следующий пример показывает класс, реализующий простой декоратор.  В примере декоратор просто украшает углы <xref:System.Windows.UIElement> кругами.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
 На следующем рисунке показан SimpleCircleAdorner примененный к <xref:System.Windows.Controls.TextBox>.  
  
 ![Пример Adorners: украшенное текстовое поле](../../../../docs/framework/wpf/controls/media/adornedtextbox.png "AdornedTextBox")  
  
<a name="rendering_behavior_for_Adorners"></a>   
## Поведение отрисовки декоративных элементов  
 Важно обратить внимание, что декораторы не включают любое обязательное поведение отрисовки; гарантируется, что ответственность за отрисовку декоратора лежит на реализаторе декоратора.  Распространенным способом реализации поведения визуализации является переопределение метода <xref:System.Windows.UIElement.OnRender%2A> и использование одного или более объектов <xref:System.Windows.Media.DrawingContext> для отрисовки графических компонентов декоратора по мере необходимости \(как показано в приведенном выше примере\).  
  
> [!NOTE]
>  Все, что помещается в уровень декоратора отображается поверх любых других установленных вами стилей.  Другими словами, декораторы визуально всегда наверху и не могут быть переопределены [по оси z](GTMT).  
  
<a name="adorner_events_hittest"></a>   
## События и проверки попадания  
 Декораторы получают события ввода так же, как и любой другой <xref:System.Windows.FrameworkElement>.  Поскольку декоратор всегда выше по [оси z](GTMT), чем украшаемый им элемент, декоратор получает события ввода, такие как <xref:System.Windows.UIElement.Drop> или <xref:System.Windows.UIElement.MouseMove>, которые могут быть предназначены для лежащего ниже графического элемента.  Декоратор может ожидать определенные события ввода и передавать их на лежащий ниже графический элемент путем повторного вызова события.  
  
 Чтобы включить передачу проверки попадания элементов под декоратором, установите свойство проверки попадания <xref:System.Windows.UIElement.IsHitTestVisible%2A> в **false** на декораторе.  Дополнительные сведения о проверке попадания см. в разделе  
  
 [Проверка попадания на визуальном уровне](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md).  
  
<a name="adorn_single_element"></a>   
## Декорирование одного элемента пользовательского интерфейса  
 Для привязки графического элемента к конкретному объекту <xref:System.Windows.UIElement> выполните следующие действия:  
  
1.  Вызовите статический метод <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>, чтобы получить объект <xref:System.Windows.Documents.AdornerLayer> для оформляемого объекта <xref:System.Windows.UIElement>.  Данный метод <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> перемещается вверх по дереву Visual, начиная с заданного <xref:System.Windows.UIElement>, и возвращает первый найденный слой декоративных элементов.  \(Если уровни графических элементов не найдены, метод возвращает значение null.\)  
  
2.  Вызовите метод <xref:System.Windows.Documents.AdornerLayer.Add%2A> для привязки декоратора к нужному <xref:System.Windows.UIElement>.  
  
 В следующем примере выполняется привязка объекта SimpleCircleAdorner \(см. выше\) к объекту <xref:System.Windows.Controls.TextBox> с именем *myTextBox*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  Использование [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для привязки элемента оформления к другому элементу в текущей версии не поддерживается.  
  
<a name="adorn_children_panel"></a>   
## Декорирование дочерних объектов Panel  
 Для привязки элемента оформления к дочерним объектам <xref:System.Windows.Controls.Panel>, выполните следующие действия.  
  
1.  Вызовите `static` метод <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> для поиска графического уровня для элемента, чьи дочерние элементы надо оформить.  
  
2.  Выполните перечисление через дочерние элементы родительского элемента и вызовите метод <xref:System.Windows.Documents.AdornerLayer.Add%2A> для привязки элемента оформления к каждому дочернему элементу.  
  
 Следующий пример привязывает SimpleCircleAdorner \(показанный выше\) к дочерним элементам <xref:System.Windows.Controls.StackPanel> с именем *myStackPanel*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
## См. также  
 <xref:System.Windows.Media.AdornerHitTestResult>   
 [Обзор фигур и базовых средств рисования в приложении WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/controls/adorners-how-to-topics.md)