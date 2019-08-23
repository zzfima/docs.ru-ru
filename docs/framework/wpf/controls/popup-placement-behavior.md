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
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951734"
---
# <a name="popup-placement-behavior"></a>Поведение при размещении контекстного меню
<xref:System.Windows.Controls.Primitives.Popup> Элемент управления отображает содержимое в отдельном окне, которое перемещается в приложение. Можно <xref:System.Windows.Controls.Primitives.Popup> указать расположение относительно элемента управления, мыши или экрана с <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>помощью свойств <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>,, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> .  Эти свойства взаимодействуют, чтобы обеспечить гибкость при указании расположения <xref:System.Windows.Controls.Primitives.Popup>.  
  
> [!NOTE]
> Классы <xref:System.Windows.Controls.ToolTip> и<xref:System.Windows.Controls.ContextMenu> также определяют эти пять свойств и ведут себя аналогичным образом.  

<a name="Positioning"></a>   
## <a name="positioning-the-popup"></a>Размещение всплывающего окна  
 Размещение <xref:System.Windows.Controls.Primitives.Popup> может быть относительным <xref:System.Windows.UIElement> по отношению к или ко всему экрану.  В следующем примере создаются четыре <xref:System.Windows.Controls.Primitives.Popup> элемента управления, которые являются относительными <xref:System.Windows.UIElement>к, в данном случае изображение. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup> Для всех элементов управления свойству присвоено значение, но каждому свойству размещения присваивается разность. <xref:System.Windows.Controls.Primitives.Popup> `image1`  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 На следующем рисунке показано изображение и <xref:System.Windows.Controls.Primitives.Popup> элементы управления  
  
 ![Изображение с четырьмя всплывающими элементами управления](./media/popup-placement-behavior/popup-placement-intro.png "Изображение с четырьмя всплывающими окнами")    
  
 В этом простом <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> примере показано <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, как задать <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойства и, но с помощью свойств <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, <xref:System.Windows.Controls.Primitives.Popup> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> вы еще больше контролируете место расположения.  
  
<a name="Definitions"></a>   
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>Определения терминов: Анатомия всплывающего окна  
 Следующие термины полезны для <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>понимания того, как свойства <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>,, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> связаны друг с другом и <xref:System.Windows.Controls.Primitives.Popup>:  
  
- Целевой объект  
  
- Целевая область  
  
- Исходная точка  
  
- Точка выравнивания всплывающего окна  
  
 Эти термины предоставляют удобный способ обращения к различным аспектам <xref:System.Windows.Controls.Primitives.Popup> и элементу управления, с которым он связан.  
  
### <a name="target-object"></a>Целевой объект  
 *Целевой объект* является элементом, с которым <xref:System.Windows.Controls.Primitives.Popup> связан элемент. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> Если свойство задано, то он указывает целевой объект.  Если <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> параметр не установлен <xref:System.Windows.Controls.Primitives.Popup> и имеет родителя, родительским объектом является целевой объект.  Если нет <xref:System.Windows.Controls.Primitives.Popup> значения и родителя, то целевой объект отсутствует, а элемент располагается относительно экрана. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>  
  
 В следующем примере создается объект <xref:System.Windows.Controls.Primitives.Popup> , который является дочерним <xref:System.Windows.Controls.Canvas>для.  В примере не задается <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> свойство <xref:System.Windows.Controls.Primitives.Popup>для. Значение по умолчанию <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> для <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>равно, <xref:System.Windows.Controls.Canvas>поэтому <xref:System.Windows.Controls.Primitives.Popup> отображается под.  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 На следующем рисунке показано, что <xref:System.Windows.Controls.Primitives.Popup> объект расположен относительно. <xref:System.Windows.Controls.Canvas>  
  
 ![Элемент управления Popup без PlacementTarget](./media/popup-placement-behavior/popup-placement-no-placement-target.png "Всплывающее окно без PlacementTarget.")  

 В следующем примере создается объект <xref:System.Windows.Controls.Primitives.Popup> , который является дочерним <xref:System.Windows.Controls.Canvas>для <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> , но на этот раз <xref:System.Windows.Shapes.Ellipse>для `ellipse1`задано значение, поэтому всплывающее окно отображается под.  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 На следующем рисунке показано, что <xref:System.Windows.Controls.Primitives.Popup> объект расположен относительно. <xref:System.Windows.Shapes.Ellipse>  
  
 ![Всплывающее окно, расположенное относительно эллипса](./media/popup-placement-behavior/popup-placement-with-placement-target.png "Всплывающее окно с PlacementTarget")    
  
