---
title: Поведение при размещении контекстного меню
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: 063b309ebaf0944787ce40725eed250e59f09dff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176764"
---
# <a name="popup-placement-behavior"></a>Поведение при размещении контекстного меню
Элемент <xref:System.Windows.Controls.Primitives.Popup> управления отображает содержимое в отдельном окне, которое плавает над приложением. Вы можете указать <xref:System.Windows.Controls.Primitives.Popup> положение относительного элемента управления, мыши или <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>экрана <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>с <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> помощью , , и свойства.  Эти свойства работают вместе, чтобы дать вам <xref:System.Windows.Controls.Primitives.Popup>гибкость в определении позиции .  
  
> [!NOTE]
> <xref:System.Windows.Controls.ToolTip> Классы <xref:System.Windows.Controls.ContextMenu> также определяют эти пять свойств и ведут себя аналогичным образом.  

<a name="Positioning"></a>
## <a name="positioning-the-popup"></a>Размещение всплывающего окна  
 Размещение <xref:System.Windows.Controls.Primitives.Popup> может быть относительно <xref:System.Windows.UIElement> или всего экрана.  Следующий пример <xref:System.Windows.Controls.Primitives.Popup> создает четыре элемента <xref:System.Windows.UIElement>управления, которые по отношению к изображению. Все <xref:System.Windows.Controls.Primitives.Popup> элементы управления <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> имеют `image1`свойство, <xref:System.Windows.Controls.Primitives.Popup> установленное, но каждый из них имеет различное значение для размещения имущества.  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 На следующем рисунке показано <xref:System.Windows.Controls.Primitives.Popup> изображение и элементы управления  
  
 ![Изображение с четырьмя элементами управления всплывающих окон](./media/popup-placement-behavior/popup-placement-intro.png "Изображение с четырьмя всплывающими окном")
  
 Этот простой пример показывает, <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> как установить и <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>свойства, <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> но с помощью , <xref:System.Windows.Controls.Primitives.Popup> и свойства, у вас есть еще больший контроль над тем, где находится.  
  
<a name="Definitions"></a>
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>Определение терминов: анатомия всплывающего окна  
 Следующие термины полезны в <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>понимании <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> <xref:System.Windows.Controls.Primitives.Popup>того, как , , и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> свойства относятся друг к другу и:  
  
- Целевой объект  
  
- Целевая область  
  
- Исходная точка  
  
- Точка выравнивания всплывающего окна  
  
 Эти термины обеспечивают удобный способ для <xref:System.Windows.Controls.Primitives.Popup> обозначения различных аспектов и управления, с которым он связан.  
  
### <a name="target-object"></a>Целевой объект  
 *Целевой объект* — это <xref:System.Windows.Controls.Primitives.Popup> элемент, с которым связан. Если <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> свойство установлено, оно определяет целевой объект.  Если <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> не установлен, <xref:System.Windows.Controls.Primitives.Popup> а у него есть родитель, родительский объект является целевым объектом.  Если нет <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> значения и нет родительского, нет целевого объекта, и <xref:System.Windows.Controls.Primitives.Popup> он расположен относительно экрана.  
  
 Следующий пример <xref:System.Windows.Controls.Primitives.Popup> создает, что является <xref:System.Windows.Controls.Canvas>ребенком .  Пример не устанавливает <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> свойство <xref:System.Windows.Controls.Primitives.Popup>на . Значение по <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> умолчанию для <xref:System.Windows.Controls.Primitives.Popup> есть, <xref:System.Windows.Controls.Canvas> <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>поэтому появляется ниже .  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 Ниже показано, что <xref:System.Windows.Controls.Primitives.Popup> позиционируется <xref:System.Windows.Controls.Canvas>по отношению к .  
  
 ![Элемент управления всплывающим окном без PlacementTarget](./media/popup-placement-behavior/popup-placement-no-placement-target.png "Всплывающее окно без placementTarget.")  

 Следующий пример <xref:System.Windows.Controls.Primitives.Popup> создает, что является <xref:System.Windows.Controls.Canvas>ребенком, <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> но на `ellipse1`этот раз установлен на <xref:System.Windows.Shapes.Ellipse>, так всплывающее окно появляется ниже .  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 Ниже показано, что <xref:System.Windows.Controls.Primitives.Popup> позиционируется <xref:System.Windows.Shapes.Ellipse>по отношению к .  
  
 ![Размещение всплывающего окна относительно эллипса](./media/popup-placement-behavior/popup-placement-with-placement-target.png "Всплывающее окно с PlacementTarget")
  
