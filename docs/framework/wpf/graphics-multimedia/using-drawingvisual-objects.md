---
title: "Использование объектов DrawingVisual | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DrawingVisual - объект (визуальный слой)"
  - "визуальный слой, объекты DrawingVisual"
ms.assetid: 0b4e711d-e640-40cb-81c3-8f5c59909b7d
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Использование объектов DrawingVisual
Этот раздел содержит обзор использования объектов <xref:System.Windows.Media.DrawingVisual> в визуальном слое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 В этом разделе содержатся следующие подразделы.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
-   [Рисование визуального объекта](#drawing_visual_object)  
  
-   [Контейнер узла DrawingVisual](#drawingvisual_host_container)  
  
-   [Создание объектов DrawingVisual](#creating_drawingvisual_objects)  
  
-   [Создание переопределений членов FrameworkElement](#creating_overrides)  
  
-   [Предоставление поддержки проверки попадания](#providing_hit_testing_support)  
  
-   [Связанные разделы](#seeAlsoToggle)  
  
<a name="drawingvisual_object"></a>   
## Объект DrawingVisual  
 Объект <xref:System.Windows.Media.DrawingVisual> представляет собой облегченный класс рисования, который используется для отображения фигур, рисунков или текста.  Этот класс считается упрощенным, поскольку он не предоставляет макет или обработку событий, что повышает его производительность.  По этой причине эти объекты идеально подходят для фоновых рисунков и коллекций картинок.  
  
<a name="drawingvisual_host_container"></a>   
## Контейнер узла DrawingVisual  
 Чтобы использовать объекты <xref:System.Windows.Media.DrawingVisual>, необходимо создать контейнер узла для объектов.  Объект контейнера узла должен быть производным от класса <xref:System.Windows.FrameworkElement>, который предоставляет макет и обеспечивает обработку событий, не поддерживаемых классом <xref:System.Windows.Media.DrawingVisual>.  Объект контейнера узла не отображает все свойства видимости, поскольку его основной целью является содержание дочерних объектов.  Однако для свойства <xref:System.Windows.UIElement.Visibility%2A> контейнера узла должно быть установлено значение <xref:System.Windows.Visibility>; в противном случае, ни один из его дочерних элементов не будет отображен.  
  
 При создании объекта контейнера узла для визуальных объектов необходимо сохранить ссылки визуального объекта в коллекции <xref:System.Windows.Media.VisualCollection>.  Используйте метод <xref:System.Windows.Media.VisualCollection.Add%2A>, чтобы добавить визуальный объект в контейнер узла.  В следующем примере создается объект контейнер узла и три визуальных объекта, которые добавляются к его коллекции <xref:System.Windows.Media.VisualCollection>.  
  
 [!code-csharp[DrawingVisualSample#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
>  Полный пример кода, из которого был взят предыдущий пример, см. на веб\-странице [Hit Test Using DrawingVisuals Sample](http://go.microsoft.com/fwlink/?LinkID=159994).  
  
<a name="creating_drawingvisual_objects"></a>   
## Создание объектов DrawingVisual  
 При создании в объекте <xref:System.Windows.Media.DrawingVisual> отсутствует содержимое рисунка.  Можно добавить текст, рисунок или изображение, извлекая содержимое <xref:System.Windows.Media.DrawingContext> объекта и рисуя в него.  Объект <xref:System.Windows.Media.DrawingContext> возвращается путем вызова метода <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> объекта <xref:System.Windows.Media.DrawingVisual>.  
  
 Чтобы нарисовать прямоугольник в содержимое <xref:System.Windows.Media.DrawingContext>, используйте метод <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> объекта <xref:System.Windows.Media.DrawingContext>.  Похожие методы существуют для рисования других типов содержимого.  Закончив рисование в содержимое <xref:System.Windows.Media.DrawingContext>, вызовите метод <xref:System.Windows.Media.DrawingContext.Close%2A>, чтобы закрыть объект <xref:System.Windows.Media.DrawingContext> и сохранить содержимое.  
  
 В следующем примере создается объект <xref:System.Windows.Media.DrawingVisual>, и прямоугольник рисуется в его содержимое <xref:System.Windows.Media.DrawingContext>.  
  
 [!code-csharp[DrawingVisualSample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>   
## Создание переопределений членов FrameworkElement  
 Объект контейнера узла отвечает за управление его коллекцией визуальных объектов.  Для этого необходимо, чтобы контейнер узла реализовывал переопределения членов производного класса <xref:System.Windows.FrameworkElement>.  
  
 Далее перечислены два члена, которые необходимо переопределить:  
  
-   Член <xref:System.Windows.FrameworkElement.GetVisualChild%2A>: возвращает дочерний элемент по указанному индексу из коллекции дочерних элементов.  
  
-   Член <xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: получает число визуальных дочерних элементов внутри этого элемента.  
  
 В следующем примере реализуются переопределение для двух членов <xref:System.Windows.FrameworkElement>.  
  
 [!code-csharp[DrawingVisualSample#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>   
## Предоставление поддержки проверки попадания  
 Объект контейнера узла может обеспечивать обработку события, даже если оно не отображает никаких свойств видимости, однако для его свойства <xref:System.Windows.UIElement.Visibility%2A> должно быть установлено значение <xref:System.Windows.Visibility>.  Это позволяет создать процедуру обработки события для контейнера узла, которая может перехватить события мыши, например отпускание левой кнопки.  Процедура обработки события может затем реализовать проверку попадания путем вызова метода <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>.  Параметр <xref:System.Windows.Media.HitTestResultCallback> этого метода относится к процедуре, определенной пользователем, которую можно использовать для определения итогового действия проверки попадания.  
  
 В следующем примере проверка попадания реализуется для объекта контейнера узла и его дочерних элементов.  
  
 [!code-csharp[DrawingVisualSample#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## См. также  
 <xref:System.Windows.Media.DrawingVisual>   
 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>   
 [Общие сведения об отрисовке графики в WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)   
 [Проверка попадания на визуальном уровне](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)