> [!NOTE]
> Для <xref:System.Windows.Controls.ToolTip> значениепоумолчанию<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>—. <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>  Для <xref:System.Windows.Controls.ContextMenu> значениепоумолчанию<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>—. <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Эти значения описаны дальше, в разделе "Совместная работа свойств".  
  
### <a name="target-area"></a>Целевая область  
 *Целевая область* — это область на экране, <xref:System.Windows.Controls.Primitives.Popup> относительно которой отсчитывается. В предыдущих примерах <xref:System.Windows.Controls.Primitives.Popup> объект выполнит выравнивание по границам целевого объекта, но в некоторых случаях <xref:System.Windows.Controls.Primitives.Popup> объект выполнит выравнивание по другим границам, даже если <xref:System.Windows.Controls.Primitives.Popup> у объекта есть целевой объект.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Если свойство задано, Целевая область отличается от границ целевого объекта.  
  
 В следующем примере создаются два <xref:System.Windows.Controls.Canvas> объекта, каждый из <xref:System.Windows.Shapes.Rectangle> которых содержит и <xref:System.Windows.Controls.Primitives.Popup>.  В обоих случаях целевым объектом для <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Canvas>является. <xref:System.Windows.Rect.X%2A> <xref:System.Windows.Rect.Y%2A>В первом <xref:System.Windows.Controls.Canvas> содержит <xref:System.Windows.Rect.Width%2A>набор, свойства,, и<xref:System.Windows.Rect.Height%2A> , для которых заданы значения 50, 50, 50 и 100 соответственно. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> <xref:System.Windows.Controls.Primitives.Popup> Объект <xref:System.Windows.Controls.Primitives.Popup> во втором <xref:System.Windows.Controls.Canvas> не имеет <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> набора.  В результате первая <xref:System.Windows.Controls.Primitives.Popup> размещается <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> под, а вторая <xref:System.Windows.Controls.Primitives.Popup> располагается под <xref:System.Windows.Controls.Canvas>. Каждая <xref:System.Windows.Controls.Canvas> из них также <xref:System.Windows.Shapes.Rectangle> содержит объект с <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> теми же границами, что и для <xref:System.Windows.Controls.Primitives.Popup>первого.  Обратите внимание <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , что объект не создает видимый элемент в приложении; в примере создается <xref:System.Windows.Shapes.Rectangle> объект для представления <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 На следующем рисунке показан результат примера, приведенного выше.  
  
 ![Всплывающее окно с PlacementRectangle и без] него (./media/popup-placement-behavior/popup-placement-placement-rectangle.png "Всплывающее окно с PlacementRectangle и без него.")  

### <a name="target-origin-and-popup-alignment-point"></a>Исходная точка и точка выравнивания всплывающего окна  
 *Исходная точка* и *точка выравнивания всплывающего окна* являются опорными точками на целевой области и всплывающем окне соответственно, которые используются для позиционирования. Для смещения всплывающего <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> окна <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> от целевой области можно использовать свойства и.  <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> И<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> являются относительными к исходному объекту и точке выравнивания всплывающего окна. Значение <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойства определяет место расположения целевого объекта и точки выравнивания всплывающего окна.  
  
 В следующем примере создается <xref:System.Windows.Controls.Primitives.Popup> свойство и <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> присваивается значение <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 20 для свойств и.  Для <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.Popup>свойства задано значение (по умолчанию), поэтому исходная точка находится в левом нижнем углу целевой области, а точкой выравнивания всплывающего окна является левый верхний угол. <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 На следующем рисунке показан результат примера, приведенного выше.  
  
 ![Размещение всплывающего окна с точкой выравнивания исходного объекта](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "Всплывающее окно с HorizontalOffset и VerticalOffset.")    
  