> [!NOTE]
> Для, <xref:System.Windows.Controls.ToolTip>значение <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> по <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>умолчанию .  Для, <xref:System.Windows.Controls.ContextMenu>значение <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> по <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>умолчанию . Эти значения описаны дальше, в разделе "Совместная работа свойств".  
  
### <a name="target-area"></a>Целевая область  
 Целевой *областью* является область на <xref:System.Windows.Controls.Primitives.Popup> экране, к которую он находится относительно. В предыдущих примерах <xref:System.Windows.Controls.Primitives.Popup> он выравнивается по границам целевого объекта, <xref:System.Windows.Controls.Primitives.Popup> но в некоторых случаях выравнивается <xref:System.Windows.Controls.Primitives.Popup> по другим границам, даже если у объекта-цели есть объект.  Если <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> свойство установлено, целевая область отличается от границ целевого объекта.  
  
 Следующий пример <xref:System.Windows.Controls.Canvas> создает два объекта, <xref:System.Windows.Shapes.Rectangle> каждый из которых содержит a и a. <xref:System.Windows.Controls.Primitives.Popup>  В обоих случаях целевым <xref:System.Windows.Controls.Primitives.Popup> объектом для <xref:System.Windows.Controls.Canvas>является. В <xref:System.Windows.Controls.Primitives.Popup> первом <xref:System.Windows.Controls.Canvas> есть <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> набор, с <xref:System.Windows.Rect.X%2A> <xref:System.Windows.Rect.Y%2A>его <xref:System.Windows.Rect.Width%2A>, <xref:System.Windows.Rect.Height%2A> , и свойства, установленные на 50, 50, 50 и 100, соответственно. Во <xref:System.Windows.Controls.Primitives.Popup> втором <xref:System.Windows.Controls.Canvas> нет <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> набора.  <xref:System.Windows.Controls.Primitives.Popup> В результате, первый расположен <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ниже, а <xref:System.Windows.Controls.Primitives.Popup> второй расположен <xref:System.Windows.Controls.Canvas>ниже . Каждый <xref:System.Windows.Controls.Canvas> также <xref:System.Windows.Shapes.Rectangle> содержит, что имеет <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> те же <xref:System.Windows.Controls.Primitives.Popup>границы, как для первого .  Обратите внимание, что не <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> создается видимый элемент в приложении; пример создает <xref:System.Windows.Shapes.Rectangle> для представления <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 На следующем рисунке показан результат примера, приведенного выше.  
  
 ![Всплывающее меню с PlacementRectangle и без него](./media/popup-placement-behavior/popup-placement-placement-rectangle.png "Всплывающее окно с и без размещенияRectangle.")  

### <a name="target-origin-and-popup-alignment-point"></a>Исходная точка и точка выравнивания всплывающего окна  
 *Исходная точка* и *точка выравнивания всплывающего окна* являются опорными точками на целевой области и всплывающем окне соответственно, которые используются для позиционирования. Вы можете <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> использовать <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> и свойства, чтобы компенсировать всплывающее окно из целевой области.  И <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> являются относительно целевого происхождения и точки выравнивания всплывающих данных. Значение <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойства определяет, где находится место происхождения цели и точка выравнивания всплывающих данных.  
  
 Следующий пример <xref:System.Windows.Controls.Primitives.Popup> создает и <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> устанавливает и свойства до 20.  Свойство <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> настроено <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> (по умолчанию), поэтому цель происхождения является нижним левым углом целевой области и всплывающее точка выравнивания является верхним левым углом <xref:System.Windows.Controls.Primitives.Popup>.  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 На следующем рисунке показан результат примера, приведенного выше.  
  
 ![Размещение всплывающего окна с точкой выравнивания в исходной точке](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "Всплывающее окно с HorizontalOffset и VerticalOffset.")
  
<a name="How"></a>
## <a name="how-the-properties-work-together"></a>Совместная работа свойств  
 Значения <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>и <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> должны быть рассмотрены вместе, чтобы выяснить правильную целевую область, целевое происхождение и всплывающие точки выравнивания.  Например, если значение <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>является, нет целевого <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> объекта, игнорируется, а целевая область является границами указателя мыши. С другой <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> стороны, <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>если <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> есть, то родитель <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> определяет целевой объект и определяет целевую область.  
  
 В следующей таблице описывается целевой объект, целевая область, <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> начало цели <xref:System.Windows.Controls.Primitives.PlacementMode> и точка выравнивания всплывающих данных и указывается, используются ли значение каждого перечисления и используются ли они для каждого значения перечисления.  
  
