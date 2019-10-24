---
title: Поведение при размещении контекстного меню
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: ca984aa724cf3f076d6073aa8b8179abfb91d26c
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "69951734"
---
# <a name="popup-placement-behavior"></a>Поведение при размещении контекстного меню
Элемент управления <xref:System.Windows.Controls.Primitives.Popup> отображает содержимое в отдельном окне, которое перемещается в приложение. Можно указать расположение <xref:System.Windows.Controls.Primitives.Popup> относительно элемента управления, мыши или экрана с помощью свойств <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>.  Эти свойства взаимодействуют, чтобы обеспечить гибкость при указании расположения <xref:System.Windows.Controls.Primitives.Popup>.  
  
> [!NOTE]
> Классы <xref:System.Windows.Controls.ToolTip> и <xref:System.Windows.Controls.ContextMenu> также определяют эти пять свойств и ведут себя аналогичным образом.  

<a name="Positioning"></a>   
## <a name="positioning-the-popup"></a>Размещение всплывающего окна  
 Размещение <xref:System.Windows.Controls.Primitives.Popup> может относиться к <xref:System.Windows.UIElement>у или ко всему экрану.  В следующем примере создаются четыре элемента управления <xref:System.Windows.Controls.Primitives.Popup>, которые относятся к <xref:System.Windows.UIElement> (в данном случае изображение). Для всех элементов управления <xref:System.Windows.Controls.Primitives.Popup> свойство <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> имеет значение `image1`, но у каждого <xref:System.Windows.Controls.Primitives.Popup> есть другое значение для свойства размещения.  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 На следующем рисунке показано изображение и элементы управления <xref:System.Windows.Controls.Primitives.Popup>  
  
 ![Изображение с четырьмя элементами управления всплывающих окон](./media/popup-placement-behavior/popup-placement-intro.png "Изображение с четырьмя всплывающими окнами")    
  
 В этом простом примере показано, как задать свойства <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> и <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, но с помощью свойств <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> вы еще больше контролируете расположение <xref:System.Windows.Controls.Primitives.Popup>.  
  
<a name="Definitions"></a>   
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>Определение терминов: анатомия всплывающего окна  
 Следующие термины полезны для понимания того, как свойства <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> связаны друг с другом и <xref:System.Windows.Controls.Primitives.Popup>.  
  
- Целевой объект  
  
- Целевая область  
  
- Исходная точка  
  
- Точка выравнивания всплывающего окна  
  
 Эти термины предоставляют удобный способ обращения к различным аспектам <xref:System.Windows.Controls.Primitives.Popup> и элементу управления, с которым он связан.  
  
### <a name="target-object"></a>Целевой объект  
 *Целевой объект* — это элемент, с которым связан <xref:System.Windows.Controls.Primitives.Popup>. Если задано свойство <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, то он указывает целевой объект.  Если параметр <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> не задан, а <xref:System.Windows.Controls.Primitives.Popup> имеет родителя, то родительским объектом является целевой объект.  Если нет <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>ного значения и родительского объекта, то целевой объект отсутствует, а <xref:System.Windows.Controls.Primitives.Popup> располагается относительно экрана.  
  
 В следующем примере создается <xref:System.Windows.Controls.Primitives.Popup>, который является дочерним для <xref:System.Windows.Controls.Canvas>.  В этом примере не задается свойство <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> в <xref:System.Windows.Controls.Primitives.Popup>. Значение по умолчанию для <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>, поэтому <xref:System.Windows.Controls.Primitives.Popup> отображается под <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 На следующем рисунке показано, что <xref:System.Windows.Controls.Primitives.Popup> располагается относительно <xref:System.Windows.Controls.Canvas>.  
  
 ![Элемент управления всплывающим окном без PlacementTarget](./media/popup-placement-behavior/popup-placement-no-placement-target.png "Всплывающее окно без PlacementTarget.")  

 В следующем примере создается <xref:System.Windows.Controls.Primitives.Popup>, который является дочерним для <xref:System.Windows.Controls.Canvas>, но на этот раз <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> устанавливается в `ellipse1`, поэтому всплывающее окно отображается под <xref:System.Windows.Shapes.Ellipse>.  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 На следующем рисунке показано, что <xref:System.Windows.Controls.Primitives.Popup> располагается относительно <xref:System.Windows.Shapes.Ellipse>.  
  
 ![Размещение всплывающего окна относительно эллипса](./media/popup-placement-behavior/popup-placement-with-placement-target.png "Всплывающее окно с PlacementTarget")    
  