<a name="How"></a>   
## <a name="how-the-properties-work-together"></a>Совместная работа свойств  
 Значения <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>и должнырассматриватьсявместедляопределенияправильнойцелевойобласти,целевогоисточникаиточкивыравниваниявсплывающегоокна.<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>  Например, если значение <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> равно <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, то целевой объект отсутствует, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> не учитывается, а Целевая область является границами указателя мыши. С другой стороны, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> если имеет <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>значение, то <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> родительский объект <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> или определяет целевую область.  
  
 В следующей таблице описаны целевой объект, Целевая область, целевое положение и точка выравнивания всплывающего окна <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> , <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> а также указывается, <xref:System.Windows.Controls.Primitives.PlacementMode> используются ли для каждого значения перечисления.  
  
|PlacementMode|Целевой объект|Целевая область|Исходная точка|Точка выравнивания всплывающего окна|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Не применяется <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>игнорируется.|Экран или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , если он задан.  Объект <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> отсчитывается относительно экрана.|Левый верхний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Не применяется <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>игнорируется.|Экран или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , если он задан.  Объект <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> отсчитывается относительно экрана.|Левый верхний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>или родительский элемент.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , если он задан.  Объект <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> является относительным для целевого объекта.|Левый нижний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>или родительский элемент.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , если он задан.  Объект <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> является относительным для целевого объекта.|Центр целевой области.|Центр <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>или родительский элемент.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , если он задан.  Объект <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> является относительным для целевого объекта.|<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>Определяется.|<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>Определяется.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>или родительский элемент.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , если он задан.  Объект <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> является относительным для целевого объекта.|Левый верхний угол целевой области.|Правый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Не применяется <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>игнорируется.|Границы указателя мыши. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>игнорируется.|Левый нижний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Не применяется <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>игнорируется.|Границы указателя мыши. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>игнорируется.|Левый верхний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>или родительский элемент.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , если он задан.  Объект <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> является относительным для целевого объекта.|Левый верхний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>или родительский элемент.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , если он задан.  Объект <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> является относительным для целевого объекта.|Левый верхний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>или родительский элемент.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , если он задан.  Объект <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> является относительным для целевого объекта.|Правый верхний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>или родительский элемент.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , если он задан.  Объект <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> является относительным для целевого объекта.|Левый верхний угол целевой области.|Нижний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|  
  
 На следующих иллюстрациях показана <xref:System.Windows.Controls.Primitives.Popup>, Целевая область, Целевая точка и точки выравнивания всплывающего окна для каждого <xref:System.Windows.Controls.Primitives.PlacementMode> значения. На каждом рисунке Целевая область является желтой, а <xref:System.Windows.Controls.Primitives.Popup> — синим.  
  
 ![Всплывающее окно с абсолютным или абсолутепоинт размещением](./media/popup-placement-behavior/popup-placement-absolute.png "Размещение является абсолютным или абсолутепоинт.")    
  
 ![Всплывающее окно с нижним размещением](./media/popup-placement-behavior/popup-placement-bottom.png "Размещение снизу.")   
  
 ![Всплывающее окно с размещением по центру](./media/popup-placement-behavior/popup-placement-center.png "Размещение по центру.")    
  
 ![Всплывающее окно с размещением слева](./media/popup-placement-behavior/popup-placement-left.png "Размещение по левому краю.")   
  
 ![Всплывающее окно с размещением мыши](./media/popup-placement-behavior/popup-placement-mouse.png "Размещение — мышь.")  
  
 ![Всплывающее окно с маусепоинт размещением](./media/popup-placement-behavior/popup-placement-mousepoint.png "Размещение — маусепоинт.")  
  
 ![Всплывающее окно с относительным или релативепоинт размещением](./media/popup-placement-behavior/popup-placement-relative.png "Размещение является относительным или релативепоинт.")    
  
 ![Всплывающее окно с правильным размещением](./media/popup-placement-behavior/popup-placement-right.png "Размещение — right.")    
  
 ![Всплывающее окно с верхним размещением](./media/popup-placement-behavior/popup-placement-top.png "Размещение — Top.")    
  
<a name="When"></a>   
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Когда всплывающее окно достигает края экрана  
 По соображениям безопасности объект <xref:System.Windows.Controls.Primitives.Popup> не может быть скрыт границей экрана. Одно из следующих трех действий происходит при <xref:System.Windows.Controls.Primitives.Popup> обнаружении края экрана:  
  