|PlacementMode|Целевой объект|Целевая область|Исходная точка|Точка выравнивания всплывающего окна|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Неприменимо. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> игнорируется.|Экран, или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> если он установлен.  По <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> отношению к экрану.|Левый верхний угол целевой области.|Верхний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Неприменимо. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> игнорируется.|Экран, или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> если он установлен.  По <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> отношению к экрану.|Левый верхний угол целевой области.|Верхний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>или родителей.|Целевой объект, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> или если он установлен.  Относительно <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> целевого объекта.|Левый нижний угол целевой области.|Верхний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>или родителей.|Целевой объект, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> или если он установлен.  Относительно <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> целевого объекта.|Центр целевой области.|Центр <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>или родителей.|Целевой объект, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> или если он установлен.  Относительно <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> целевого объекта.|Определяется <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|Определяется <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>или родителей.|Целевой объект, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> или если он установлен.  Относительно <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> целевого объекта.|Левый верхний угол целевой области.|В правом верхнем <xref:System.Windows.Controls.Primitives.Popup>углу .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Неприменимо. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> игнорируется.|Границы указателя мыши. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> игнорируется.|Левый нижний угол целевой области.|Верхний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Неприменимо. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> игнорируется.|Границы указателя мыши. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> игнорируется.|Левый верхний угол целевой области.|Верхний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>или родителей.|Целевой объект, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> или если он установлен.  Относительно <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> целевого объекта.|Левый верхний угол целевой области.|Верхний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>или родителей.|Целевой объект, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> или если он установлен.  Относительно <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> целевого объекта.|Левый верхний угол целевой области.|Верхний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>или родителей.|Целевой объект, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> или если он установлен.  Относительно <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> целевого объекта.|Правый верхний угол целевой области.|Верхний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>или родителей.|Целевой объект, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> или если он установлен.  Относительно <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> целевого объекта.|Левый верхний угол целевой области.|В левом нижнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
  
 Следующие иллюстрации <xref:System.Windows.Controls.Primitives.Popup>показывают область, целевую область, целевое <xref:System.Windows.Controls.Primitives.PlacementMode> происхождение и точку выравнивания всплывающих данных для каждого значения. В каждой фигуре целевая <xref:System.Windows.Controls.Primitives.Popup> область желтая, а синяя.  
  
 ![Всплывающее окно с абсолютным размещением или размещением с помощью AbsolutePoint](./media/popup-placement-behavior/popup-placement-absolute.png "Размещение является Абсолютным или АбсолютПойнт.")
  
 ![Всплывающее окно с размещением внизу](./media/popup-placement-behavior/popup-placement-bottom.png "Размещение - это дно.")
  
 ![Всплывающее окно с размещением по центру](./media/popup-placement-behavior/popup-placement-center.png "Размещение центр.")
  
 ![Всплывающее окно с размещением слева](./media/popup-placement-behavior/popup-placement-left.png "Размещение осталось.")
  
 ![Всплывающее окно с размещением относительно мыши](./media/popup-placement-behavior/popup-placement-mouse.png "Размещение мышь.")  
  
 ![Всплывающее окно с размещением с помощью MousePoint](./media/popup-placement-behavior/popup-placement-mousepoint.png "Размещение MousePoint.")  
  
 ![Всплывающее окно с относительным размещением или размещением с помощью RelativePoint](./media/popup-placement-behavior/popup-placement-relative.png "Размещение является относительным или relativePoint.")
  
 ![Всплывающее окно с размещением справа](./media/popup-placement-behavior/popup-placement-right.png "Размещение является правильным.")
  
 ![Всплывающее окно с размещением сверху](./media/popup-placement-behavior/popup-placement-top.png "Размещение является верхней.")
  
<a name="When"></a>
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Когда всплывающее окно достигает края экрана  
 По соображениям безопасности, не <xref:System.Windows.Controls.Primitives.Popup> может быть скрыт акропором экрана. Одна из следующих трех <xref:System.Windows.Controls.Primitives.Popup> вещей происходит, когда сталкивается с краем экрана:  
  
- Всплывающее окно перестраивается вдоль края <xref:System.Windows.Controls.Primitives.Popup>экрана, что бы скрыть .  
  
- Всплывающее окно использует другую точку выравнивания.  
  