> [!NOTE]
> Для <xref:System.Windows.Controls.ToolTip> значение по умолчанию <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> равно <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>.  Для <xref:System.Windows.Controls.ContextMenu> значение по умолчанию <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> равно <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>. Эти значения описаны дальше, в разделе "Совместная работа свойств".  
  
### <a name="target-area"></a>Целевая область  
 *Целевая область* — это область на экране, относительно которой <xref:System.Windows.Controls.Primitives.Popup>. В предыдущих примерах <xref:System.Windows.Controls.Primitives.Popup> соответствует границам целевого объекта, но в некоторых случаях <xref:System.Windows.Controls.Primitives.Popup> выполнит выравнивание с другими границами, даже если у <xref:System.Windows.Controls.Primitives.Popup> есть целевой объект.  Если задано свойство <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, Целевая область отличается от границ целевого объекта.  
  
 В следующем примере создаются два объекта <xref:System.Windows.Controls.Canvas>, каждый из которых содержит <xref:System.Windows.Shapes.Rectangle> и <xref:System.Windows.Controls.Primitives.Popup>.  В обоих случаях целевым объектом для <xref:System.Windows.Controls.Primitives.Popup> является <xref:System.Windows.Controls.Canvas>. @No__t_0 в первой <xref:System.Windows.Controls.Canvas> имеет набор <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, для свойств <xref:System.Windows.Rect.X%2A>, <xref:System.Windows.Rect.Y%2A>, <xref:System.Windows.Rect.Width%2A> и <xref:System.Windows.Rect.Height%2A> установлены значения 50, 50, 50 и 100 соответственно. @No__t_0 во втором <xref:System.Windows.Controls.Canvas> не имеет набора <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  В результате первая <xref:System.Windows.Controls.Primitives.Popup> располагается под <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, а вторая <xref:System.Windows.Controls.Primitives.Popup> располагается под <xref:System.Windows.Controls.Canvas>. Каждая <xref:System.Windows.Controls.Canvas> также содержит <xref:System.Windows.Shapes.Rectangle> с теми же границами, что и <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> для первого <xref:System.Windows.Controls.Primitives.Popup>.  Обратите внимание, что <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> не создает видимый элемент в приложении; в примере создается <xref:System.Windows.Shapes.Rectangle> для представления <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 На следующем рисунке показан результат примера, приведенного выше.  
  
 ![Всплывающее меню с PlacementRectangle и без него](./media/popup-placement-behavior/popup-placement-placement-rectangle.png "Всплывающее окно с PlacementRectangle и без него.")  

### <a name="target-origin-and-popup-alignment-point"></a>Исходная точка и точка выравнивания всплывающего окна  
 *Исходная точка* и *точка выравнивания всплывающего окна* являются опорными точками на целевой области и всплывающем окне соответственно, которые используются для позиционирования. Для смещения всплывающего окна от целевой области можно использовать свойства <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>.  @No__t_0 и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> являются относительными к исходному объекту и точке выравнивания всплывающего окна. Значение свойства <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> определяет место расположения целевого объекта и точки выравнивания всплывающего окна.  
  
 В следующем примере создается <xref:System.Windows.Controls.Primitives.Popup> и устанавливаются свойства <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> равными 20.  Свойству <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> присвоено значение <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> (по умолчанию), поэтому исходная точка находится в левом нижнем углу целевой области, а всплывающее окно находится в левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 На следующем рисунке показан результат примера, приведенного выше.  
  
 ![Размещение всплывающего окна с точкой выравнивания в исходной точке](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "Всплывающее окно с HorizontalOffset и VerticalOffset.")    
  