- Всплывающее окно автоматически выстраивается вдоль границы экрана, которая будет скрывать <xref:System.Windows.Controls.Primitives.Popup>.  
  
- Всплывающее окно использует другую точку выравнивания.  
  
- Всплывающее окно использует другую исходную точку и точку выравнивания.  
  
 Эти параметры будут описаны далее в данном разделе.  
  
 Поведение, <xref:System.Windows.Controls.Primitives.Popup> возникающее при возникновении края экрана, зависит от значения <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойства и того, на каком крае экрана встречается всплывающее окно. В следующей таблице приводится сводка поведения при <xref:System.Windows.Controls.Primitives.Popup> обнаружении границы экрана для каждого <xref:System.Windows.Controls.Primitives.PlacementMode> значения.  
  
|PlacementMode|Верхний край|Нижний край|Левый край|Правый край|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Выравнивание по верхнему краю.|Точка выравнивания всплывающего окна меняется на левый нижний угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Точка выравнивания всплывающего окна меняется на правый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Выравнивание по верхнему краю.|Исходная точка изменяется в левый верхний угол целевой области, а точки выравнивания всплывающего окна меняются на левый нижний угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Исходная точка изменится на верхний правый угол целевой области, а пункт выравнивания всплывающего окна изменится на левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Выравнивание по верхнему краю.|Исходная точка изменяется в левый верхний угол целевой области (границы указателя мыши), а пункт выравнивания всплывающего окна меняется на левый нижний угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Выравнивание по верхнему краю.|Точка выравнивания всплывающего окна меняется на левый нижний угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Точка выравнивания всплывающего окна переходит в верхний правый угол всплывающего окна.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|Выравнивание по верхнему краю.|Точка выравнивания всплывающего окна меняется на левый нижний угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Точка выравнивания всплывающего окна переходит в верхний правый угол всплывающего окна.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Исходная точка изменится на левый верхний угол целевой области, а пункт выравнивания всплывающего окна изменится на правый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|Исходная точка изменяется в нижний левый угол целевой области, а пункт выравнивания всплывающего окна меняется на левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>. Фактически это то же самое, что и при <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> использовании <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
  
### <a name="aligning-to-the-screen-edge"></a>Выравнивание по краю экрана  
 Объект <xref:System.Windows.Controls.Primitives.Popup> может выделяться по границе экрана путем изменения его расположения, чтобы весь <xref:System.Windows.Controls.Primitives.Popup> экран отображался на экране.  В этом случае расстояние между исходным источником и точкой выравнивания всплывающего окна может отличаться от значений <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> и. <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> Если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> имеет <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>значение ,<xref:System.Windows.Controls.Primitives.PlacementMode.Center> или<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>, то<xref:System.Windows.Controls.Primitives.Popup> выровняйте себя по всем границам экрана.  Например <xref:System.Windows.Controls.Primitives.Popup> , предположим, что <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> для свойства задано <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> значение <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> и задано значение 100.  Если нижний край экрана скрывает все или часть <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Primitives.Popup> , перемещается вдоль нижнего края экрана, а вертикальное расстояние между исходным источником и точкой выравнивания всплывающего окна меньше 100. Эта ситуация представлена на рисунке ниже.  
  
 ![Всплывающее окно, выровняйте до края экрана](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "Всплывающее окно соответствует границе экрана.")    
  