- Всплывающее окно использует другую исходную точку и точку выравнивания.  
  
 Эти параметры будут описаны далее в данном разделе.  
  
 Поведение, <xref:System.Windows.Controls.Primitives.Popup> когда он сталкивается с краем экрана, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> зависит от значения свойства и того, какой край экрана сталкивается с всплывающими кадрами. В следующей таблице приводится <xref:System.Windows.Controls.Primitives.Popup> краткое изложение <xref:System.Windows.Controls.Primitives.PlacementMode> поведения при столкновении с краем экрана для каждого значения.  
  
|PlacementMode|Верхний край|Нижний край|Левый край|Правый край|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Выравнивание по верхнему краю.|Точка выравнивания всплывающих пунктов изменяется <xref:System.Windows.Controls.Primitives.Popup>в левый нижний угол .|Выравнивание по левому краю.|Точка выравнивания всплывающих пунктов изменяется <xref:System.Windows.Controls.Primitives.Popup>в правом верхнем углу .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Выравнивание по верхнему краю.|Целевое происхождение изменяется в верхнем левом углу целевой области, а точка выравнивания всплывающих пунктов изменяется в левый нижний угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Целевое происхождение изменяется в правом верхнем углу целевой области, а точка выравнивания всплывающих пунктов изменяется в верхний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Выравнивание по верхнему краю.|Целевое происхождение изменяется в верхнем левом углу целевой области (границы указателя мыши) и точка выравнивания <xref:System.Windows.Controls.Primitives.Popup>всплывающих сторон изменяется в левый нижний угол .|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Выравнивание по верхнему краю.|Точка выравнивания всплывающих пунктов изменяется <xref:System.Windows.Controls.Primitives.Popup>в левый нижний угол .|Выравнивание по левому краю.|Точка выравнивания всплывающего окна переходит в верхний правый угол всплывающего окна.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|Выравнивание по верхнему краю.|Точка выравнивания всплывающих пунктов изменяется <xref:System.Windows.Controls.Primitives.Popup>в левый нижний угол .|Выравнивание по левому краю.|Точка выравнивания всплывающего окна переходит в верхний правый угол всплывающего окна.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Целевое происхождение изменяется в верхнем левом углу целевой области, а точка выравнивания всплывающих пунктов изменяется в правом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|Целевое происхождение изменяется в левом нижнем углу целевой области, а точка выравнивания <xref:System.Windows.Controls.Primitives.Popup>всплывающих пунктов изменяется в лево-верхний угол . По сути, это то <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> же <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>самое, когда это .|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
  
### <a name="aligning-to-the-screen-edge"></a>Выравнивание по краю экрана  
 А <xref:System.Windows.Controls.Primitives.Popup> может выровнять к краю экрана, перепозиционируя себя так, чтобы все <xref:System.Windows.Controls.Primitives.Popup> было видно на экране.  Когда это происходит, расстояние между целевым происхождением и точкой <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> выравнивания всплывающих данных может отличаться от значений и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>. <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Когда, <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute> <xref:System.Windows.Controls.Primitives.PlacementMode.Center>или <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>, <xref:System.Windows.Controls.Primitives.Popup> выравнивает себя к каждому краю экрана.  Например, предположим, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> что <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> он <xref:System.Windows.Controls.Primitives.Popup> установил и установил 100.  Если нижний край экрана скрывает все или <xref:System.Windows.Controls.Primitives.Popup>часть, <xref:System.Windows.Controls.Primitives.Popup> то перепозиционирует себя вдоль нижнего края экрана, а вертикальное расстояние между целевым происхождением и точкой выравнивания всплывающих частей меньше 100. Эта ситуация представлена на рисунке ниже.  
  
 ![Всплывающее окно, выравниваемое по краю экрана](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "Всплывающее окно выравнивается к краю экрана.")
  