<a name="How"></a>   
## <a name="how-the-properties-work-together"></a>Совместная работа свойств  
 Значения <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> и <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> должны рассматриваться вместе для определения правильной целевой области, целевого источника и точки выравнивания всплывающего окна.  Например, если значение <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> равно <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, то отсутствует целевой объект, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> игнорируется, а Целевая область — границы указателя мыши. С другой стороны, если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родитель определяет целевой объект, а <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> определяет целевую область.  
  
 В следующей таблице описаны целевой объект, Целевая область, целевое положение и точка выравнивания всплывающего окна, а также указано, используются ли <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> и <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> для каждого значения перечисления <xref:System.Windows.Controls.Primitives.PlacementMode>.  
  
|PlacementMode|Целевой объект|Целевая область|Исходная точка|Точка выравнивания всплывающего окна|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Неприменимо. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> игнорируется.|Экран или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, если он задан.  @No__t_0 задается относительно экрана.|Левый верхний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Неприменимо. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> игнорируется.|Экран или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, если он задан.  @No__t_0 задается относительно экрана.|Левый верхний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительский элемент.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, если он задан.  @No__t_0 задается относительно целевого объекта.|Левый нижний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительский элемент.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, если он задан.  @No__t_0 задается относительно целевого объекта.|Центр целевой области.|Центр <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительский элемент.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, если он задан.  @No__t_0 задается относительно целевого объекта.|Определяется <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|Определяется <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительский элемент.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, если он задан.  @No__t_0 задается относительно целевого объекта.|Левый верхний угол целевой области.|Правый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Неприменимо. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> игнорируется.|Границы указателя мыши. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> игнорируется.|Левый нижний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Неприменимо. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> игнорируется.|Границы указателя мыши. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> игнорируется.|Левый верхний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительский элемент.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, если он задан.  @No__t_0 задается относительно целевого объекта.|Левый верхний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительский элемент.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, если он задан.  @No__t_0 задается относительно целевого объекта.|Левый верхний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительский элемент.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, если он задан.  @No__t_0 задается относительно целевого объекта.|Правый верхний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительский элемент.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, если он задан.  @No__t_0 задается относительно целевого объекта.|Левый верхний угол целевой области.|Левый нижний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
  
 На следующих иллюстрациях показаны <xref:System.Windows.Controls.Primitives.Popup>, Целевая область, Целевая точка и точки выравнивания всплывающего окна для каждого значения <xref:System.Windows.Controls.Primitives.PlacementMode>. На каждом рисунке Целевая область является желтой, а <xref:System.Windows.Controls.Primitives.Popup> — синим.  
  
 ![Всплывающее окно с абсолютным размещением или размещением с помощью AbsolutePoint](./media/popup-placement-behavior/popup-placement-absolute.png "Размещение является абсолютным или Абсолутепоинт.")    
  
 ![Всплывающее окно с размещением внизу](./media/popup-placement-behavior/popup-placement-bottom.png "Размещение снизу.")   
  
 ![Всплывающее окно с размещением по центру](./media/popup-placement-behavior/popup-placement-center.png "Размещение по центру.")    
  
 ![Всплывающее окно с размещением слева](./media/popup-placement-behavior/popup-placement-left.png "Размещение по левому краю.")   
  
 ![Всплывающее окно с размещением относительно мыши](./media/popup-placement-behavior/popup-placement-mouse.png "Размещение — мышь.")  
  
 ![Всплывающее окно с размещением с помощью MousePoint](./media/popup-placement-behavior/popup-placement-mousepoint.png "Размещение — Маусепоинт.")  
  
 ![Всплывающее окно с относительным размещением или размещением с помощью RelativePoint](./media/popup-placement-behavior/popup-placement-relative.png "Размещение является относительным или Релативепоинт.")    
  
 ![Всплывающее окно с размещением справа](./media/popup-placement-behavior/popup-placement-right.png "Размещение — right.")    
  
 ![Всплывающее окно с размещением сверху](./media/popup-placement-behavior/popup-placement-top.png "Размещение — Top.")    
  