### <a name="changing-the-popup-alignment-point"></a>Изменение точки выравнивания всплывающего окна  
 Если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> имеет <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>значение ,<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint> или<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>, точка выравнивания всплывающего окна изменяется, когда всплывающее окно встречает нижний или правый край экрана.  
  
 На следующем рисунке показано, что когда нижний край экрана скрывает все или часть <xref:System.Windows.Controls.Primitives.Popup>, точка выравнивания всплывающего окна находится в левом нижнем углу. <xref:System.Windows.Controls.Primitives.Popup>  
  
 ![Новая точка выравнивания из-за нижнего края экрана](./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "Всплывающее окно встречает нижний край экрана и изменяет точку выравнивания всплывающего окна.")  

 На следующем рисунке показано, что когда <xref:System.Windows.Controls.Primitives.Popup> элемент скрыт с помощью края экрана, точка выравнивания всплывающего окна находится в правом верхнем углу. <xref:System.Windows.Controls.Primitives.Popup>  
  
 ![Новая точка выравнивания всплывающего окна из-за края экрана](./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "Всплывающее окно встречает правую границу экрана и изменяет точку выравнивания всплывающего окна.")    
  
 Если объект <xref:System.Windows.Controls.Primitives.Popup> встречает границы нижнего и правого края экрана, точка выравнивания всплывающего окна находится в нижнем правом углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>Изменение положения исходной точки и точки выравнивания всплывающего окна  
 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> <xref:System.Windows.Controls.Primitives.PlacementMode.Left> Есливзадано<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>значение ,<xref:System.Windows.Controls.Primitives.PlacementMode.Right>, ,<xref:System.Windows.Controls.Primitives.PlacementMode.Top>или, исходная точка выравнивания при обнаружении определенного края экрана изменяется. <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>  Граница экрана, которая вызывает изменение расположения, зависит <xref:System.Windows.Controls.Primitives.PlacementMode> от значения.  
  
 На следующем рисунке показано, что <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> если <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> параметр имеет <xref:System.Windows.Controls.Primitives.Popup> значение и встречает нижний край экрана, целевой объект — левый верхний угол целевой области, а точка выравнивания всплывающего окна — нижний левый угол элемента <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания из-за нижнего края экрана](./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "Размещение снизу, а всплывающее окно встречает нижнюю границу экрана.")    
  
 На следующем рисунке показано, что <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> если <xref:System.Windows.Controls.Primitives.PlacementMode.Left> параметр имеет <xref:System.Windows.Controls.Primitives.Popup> значение и встречает левый край экрана, целевой объект является верхним правым углом целевой области, а точка выравнивания всплывающего окна находится в левом верхнем углу элемента <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания из-за левого края экрана](./media/popup-placement-behavior/popup-placement-left-screen-edge.png "Размещение по левому краю, а всплывающее окно встречает левую границу экрана.")  
  
 На следующем рисунке показано, что <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> если <xref:System.Windows.Controls.Primitives.PlacementMode.Right> параметр имеет <xref:System.Windows.Controls.Primitives.Popup> значение и встречает правый край экрана, целевой объект — левый верхний угол целевой области, а точка выравнивания всплывающего окна — правый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания из-за правого края экрана](./media/popup-placement-behavior/popup-placement-right-screen-edge.png "Размещение производится правильно, и всплывающее окно встречает правый конец экрана.")  

 На следующем рисунке показано, что <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> если <xref:System.Windows.Controls.Primitives.PlacementMode.Top> параметр имеет <xref:System.Windows.Controls.Primitives.Popup> значение и встречает верхний край экрана, целевой объект является левым нижним углом целевой области, а точка выравнивания всплывающего окна находится в левом верхнем углу элемента <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания из-за верхнего края экрана](./media/popup-placement-behavior/popup-placement-top-screen-edge.png "Размещение сверху, и всплывающее окно встречает верхний край экрана.")  
  
 На следующем рисунке показано, что <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> если <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> параметр имеет <xref:System.Windows.Controls.Primitives.Popup> значение и встречает нижний край экрана, то исходная точка является верхним левым углом целевой области (границами указателя мыши) и выравниванием всплывающего окна. точка находится в левом нижнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания из-за границ мыши вблизи экрана](./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "Размещение — это мышь, а всплывающее окно встречает нижнюю границу экрана.")    
  
### <a name="customizing-popup-placement"></a>Настройка размещения контекстного меню  
 Вы можете настроить исходную и конечную точки выравнивания, задав <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> для <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>свойства значение. Затем определите <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> делегат, возвращающий набор возможных точек размещения и основных осей (в порядке предпочтения) <xref:System.Windows.Controls.Primitives.Popup>для. Выбрана точка, в которой отображается самая крупная часть <xref:System.Windows.Controls.Primitives.Popup> .  Расположение элемента <xref:System.Windows.Controls.Primitives.Popup> автоматически корректируется, <xref:System.Windows.Controls.Primitives.Popup> если скрывается по границе экрана. См. пример в разделе [Указание пользовательского расположения контекстного меню](how-to-specify-a-custom-popup-position.md).  
  
## <a name="see-also"></a>См. также

- [Пример размещения всплывающего окна](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)
