---
title: Использование объектов DrawingVisual
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- visual layer [WPF], DrawingVisual objects
- DrawingVisual objects in visual layer [WPF]
ms.assetid: 0b4e711d-e640-40cb-81c3-8f5c59909b7d
ms.openlocfilehash: 9d67fbc0d9716c9df3935232c6c7e579b50d55bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148326"
---
# <a name="using-drawingvisual-objects"></a>Использование объектов DrawingVisual
В этой теме содержится <xref:System.Windows.Media.DrawingVisual> обзор того, как использовать объекты в визуальном [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] слое.  
  
<a name="drawingvisual_object"></a>
## <a name="drawingvisual-object"></a>Объект DrawingVisual  
 Это <xref:System.Windows.Media.DrawingVisual> легкий класс рисования, который используется для визуализации форм, изображений или текста. Этот класс считается упрощенным, так как не предоставляет средств для работы с разметкой и обработку событий, что повышает его производительность. Поэтому этот класс идеально подходит для фоновых рисунков или клипов.  
  
<a name="drawingvisual_host_container"></a>
## <a name="drawingvisual-host-container"></a>Контейнер размещения DrawingVisual  
 Для использования <xref:System.Windows.Media.DrawingVisual> объектов необходимо создать контейнер-хост для объектов. Объект контейнера-хоста <xref:System.Windows.FrameworkElement> должен вытекать из класса, который обеспечивает <xref:System.Windows.Media.DrawingVisual> поддержку обработки событий, которой не хватает классу. Объект контейнера размещения не отображает видимых свойств, так как его основное назначение — включать дочерние объекты. Тем не <xref:System.Windows.UIElement.Visibility%2A> менее, свойство контейнера-хозяина должно быть установлено на; <xref:System.Windows.Visibility.Visible> в противном случае, ни один из его элементов ребенка не будет виден.  
  
 При создании объекта контейнера-хозяина для визуальных объектов необходимо хранить <xref:System.Windows.Media.VisualCollection>ссылки на визуальные объекты в . Используйте <xref:System.Windows.Media.VisualCollection.Add%2A> метод для добавления визуального объекта в контейнер-хост. В следующем примере создается объект контейнера-хоста, и <xref:System.Windows.Media.VisualCollection>к его добавлены три визуальных объекта.  
  
 [!code-csharp[DrawingVisualSample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
> Полный код примера, из которого был взят предыдущий пример кода, см. в разделе [Проверка нажатия с помощью примера DrawingVisuals](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual).  
  
<a name="creating_drawingvisual_objects"></a>
## <a name="creating-drawingvisual-objects"></a>Создание объектов DrawingVisual  
 При создании <xref:System.Windows.Media.DrawingVisual> объекта он не имеет содержимого чертежа. Вы можете добавить текст, графику или содержимое <xref:System.Windows.Media.DrawingContext> изображения, извлекая объект и втягивая в него. A <xref:System.Windows.Media.DrawingContext> возвращается, <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> вызывая <xref:System.Windows.Media.DrawingVisual> метод объекта.  
  
 Чтобы нарисовать прямоугольник в, <xref:System.Windows.Media.DrawingContext>используйте <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> метод <xref:System.Windows.Media.DrawingContext> объекта. Существуют аналогичные методы для рисования других объектов. Когда вы закончите рисовать содержимое <xref:System.Windows.Media.DrawingContext>в, вызовите <xref:System.Windows.Media.DrawingContext.Close%2A> метод, чтобы закрыть <xref:System.Windows.Media.DrawingContext> и упорствовать содержание.  
  
 В следующем примере <xref:System.Windows.Media.DrawingVisual> создается объект, и прямоугольник <xref:System.Windows.Media.DrawingContext>втягивается в его.  
  
 [!code-csharp[DrawingVisualSample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>
## <a name="creating-overrides-for-frameworkelement-members"></a>Создание переопределений для членов класса FrameworkElement  
 Объект контейнера размещения отвечает за управление своей коллекцией визуальных объектов. Для этого необходимо, чтобы участник реализации <xref:System.Windows.FrameworkElement> контейнера-хоста перекрывался для производного класса.  
  
 Ниже приводятся два члена класса, которые необходимо переопределить.  
  
- <xref:System.Windows.FrameworkElement.GetVisualChild%2A>: Возвращает ребенка по указанному индексу из коллекции элементов ребенка.  
  
- <xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: Получает количество визуальных элементов ребенка в этом элементе.  
  
 В следующем примере выполняются <xref:System.Windows.FrameworkElement> переопределения для двух членов.  
  
 [!code-csharp[DrawingVisualSample#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>
## <a name="providing-hit-testing-support"></a>Поддержка проверки нажатия  
 Объект контейнера-хоста может обеспечить обработку событий, даже <xref:System.Windows.UIElement.Visibility%2A> если он не <xref:System.Windows.Visibility.Visible>отображает никаких видимых свойств, однако его свойство должно быть установлено на . Это позволяет создать процедуру обработки событий для контейнера размещения. Эта процедура сможет перехватывать события мыши, например отпускание левой кнопки мыши. Процедура обработки событий может затем реализовать тестирование <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> хита, ссылаясь на метод. Параметр метода <xref:System.Windows.Media.HitTestResultCallback> относится к процедуре, определяемой пользователем, которую можно использовать для определения полученного действия хит-теста.  
  
 В следующем примере реализована поддержка проверки нажатия для объекта узла контейнера и его дочерних объектов.  
  
 [!code-csharp[DrawingVisualSample#103](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.DrawingVisual>
- <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>
- [Общие сведения об отрисовке графики в WPF](wpf-graphics-rendering-overview.md)
- [Проверка попадания на визуальном уровне](hit-testing-in-the-visual-layer.md)