<a name="When"></a>   
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Когда всплывающее окно достигает края экрана  
 По соображениям безопасности <xref:System.Windows.Controls.Primitives.Popup> не может быть скрыта границей экрана. Одно из следующих трех действий происходит, когда <xref:System.Windows.Controls.Primitives.Popup> встречает ребро экрана:  
  
- Всплывающее окно автоматически выстраивается вдоль границы экрана, которая будет скрывать <xref:System.Windows.Controls.Primitives.Popup>.  
  
- Всплывающее окно использует другую точку выравнивания.  
  
- Всплывающее окно использует другую исходную точку и точку выравнивания.  
  
 Эти параметры будут описаны далее в данном разделе.  
  
 Поведение <xref:System.Windows.Controls.Primitives.Popup> при возникновении края экрана зависит от значения свойства <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> и от того, на каком крае экрана встречается всплывающее окно. В следующей таблице приводится сводка поведения, когда <xref:System.Windows.Controls.Primitives.Popup> встречает границы экрана для каждого значения <xref:System.Windows.Controls.Primitives.PlacementMode>.  
  
|PlacementMode|Верхний край|Нижний край|Левый край|Правый край|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Выравнивание по верхнему краю.|Точка выравнивания всплывающего окна меняется на левый нижний угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Точка выравнивания всплывающего окна меняется на правый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Выравнивание по верхнему краю.|Исходная точка изменяется в левый верхний угол целевой области, а пункт выравнивания всплывающего окна меняется на левый нижний угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Исходная точка изменится в верхний правый угол целевой области, а пункт выравнивания всплывающего окна изменится на левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Выравнивание по верхнему краю.|Исходная точка изменяется в левый верхний угол целевой области (границы указателя мыши), а пункт выравнивания всплывающего окна меняется на левый нижний угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Выравнивание по верхнему краю.|Точка выравнивания всплывающего окна меняется на левый нижний угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Точка выравнивания всплывающего окна переходит в верхний правый угол всплывающего окна.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|Выравнивание по верхнему краю.|Точка выравнивания всплывающего окна меняется на левый нижний угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Точка выравнивания всплывающего окна переходит в верхний правый угол всплывающего окна.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Исходная точка изменяется в левый верхний угол целевой области, а пункт выравнивания всплывающего окна меняется на правый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|Исходная точка изменяется в нижний левый угол целевой области, а пункт выравнивания всплывающего окна меняется на левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>. Фактически, это то же самое, что и при <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
  
### <a name="aligning-to-the-screen-edge"></a>Выравнивание по краю экрана  
 @No__t_0 может выделяться по границе экрана путем изменения его расположения, чтобы вся <xref:System.Windows.Controls.Primitives.Popup> видна на экране.  В этом случае расстояние между исходным источником и точкой выравнивания всплывающего окна может отличаться от значений <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>. Если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> имеет <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>, <xref:System.Windows.Controls.Primitives.PlacementMode.Center> или <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>, <xref:System.Windows.Controls.Primitives.Popup> выстраивается на все границы экрана.  Например, предположим, что для <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> задано значение <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>, а <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> — значение 100.  Если нижний край экрана скрывает все или часть <xref:System.Windows.Controls.Primitives.Popup>, <xref:System.Windows.Controls.Primitives.Popup> перемещается вдоль нижнего края экрана, а вертикальное расстояние между исходным источником и точкой выравнивания всплывающего окна меньше 100. Эта ситуация представлена на рисунке ниже.  
  
 ![Всплывающее окно, выравниваемое по краю экрана](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "Всплывающее окно соответствует границе экрана.")    
  
