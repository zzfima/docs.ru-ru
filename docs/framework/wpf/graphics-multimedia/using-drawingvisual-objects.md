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
ms.openlocfilehash: e76ac22d4b8205576c8ed9ab67482c143a52fbd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565318"
---
# <a name="using-drawingvisual-objects"></a>Использование объектов DrawingVisual
Этот раздел содержит общие сведения о том, как использовать <xref:System.Windows.Media.DrawingVisual> объекты в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] визуального уровня.  
  
<a name="drawingvisual_object"></a>   
## <a name="drawingvisual-object"></a>Объект DrawingVisual  
 <xref:System.Windows.Media.DrawingVisual> Является упрощенным класс рисования, который используется для отрисовки фигур, изображений или текста. Этот класс считается упрощенным, так как не предоставляет средств для работы с разметкой и обработку событий, что повышает его производительность. Поэтому этот класс идеально подходит для фоновых рисунков или клипов.  
  
<a name="drawingvisual_host_container"></a>   
## <a name="drawingvisual-host-container"></a>Контейнер размещения DrawingVisual  
 Чтобы использовать <xref:System.Windows.Media.DrawingVisual> объектов, необходимо создать контейнер узла для объектов. Объект контейнера узла должен быть производным от <xref:System.Windows.FrameworkElement> класс, предоставляющий макет и обработка событий поддерживает, <xref:System.Windows.Media.DrawingVisual> класса отсутствует. Объект контейнера размещения не отображает видимых свойств, так как его основное назначение — включать дочерние объекты. Тем не менее <xref:System.Windows.UIElement.Visibility%2A> свойство контейнера узла должно быть присвоено <xref:System.Windows.Visibility.Visible>; в противном случае будет отображаться ни один из его дочерних элементов.  
  
 При создании объекта контейнера узла для визуальных объектов, вам необходимо сохранить ссылки визуального объекта в <xref:System.Windows.Media.VisualCollection>. Используйте <xref:System.Windows.Media.VisualCollection.Add%2A> метод, чтобы добавить визуальный объект в контейнер узла. В следующем примере создается объект контейнер узла и три визуальных объектов добавляются его <xref:System.Windows.Media.VisualCollection>.  
  
 [!code-csharp[DrawingVisualSample#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
>  Полный код примера, из которого был взят предыдущий пример кода, см. в разделе [Проверка нажатия с помощью примера DrawingVisuals](http://go.microsoft.com/fwlink/?LinkID=159994).  
  
<a name="creating_drawingvisual_objects"></a>   
## <a name="creating-drawingvisual-objects"></a>Создание объектов DrawingVisual  
 При создании <xref:System.Windows.Media.DrawingVisual> объекта, он не имеет графического содержимого. Можно добавить текст, графики или изображения содержимого путем получения объекта <xref:System.Windows.Media.DrawingContext> и рисуя в него. Объект <xref:System.Windows.Media.DrawingContext> возвращается путем вызова <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> метод <xref:System.Windows.Media.DrawingVisual> объекта.  
  
 Чтобы нарисовать прямоугольник в <xref:System.Windows.Media.DrawingContext>, используйте <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> метод <xref:System.Windows.Media.DrawingContext> объекта. Существуют аналогичные методы для рисования других объектов. После завершения отображения содержимого в <xref:System.Windows.Media.DrawingContext>, вызовите <xref:System.Windows.Media.DrawingContext.Close%2A> метод закрытия <xref:System.Windows.Media.DrawingContext> и сохранить содержимое.  
  
 В следующем примере <xref:System.Windows.Media.DrawingVisual> объект создается, а прямоугольник в его <xref:System.Windows.Media.DrawingContext>.  
  
 [!code-csharp[DrawingVisualSample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>   
## <a name="creating-overrides-for-frameworkelement-members"></a>Создание переопределений для членов класса FrameworkElement  
 Объект контейнера размещения отвечает за управление своей коллекцией визуальных объектов. Это требует, что контейнер узла реализовывал переопределения члена производного <xref:System.Windows.FrameworkElement> класса.  
  
 Ниже приводятся два члена класса, которые необходимо переопределить.  
  
-   <xref:System.Windows.FrameworkElement.GetVisualChild%2A>: Возвращает дочерний элемент по указанному индексу из коллекции дочерних элементов.  
  
-   <xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: Получает количество визуальных дочерних элементов внутри этого элемента.  
  
 В следующем примере переопределяется для двух <xref:System.Windows.FrameworkElement> члены реализуются.  
  
 [!code-csharp[DrawingVisualSample#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>   
## <a name="providing-hit-testing-support"></a>Поддержка проверки нажатия  
 Объект контейнера узла может предоставить обработка событий, даже если он не отображает все свойства видимости, однако его <xref:System.Windows.UIElement.Visibility%2A> свойству необходимо присвоить значение <xref:System.Windows.Visibility.Visible>. Это позволяет создать процедуру обработки событий для контейнера размещения. Эта процедура сможет перехватывать события мыши, например отпускание левой кнопки мыши. Процедура обработки события можно реализовать проверку попадания путем вызова <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> метод. Метод <xref:System.Windows.Media.HitTestResultCallback> параметр ссылается на определяемой пользователем процедуры, можно использовать для определения результирующего действия для проверки нажатия.  
  
 В следующем примере реализована поддержка проверки нажатия для объекта узла контейнера и его дочерних объектов.  
  
 [!code-csharp[DrawingVisualSample#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.DrawingVisual>  
 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>  
 [Общие сведения об отрисовке графики в WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [Проверка нажатия на визуальном уровне](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)
