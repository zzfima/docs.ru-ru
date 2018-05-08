---
title: Поведение при размещении контекстного меню
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: 3aef3d7863bc02aa4164b1fc9ef4464fbe799cb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="popup-placement-behavior"></a>Поведение при размещении контекстного меню
Объект <xref:System.Windows.Controls.Primitives.Popup> элемент управления отображает содержимое в отдельном окне, расположенном поверх приложения. Можно указать положение <xref:System.Windows.Controls.Primitives.Popup> относительно элемента управления, мыши или экрана с помощью <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> свойства.  Эти свойства совместно обеспечивают гибкость при указании положение <xref:System.Windows.Controls.Primitives.Popup>.  
  
> [!NOTE]
>  <xref:System.Windows.Controls.ToolTip> И <xref:System.Windows.Controls.ContextMenu> классы также определяются эти пять свойств и ведут себя аналогичным образом.  
  

  
<a name="Positioning"></a>   
## <a name="positioning-the-popup"></a>Размещение всплывающего окна  
 Размещение <xref:System.Windows.Controls.Primitives.Popup> может быть относительно <xref:System.Windows.UIElement> или на весь экран.  В следующем примере создаются четыре <xref:System.Windows.Controls.Primitives.Popup> элементов управления, относящихся к <xref:System.Windows.UIElement>— в данном случае изображения. Все <xref:System.Windows.Controls.Primitives.Popup> элементы управления имеют <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> свойство `image1`, но каждый <xref:System.Windows.Controls.Primitives.Popup> имеет другое значение свойства размещения.  
  
 [!code-xaml[PopupPositionSnippet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 На следующем рисунке показано изображение и <xref:System.Windows.Controls.Primitives.Popup> элементов управления  
  
 ![Изображение с четырьмя элементами управления всплывающих окон](../../../../docs/framework/wpf/controls/media/popupplacementintro.png "PopupPlacementIntro")  
Изображение с четырьмя всплывающими окнами  
  
 Этот простой пример демонстрирует, как задать <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> и <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойства, но с помощью <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> свойства, у вас есть еще большего контроля над where <xref:System.Windows.Controls.Primitives.Popup> располагается.  
  
<a name="Definitions"></a>   
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>Определение терминов: анатомия всплывающего окна  
 Следующие термины относятся полезен для понимания как <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> свойства связаны друг с другом и <xref:System.Windows.Controls.Primitives.Popup>:  
  
-   Целевой объект  
  
-   Целевая область  
  
-   Исходная точка  
  
-   Точка выравнивания всплывающего окна  
  
 Эти термины предоставляют удобный способ для ссылки на различные аспекты <xref:System.Windows.Controls.Primitives.Popup> и элемент управления, связанного с ним.  
  
### <a name="target-object"></a>Целевой объект  
 *Целевой объект* является элементом, <xref:System.Windows.Controls.Primitives.Popup> сопоставлен. Если <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> свойство задано, оно указывает целевой объект.  Если <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> не задано и <xref:System.Windows.Controls.Primitives.Popup> есть родительский элемент, родительский является целевым объектом.  При наличии не <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> значение и родитель, отсутствует целевой объект и <xref:System.Windows.Controls.Primitives.Popup> располагается относительно экрана.  
  
 В следующем примере создается <xref:System.Windows.Controls.Primitives.Popup> который является дочерним <xref:System.Windows.Controls.Canvas>.  В примере задается <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> свойство <xref:System.Windows.Controls.Primitives.Popup>. Значение по умолчанию для <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>, поэтому <xref:System.Windows.Controls.Primitives.Popup> отображается под <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[PopupPositionSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 На следующем рисунке показано, что <xref:System.Windows.Controls.Primitives.Popup> расположено относительно <xref:System.Windows.Controls.Canvas>.  
  
 ![Всплывающий элемент управления без PlacementTarget](../../../../docs/framework/wpf/controls/media/popupplacementnoplacementtarget.PNG "PopupPlacementNoPlacementTarget")  
Всплывающее окно без PlacementTarget  
  
 В следующем примере создается <xref:System.Windows.Controls.Primitives.Popup> который является дочерним <xref:System.Windows.Controls.Canvas>, но на этот раз <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> равно `ellipse1`, поэтому появится всплывающее окно ниже <xref:System.Windows.Shapes.Ellipse>.  
  
 [!code-xaml[PopupPositionSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 На следующем рисунке показано, что <xref:System.Windows.Controls.Primitives.Popup> расположено относительно <xref:System.Windows.Shapes.Ellipse>.  
  
 ![Размещение всплывающего окна относительно эллипса](../../../../docs/framework/wpf/controls/media/popupplacementwithplacementtarget.PNG "PopupPlacementWithPlacementTarget")  
Всплывающее окно с PlacementTarget  
  
> [!NOTE]
>  Для <xref:System.Windows.Controls.ToolTip>, значение по умолчанию <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>.  Для <xref:System.Windows.Controls.ContextMenu>, значение по умолчанию <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>. Эти значения описаны дальше, в разделе "Совместная работа свойств".  
  
### <a name="target-area"></a>Целевая область  
 *Целевой области* — это область на экране, <xref:System.Windows.Controls.Primitives.Popup> относительно. В предыдущих примерах <xref:System.Windows.Controls.Primitives.Popup> выравнивается с границами целевого объекта, но в некоторых случаях <xref:System.Windows.Controls.Primitives.Popup> выравнивается по другим границам, даже если <xref:System.Windows.Controls.Primitives.Popup> имеет целевой объект.  Если <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> имеет значение, целевая область отличается от границ целевого объекта.  
  
 В следующем примере создается два <xref:System.Windows.Controls.Canvas> объектов, каждый из которых содержит <xref:System.Windows.Shapes.Rectangle> и <xref:System.Windows.Controls.Primitives.Popup>.  В обоих случаях целевым объектом для <xref:System.Windows.Controls.Primitives.Popup> — <xref:System.Windows.Controls.Canvas>. <xref:System.Windows.Controls.Primitives.Popup> В первом <xref:System.Windows.Controls.Canvas> имеет <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> задано, с его <xref:System.Windows.Rect.X%2A>, <xref:System.Windows.Rect.Y%2A>, <xref:System.Windows.Rect.Width%2A>, и <xref:System.Windows.Rect.Height%2A> свойства, значение 50, 50, 50 и 100, соответственно. <xref:System.Windows.Controls.Primitives.Popup> Во втором <xref:System.Windows.Controls.Canvas> не имеет <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> значение.  В результате первый <xref:System.Windows.Controls.Primitives.Popup> находится ниже <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , а второй — <xref:System.Windows.Controls.Primitives.Popup> находится ниже <xref:System.Windows.Controls.Canvas>. Каждый <xref:System.Windows.Controls.Canvas> также содержит <xref:System.Windows.Shapes.Rectangle> , имеет те же границы как <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> для первого <xref:System.Windows.Controls.Primitives.Popup>.  Обратите внимание, что <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> не создает видимого элемента в приложении; в примере создается <xref:System.Windows.Shapes.Rectangle> для представления <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  
  
 [!code-xaml[PopupPositionSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 На следующем рисунке показан результат примера, приведенного выше.  
  
 ![Всплывающее окно с PlacementRectangle и без](../../../../docs/framework/wpf/controls/media/popupplacementplacementrectangle.PNG "PopupPlacementPlacementRectangle")  
Всплывающее меню с PlacementRectangle и без него  
  
### <a name="target-origin-and-popup-alignment-point"></a>Исходная точка и точка выравнивания всплывающего окна  
 *Исходная точка* и *точка выравнивания всплывающего окна* являются опорными точками на целевой области и всплывающем окне соответственно, которые используются для позиционирования. Можно использовать <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> свойства смещения контекстного меню из целевой области.  <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> И <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> относительно координат и точка выравнивания всплывающего окна. Значение <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойство определяет расположение целевого источника и всплывающие точке выравнивания.  
  
 В следующем примере создается <xref:System.Windows.Controls.Primitives.Popup> и задает <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> свойства до 20 символов.  <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Свойству <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> (по умолчанию), поэтому исходная точка является левому нижнему углу области назначения и точка выравнивания находится в левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 [!code-xaml[PopupPositionSnippet#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 На следующем рисунке показан результат примера, приведенного выше.  
  
 ![Размещение всплывающего окна в точке выравнивания начала цели](../../../../docs/framework/wpf/controls/media/popupplacementtargetoriginalignmentpoint.PNG "PopupPlacementTargetOriginAlignmentPoint")  
Всплывающее окно с HorizontalOffset и VerticalOffset  
  
<a name="How"></a>   
## <a name="how-the-properties-work-together"></a>Совместная работа свойств  
 Значения <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, и <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> должны рассматриваться вместе для выяснения правильной целевой области, начало координат и точка выравнивания всплывающего окна.  Например если значение <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, отсутствует целевой объект <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> игнорируется, и целевая область является границы указателя мыши. С другой стороны Если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родитель определяет целевой объект и <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> определяет целевую область.  
  
 В следующей таблице описываются целевой объект, целевая область, исходная точка и точка выравнивания и указывает, является ли <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> и <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> используются для каждого <xref:System.Windows.Controls.Primitives.PlacementMode> значение перечисления.  
  
|PlacementMode|Целевой объект|Целевая область|Исходная точка|Точка выравнивания всплывающего окна|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Неприменимо. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> учитывается.|Экран или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> если оно задано.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Относительно экрана.|Левый верхний угол целевой области.|В левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Неприменимо. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> учитывается.|Экран или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> если оно задано.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Относительно экрана.|Левый верхний угол целевой области.|В левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родитель.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> если оно задано.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Относительно целевого объекта.|Левый нижний угол целевой области.|В левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родитель.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> если оно задано.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Относительно целевого объекта.|Центр целевой области.|Центр <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родитель.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> если оно задано.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Относительно целевого объекта.|Определяется <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|Определяется <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родитель.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> если оно задано.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Относительно целевого объекта.|Левый верхний угол целевой области.|В правом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Неприменимо. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> учитывается.|Границы указателя мыши. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> учитывается.|Левый нижний угол целевой области.|В левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Неприменимо. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> учитывается.|Границы указателя мыши. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> учитывается.|Левый верхний угол целевой области.|В левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родитель.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> если оно задано.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Относительно целевого объекта.|Левый верхний угол целевой области.|В левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родитель.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> если оно задано.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Относительно целевого объекта.|Левый верхний угол целевой области.|В левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родитель.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> если оно задано.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Относительно целевого объекта.|Правый верхний угол целевой области.|В левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родитель.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> если оно задано.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Относительно целевого объекта.|Левый верхний угол целевой области.|В нижнем левом углу <xref:System.Windows.Controls.Primitives.Popup>.|  
  
 На следующих рисунках <xref:System.Windows.Controls.Primitives.Popup>, целевая область, исходная точка и выравнивания контекстного меню выберите команду для каждого <xref:System.Windows.Controls.Primitives.PlacementMode> значение. В каждой фигуре целевая область является желтый, а <xref:System.Windows.Controls.Primitives.Popup> — синим.  
  
 ![Всплывающее окно с абсолютным или AbsolutePoint размещением](../../../../docs/framework/wpf/controls/media/popupplacementabsolute.png "PopupPlacementAbsolute")  
Абсолютное размещение или размещение с помощью AbsolutePoint  
  
 ![Всплывающее окно с нижним размещением](../../../../docs/framework/wpf/controls/media/popupplacementbottom.png "PopupPlacementBottom")  
Расположение снизу  
  
 ![Всплывающее окно с центральным размещением](../../../../docs/framework/wpf/controls/media/popupplacementcenter.png "PopupPlacementCenter")  
Размещение в центре  
  
 ![Всплывающее окно с левым размещением](../../../../docs/framework/wpf/controls/media/popupplacementleft.png "PopupPlacementLeft")  
Размещение слева  
  
 ![Всплывающее окно с размещением относительны мыши](../../../../docs/framework/wpf/controls/media/popupplacementmouse.png "PopupPlacementMouse")  
Размещение относительно мыши  
  
 ![Всплывающее окно с размещением MousePoint](../../../../docs/framework/wpf/controls/media/popupplacementmousepoint.png "PopupPlacementMousePoint")  
Размещение относительно MousePoint  
  
 ![Всплывающее окно с относительным или RelativePoint размещением](../../../../docs/framework/wpf/controls/media/popupplacementrelative.png "PopupPlacementRelative")  
Относительное размещение или размещение с помощью RelativePoint  
  
 ![Всплывающее окно с правым размещением](../../../../docs/framework/wpf/controls/media/popupplacementright.png "PopupPlacementRight")  
Размещение справа  
  
 ![Всплывающее окно с верхним размещением](../../../../docs/framework/wpf/controls/media/popupplacementtop.png "PopupPlacementTop")  
Размещение сверху  
  
<a name="When"></a>   
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Когда всплывающее окно достигает края экрана  
 По соображениям безопасности <xref:System.Windows.Controls.Primitives.Popup> не могут быть скрыты за край экрана. Одно из следующих трех действий происходит при <xref:System.Windows.Controls.Primitives.Popup> край экрана:  
  
-   Контекстное меню располагается вдоль края экрана, который мог бы скрыть <xref:System.Windows.Controls.Primitives.Popup>.  
  
-   Всплывающее окно использует другую точку выравнивания.  
  
-   Всплывающее окно использует другую исходную точку и точку выравнивания.  
  
 Эти параметры будут описаны далее в данном разделе.  
  
 Поведение <xref:System.Windows.Controls.Primitives.Popup> при обнаружении края экрана зависит от значения <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойство и который краев, контекстное меню встречает экрана. В следующей таблице представлены поведения при <xref:System.Windows.Controls.Primitives.Popup> края экрана для каждого <xref:System.Windows.Controls.Primitives.PlacementMode> значение.  
  
|PlacementMode|Верхний край|Нижний край|Левый край|Правый край|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Выравнивание по верхнему краю.|Точка выравнивания всплывающего окна меняется на нижний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Точка выравнивания всплывающего окна изменяется в правом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Выравнивание по верхнему краю.|Исходная точка изменяется в левом верхнем углу области назначения, а точка выравнивания всплывающего окна изменяется на нижний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Исходная точка изменяется в правом верхнем углу области назначения, а точка выравнивания всплывающего окна изменяется в верхний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Выравнивание по верхнему краю.|Исходная точка изменяется в левом верхнем углу области назначения (границы указателя мыши), а точка выравнивания всплывающего окна изменяется на нижний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Выравнивание по верхнему краю.|Точка выравнивания всплывающего окна меняется на нижний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Точка выравнивания всплывающего окна переходит в верхний правый угол всплывающего окна.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|Выравнивание по верхнему краю.|Точка выравнивания всплывающего окна меняется на нижний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Точка выравнивания всплывающего окна переходит в верхний правый угол всплывающего окна.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Исходная точка изменяется в левом верхнем углу области назначения, а точка выравнивания всплывающего окна изменяется в правом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|Исходная точка изменяется на нижний левый угол области назначения и точка выравнивания всплывающего окна изменяется в левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>. По сути, это то же самое, как при <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
  
### <a name="aligning-to-the-screen-edge"></a>Выравнивание по краю экрана  
 Объект <xref:System.Windows.Controls.Primitives.Popup> можно выровнять по краю экрана путем изменения расположения таким образом всего <xref:System.Windows.Controls.Primitives.Popup> отображается на экране.  В этом случае расстояние между точка выравнивания относительно целевого источника и контекстное меню могут отличаться от значений <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>. Когда <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>, <xref:System.Windows.Controls.Primitives.PlacementMode.Center>, или <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>, <xref:System.Windows.Controls.Primitives.Popup> выравнивается по каждому краю экрана.  Например, предположим, что <xref:System.Windows.Controls.Primitives.Popup> имеет <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> значение <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> равным 100.  Если нижний край экрана скрывает все или часть <xref:System.Windows.Controls.Primitives.Popup>, <xref:System.Windows.Controls.Primitives.Popup> самостоятельно перемещается вдоль нижнего края экрана и расстояние по вертикали между исходной и контекстное меню точки выравнивания — меньше 100. Эта ситуация представлена на рисунке ниже.  
  
 ![Всплывающее окно, выравниваемое по краю экрана](../../../../docs/framework/wpf/controls/media/popupplacementrelativescreenedge.png "PopupPlacementRelativeScreenEdge")  
Всплывающее окно выравнивается по краю экрана.  
  
### <a name="changing-the-popup-alignment-point"></a>Изменение точки выравнивания всплывающего окна  
 Если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>, <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>, или <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>, точка выравнивания всплывающего окна изменяется, если контекстное меню встречает нижнего или правого края экрана.  
  
 На следующем рисунке показано, когда нижнего края экрана скрывает все или часть <xref:System.Windows.Controls.Primitives.Popup>, точка выравнивания находится в левом нижнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно нижнего края экрана](../../../../docs/framework/wpf/controls/media/popupplacementrelativepointscreenedge.png "PopupPlacementRelativePointScreenEdge")  
Всплывающее окно достигает нижнего края экрана и меняет положение точки выравнивания.  
  
 На следующем рисунке показано, что при <xref:System.Windows.Controls.Primitives.Popup> скрыто, правый край экрана, точка выравнивания находится в правом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно всплывающее окно края экрана](../../../../docs/framework/wpf/controls/media/popupplacementrelativepointrightscreenedge.png "PopupPlacementRelativePointRightScreenEdge")  
Всплывающее окно достигает правого края экрана и меняет положение точки выравнивания.  
  
 Если <xref:System.Windows.Controls.Primitives.Popup> обнаруживает нижний и правый край экрана, точка выравнивания находится в нижнем правом углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>Изменение положения исходной точки и точки выравнивания всплывающего окна  
 Когда <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.PlacementMode.Left>, <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, <xref:System.Windows.Controls.Primitives.PlacementMode.Right>, или <xref:System.Windows.Controls.Primitives.PlacementMode.Top>, выравнивание целевого источника и контекстное меню точки изменений при обнаружении определенных краев экрана.  Зависит от края экрана, который вызывает изменение положения <xref:System.Windows.Controls.Primitives.PlacementMode> значение.  
  
 На следующем рисунке показано, что при <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> и <xref:System.Windows.Controls.Primitives.Popup> встречает нижний край экрана, исходная точка находится в левом верхнем углу области назначения, а точка выравнивания находится в левом нижнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно нижнего края экрана](../../../../docs/framework/wpf/controls/media/popupplacementbottomscreenedge.png "PopupPlacementBottomScreenEdge")  
Размещение по нижнему краю и всплывающее окно достигают нижнего края экрана  
  
 На следующем рисунке показано, что при <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode.Left> и <xref:System.Windows.Controls.Primitives.Popup> встречает левый край экрана, исходная точка находится в правом верхнем углу области назначения, а точка выравнивания находится в левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно левого края экрана](../../../../docs/framework/wpf/controls/media/popupplacementleftscreenedge.png "PopupPlacementLeftScreenEdge")  
Размещение по левому краю и всплывающее окно достигают левого края экрана.  
  
 На следующем рисунке показано, что при <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode.Right> и <xref:System.Windows.Controls.Primitives.Popup> встречает правый край экрана, исходная точка находится в левом верхнем углу области назначения, а точка выравнивания находится в правом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно правого края экрана](../../../../docs/framework/wpf/controls/media/popupplacementrightscreenedge.png "PopupPlacementRightScreenEdge")  
Размещение по правому краю и всплывающее окно достигают правого края экрана.  
  
 На следующем рисунке показано, что при <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode.Top> и <xref:System.Windows.Controls.Primitives.Popup> встречает верхний край экрана, исходная точка расположена в нижнем левом углу области назначения, а точка выравнивания находится в левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно верхнего края экрана](../../../../docs/framework/wpf/controls/media/popupplacementtopscreenedge.png "PopupPlacementTopScreenEdge")  
Размещение по верхнему краю и всплывающее окно достигают верхнего края экрана.  
  
 На следующем рисунке показано, что при <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> и <xref:System.Windows.Controls.Primitives.Popup> встречает нижний край экрана, исходная точка находится в левом верхнем углу области назначения (границы указателя мыши) и выравнивания всплывающего окна точка находится в нижнем левом углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно мыши возле края экрана](../../../../docs/framework/wpf/controls/media/popupplacementmousescreenedge.png "PopupPlacementMouseScreenEdge")  
Размещение относительно мыши и всплывающее окно достигают нижнего края экрана.  
  
### <a name="customizing-popup-placement"></a>Настройка размещения контекстного меню  
 Точка выравнивания относительно целевого источника и всплывающее окно можно настроить с помощью <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойства <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>. Затем определите <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> делегат, который возвращает набор возможных точек размещения и основные оси (в порядке предпочтения) для <xref:System.Windows.Controls.Primitives.Popup>. Точка, показывающая наибольшую часть <xref:System.Windows.Controls.Primitives.Popup> выбран.  Положение <xref:System.Windows.Controls.Primitives.Popup> автоматически настраивается, если <xref:System.Windows.Controls.Primitives.Popup> по краю экрана скрыто. См. пример в разделе [Указание пользовательского расположения контекстного меню](../../../../docs/framework/wpf/controls/how-to-specify-a-custom-popup-position.md).  
  
## <a name="see-also"></a>См. также  
 [Пример размещения всплывающего окна](http://go.microsoft.com/fwlink/?LinkID=160032)