### <a name="changing-the-popup-alignment-point"></a>Изменение точки выравнивания всплывающего окна  
 Если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> имеет <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>, <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint> или <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>, точка выравнивания всплывающего окна изменяется, когда всплывающее окно встречает нижний или правый край экрана.  
  
 На следующем рисунке показано, что когда нижний край экрана скрывает все или часть <xref:System.Windows.Controls.Primitives.Popup>, точка выравнивания всплывающего окна находится в левом нижнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно нижнего края экрана](./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "Всплывающее окно встречает нижний край экрана и изменяет точку выравнивания всплывающего окна.")  

 На следующем рисунке показано, что если <xref:System.Windows.Controls.Primitives.Popup> скрыта на правом крае экрана, точка выравнивания всплывающего окна находится в правом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания всплывающего окна относительно края экрана](./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "Всплывающее окно встречает правую границу экрана и изменяет точку выравнивания всплывающего окна.")    
  
 Если <xref:System.Windows.Controls.Primitives.Popup> встречает нижний и правый края экрана, точка выравнивания всплывающего окна находится в правом нижнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>Изменение положения исходной точки и точки выравнивания всплывающего окна  
 Если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> имеет <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.PlacementMode.Left>, <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, <xref:System.Windows.Controls.Primitives.PlacementMode.Right> или <xref:System.Windows.Controls.Primitives.PlacementMode.Top>, исходная точка и положение всплывающего окна изменяются при обнаружении определенного края экрана.  Граница экрана, которая вызывает изменение расположения, зависит от значения <xref:System.Windows.Controls.Primitives.PlacementMode>.  
  
 На следующем рисунке показано, что если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> имеет <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> и <xref:System.Windows.Controls.Primitives.Popup> встречает нижний край экрана, то целевой точкой является левый верхний угол целевой области, а точка выравнивания всплывающего окна находится в левом нижнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно нижнего края экрана](./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "Размещение снизу, а всплывающее окно встречает нижнюю границу экрана.")    
  
 На следующем рисунке показано, что если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> имеет <xref:System.Windows.Controls.Primitives.PlacementMode.Left> и <xref:System.Windows.Controls.Primitives.Popup> встречает левое ребро экрана, то целевой точкой является правый верхний угол целевой области, а точка выравнивания всплывающего окна — левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно левого края экрана](./media/popup-placement-behavior/popup-placement-left-screen-edge.png "Размещение по левому краю, а всплывающее окно встречает левую границу экрана.")  
  
 На следующем рисунке показано, что если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> имеет <xref:System.Windows.Controls.Primitives.PlacementMode.Right> и <xref:System.Windows.Controls.Primitives.Popup> встречает правое ребро экрана, исходная точка является верхним левым углом целевой области, а точкой выравнивания всплывающего окна является правый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно правого края экрана](./media/popup-placement-behavior/popup-placement-right-screen-edge.png "Размещение производится правильно, и всплывающее окно встречает правый конец экрана.")  

 На следующем рисунке показано, что если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> имеет <xref:System.Windows.Controls.Primitives.PlacementMode.Top> и <xref:System.Windows.Controls.Primitives.Popup> встречает верхний край экрана, исходная точка находится в левом нижнем углу целевой области, а точкой выравнивания всплывающего окна является левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно верхнего края экрана](./media/popup-placement-behavior/popup-placement-top-screen-edge.png "Размещение сверху, и всплывающее окно встречает верхний край экрана.")  
  
 На следующем рисунке показано, что если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> имеет <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> и <xref:System.Windows.Controls.Primitives.Popup> встречает нижний край экрана, исходная точка является верхним левым углом целевой области (границами указателя мыши) и точкой выравнивания всплывающего окна слева направо. угол <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![новая точка выравнивания относительно положения мыши возле края экрана](./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "Размещение — это мышь, а всплывающее окно встречает нижнюю границу экрана.")    
  
### <a name="customizing-popup-placement"></a>Настройка размещения контекстного меню  
 Можно настроить исходную и конечную точки выравнивания, задав для свойства <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> значение <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>. Затем определите <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> делегат, который возвращает набор возможных точек размещения и основных осей (в порядке предпочтения) для <xref:System.Windows.Controls.Primitives.Popup>. Выбирается точка, показывающая самую большую часть <xref:System.Windows.Controls.Primitives.Popup>.  Расположение <xref:System.Windows.Controls.Primitives.Popup> автоматически корректируется, если <xref:System.Windows.Controls.Primitives.Popup> скрыта границей экрана. См. пример в разделе [Указание пользовательского расположения контекстного меню](how-to-specify-a-custom-popup-position.md).  
  
## <a name="see-also"></a>См. также

- [Пример размещения всплывающего окна](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)