### <a name="changing-the-popup-alignment-point"></a>Изменение точки выравнивания всплывающего окна  
 Если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>есть, <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint> <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>или , всплывающее место выравнивания меняется, когда всплывающее окно сталкивается с нижней или правой кромки экрана.  
  
 Следующая иллюстрация показывает, что, когда нижний край <xref:System.Windows.Controls.Primitives.Popup>экрана скрывает все или часть, точка <xref:System.Windows.Controls.Primitives.Popup>выравнивания всплывающих окно является нижним левым углом .  
  
 ![Новая точка выравнивания относительно нижнего края экрана](./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "Всплывающее окно сталкивается с нижним краем экрана и изменяет точку выравнивания всплывающих данных.")  

 Следующая иллюстрация показывает, <xref:System.Windows.Controls.Primitives.Popup> что, когда скрыты правый край экрана, всплывающее выравнивание точки верхнего правого угла <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания всплывающего окна относительно края экрана](./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "Всплывающее окно сталкивается с правым краем экрана и изменяет точку выравнивания всплывающих данных.")
  
 Если <xref:System.Windows.Controls.Primitives.Popup> перед нижним и правым краями экрана, точка выравнивания всплывающих <xref:System.Windows.Controls.Primitives.Popup>лиц является нижним правым углом.  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>Изменение положения исходной точки и точки выравнивания всплывающего окна  
 Когда <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>это <xref:System.Windows.Controls.Primitives.PlacementMode.Left> <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, <xref:System.Windows.Controls.Primitives.PlacementMode.Right>, <xref:System.Windows.Controls.Primitives.PlacementMode.Top>, или , целевого происхождения и всплывающих выравнивания точки изменения, если определенный край экрана встречается.  Край экрана, который приводит к изменению позиции, зависит от <xref:System.Windows.Controls.Primitives.PlacementMode> значения.  
  
 Следующая иллюстрация показывает, что, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> когда и <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> <xref:System.Windows.Controls.Primitives.Popup> сталкивается с нижней кромкой экрана, цель происхождения в верхнем левом углу <xref:System.Windows.Controls.Primitives.Popup>целевой области и всплывающее точка выравнивания является нижним левым углом .  
  
 ![Новая точка выравнивания относительно нижнего края экрана](./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "Размещение является нижним и всплывающее окно сталкивается с нижней кромкой экрана.")
  
 Следующая иллюстрация показывает, что, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> когда и <xref:System.Windows.Controls.Primitives.PlacementMode.Left> <xref:System.Windows.Controls.Primitives.Popup> встречи с левым краем экрана, целевой источник является верхним правым углом целевой области и всплывающее точка выравнивания является верхним левым углом . <xref:System.Windows.Controls.Primitives.Popup>  
  
 ![Новая точка выравнивания относительно левого края экрана](./media/popup-placement-behavior/popup-placement-left-screen-edge.png "Размещение слева и всплывающее окно сталкивается с левым краем экрана.")  
  
 Следующая иллюстрация показывает, что, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> когда и <xref:System.Windows.Controls.Primitives.PlacementMode.Right> <xref:System.Windows.Controls.Primitives.Popup> сталкивается с правым краем экрана, цель происхождения в верхнем левом углу <xref:System.Windows.Controls.Primitives.Popup>целевой области и всплывающее точка выравнивания является верхним правым углом .  
  
 ![Новая точка выравнивания относительно правого края экрана](./media/popup-placement-behavior/popup-placement-right-screen-edge.png "Размещение является правильным и всплывающие встречи правого края экрана.")  

 Следующая иллюстрация показывает, что, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> когда и <xref:System.Windows.Controls.Primitives.PlacementMode.Top> <xref:System.Windows.Controls.Primitives.Popup> сталкивается с верхним краем экрана, цель происхождения в левом нижнем углу целевой области и всплывающее точка выравнивания является верхним левым углом . <xref:System.Windows.Controls.Primitives.Popup>  
  
 ![Новая точка выравнивания относительно верхнего края экрана](./media/popup-placement-behavior/popup-placement-top-screen-edge.png "Размещение top и всплывающее окно сталкивается с верхней кромкой экрана.")  
  
 Следующая иллюстрация показывает, что, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> когда и <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> <xref:System.Windows.Controls.Primitives.Popup> сталкивается с нижней кромкой экрана, цель происхождения в верхнем левом углу целевой области (границы <xref:System.Windows.Controls.Primitives.Popup>указателя мыши) и всплывающее место выравнивания является нижним левым углом .  
  
 ![новая точка выравнивания относительно положения мыши возле края экрана](./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "Размещение мышь и всплывающее окно сталкивается с нижней кромки экрана.")
  
### <a name="customizing-popup-placement"></a>Настройка размещения всплывающего окна  
 Вы можете настроить целевое происхождение и точку <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> выравнивания всплывающих данных, установив <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>свойство. Затем определите делегата, <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> который возвращает набор возможных точек размещения и <xref:System.Windows.Controls.Primitives.Popup>основных осей (в порядке предпочтения) для . Точка, отображаемый самой большой частью выбранной <xref:System.Windows.Controls.Primitives.Popup> части.  Положение <xref:System.Windows.Controls.Primitives.Popup> автоматически корректируется, <xref:System.Windows.Controls.Primitives.Popup> если скрыто краем экрана. См. пример в разделе [Указание пользовательского расположения всплывающего окна](how-to-specify-a-custom-popup-position.md).  
  
## <a name="see-also"></a>См. также раздел

- [Пример размещения всплывающего окна](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)
