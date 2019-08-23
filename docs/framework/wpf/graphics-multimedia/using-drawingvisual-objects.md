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
ms.openlocfilehash: 4e6fc89b64f7b0acc1a0077708d567eb97e2868e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962834"
---
# <a name="using-drawingvisual-objects"></a>Использование объектов DrawingVisual
В этом разделе приводятся общие сведения об <xref:System.Windows.Media.DrawingVisual> использовании объектов на визуальномуровне.[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]  
  
<a name="drawingvisual_object"></a>   
## <a name="drawingvisual-object"></a>Объект DrawingVisual  
 <xref:System.Windows.Media.DrawingVisual> — упрощенный класс, используемый для отрисовки фигур, изображений и текста. Этот класс считается упрощенным, так как не предоставляет средств для работы с разметкой и обработку событий, что повышает его производительность. Поэтому этот класс идеально подходит для фоновых рисунков или клипов.  
  
<a name="drawingvisual_host_container"></a>   
## <a name="drawingvisual-host-container"></a>Контейнер размещения DrawingVisual  
 Чтобы использовать <xref:System.Windows.Media.DrawingVisual> объекты, необходимо создать контейнер узла для объектов. Объект контейнера узла должен быть производным от <xref:System.Windows.FrameworkElement> класса, который обеспечивает поддержку макета и обработки событий, который отсутствует в <xref:System.Windows.Media.DrawingVisual> классе. Объект контейнера размещения не отображает видимых свойств, так как его основное назначение — включать дочерние объекты. Однако свойство контейнера узла должно иметь <xref:System.Windows.Visibility.Visible>значение; в противном случае ни один из его дочерних элементов не будет виден. <xref:System.Windows.UIElement.Visibility%2A>  
  
 При создании объекта контейнера узла для визуальных объектов необходимо сохранить ссылки на визуальные объекты в <xref:System.Windows.Media.VisualCollection>. Используйте метод <xref:System.Windows.Media.VisualCollection.Add%2A> , чтобы добавить визуальный объект в контейнер узла. В следующем примере создается объект контейнера узла, и в него <xref:System.Windows.Media.VisualCollection>добавляются три визуальных объекта.  
  
 [!code-csharp[DrawingVisualSample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
> Полный код примера, из которого был взят предыдущий пример кода, см. в разделе [Проверка нажатия с помощью примера DrawingVisuals](https://go.microsoft.com/fwlink/?LinkID=159994).  
  
<a name="creating_drawingvisual_objects"></a>   
## <a name="creating-drawingvisual-objects"></a>Создание объектов DrawingVisual  
 При создании <xref:System.Windows.Media.DrawingVisual> объекта он не имеет содержимого. Можно добавить текст, графику или изображение, извлекая объект <xref:System.Windows.Media.DrawingContext> и рисуя его. Возвращается путем <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> вызова метода<xref:System.Windows.Media.DrawingVisual> объекта. <xref:System.Windows.Media.DrawingContext>  
  
 Чтобы нарисовать прямоугольник в <xref:System.Windows.Media.DrawingContext>, <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> используйте метод <xref:System.Windows.Media.DrawingContext> объекта. Существуют аналогичные методы для рисования других объектов. Завершив рисование содержимого в <xref:System.Windows.Media.DrawingContext>, <xref:System.Windows.Media.DrawingContext.Close%2A> вызовите метод, чтобы закрыть <xref:System.Windows.Media.DrawingContext> и сохранить содержимое.  
  
 В следующем примере <xref:System.Windows.Media.DrawingVisual> создается объект, и в него <xref:System.Windows.Media.DrawingContext>рисуется прямоугольник.  
  
 [!code-csharp[DrawingVisualSample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>   
## <a name="creating-overrides-for-frameworkelement-members"></a>Создание переопределений для членов класса FrameworkElement  
 Объект контейнера размещения отвечает за управление своей коллекцией визуальных объектов. Для этого необходимо, чтобы контейнер размещения реализовывал переопределения членов для производного <xref:System.Windows.FrameworkElement> класса.  
  
 Ниже приводятся два члена класса, которые необходимо переопределить.  
  
- <xref:System.Windows.FrameworkElement.GetVisualChild%2A>: Возвращает дочерний элемент по указанному индексу из коллекции дочерних элементов.  
  
- <xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: Получает количество визуальных дочерних элементов внутри этого элемента.  
  
 В следующем примере реализуются переопределения для двух <xref:System.Windows.FrameworkElement> элементов.  
  
 [!code-csharp[DrawingVisualSample#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>   
## <a name="providing-hit-testing-support"></a>Поддержка проверки нажатия  
 Объект контейнера узла может обеспечить обработку событий, даже если он не отображает видимые свойства, однако его <xref:System.Windows.UIElement.Visibility%2A> свойство должно иметь <xref:System.Windows.Visibility.Visible>значение. Это позволяет создать процедуру обработки событий для контейнера размещения. Эта процедура сможет перехватывать события мыши, например отпускание левой кнопки мыши. Затем подпрограммы обработки событий могут реализовать проверку попадания, вызвав <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> метод. <xref:System.Windows.Media.HitTestResultCallback> Параметр метода ссылается на определяемую пользователем процедуру, которую можно использовать для определения результирующего действия проверки попадания.  
  
 В следующем примере реализована поддержка проверки нажатия для объекта узла контейнера и его дочерних объектов.  
  
 [!code-csharp[DrawingVisualSample#103](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.DrawingVisual>
- <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>
- [Общие сведения об отрисовке графики в WPF](wpf-graphics-rendering-overview.md)
- [Проверка нажатия на визуальном уровне](hit-testing-in-the-visual-layer.md)
