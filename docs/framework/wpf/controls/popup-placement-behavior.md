---
title: "Поведение при размещении контекстного меню | Microsoft Docs"
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
  - "всплывающие окна"
  - "Popup-элемент управления, размещение"
  - "всплывающие окна - размещение"
  - "позиционирование всплывающих окон"
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Поведение при размещении контекстного меню
Объект <xref:System.Windows.Controls.Primitives.Popup> элемент управления отображает содержимое в отдельном окне, расположенном поверх приложения. Можно указать положение <xref:System.Windows.Controls.Primitives.Popup> относительно элемента управления, мыши или экрана с помощью <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> свойства.  Эти свойства совместно обеспечивают гибкость при указании положения объекта <xref:System.Windows.Controls.Primitives.Popup>.  
  
> [!NOTE]
>  <xref:System.Windows.Controls.ToolTip> и <xref:System.Windows.Controls.ContextMenu> классы также определяются эти пять свойств и ведут себя аналогичным образом.  
  
   
  
<a name="Positioning"></a>   
## <a name="positioning-the-popup"></a>Размещение всплывающего окна  
 Размещение <xref:System.Windows.Controls.Primitives.Popup> может быть относительно <xref:System.Windows.UIElement> или на весь экран.  В следующем примере создаются четыре <xref:System.Windows.Controls.Primitives.Popup> элементов управления, относящихся к <xref:System.Windows.UIElement>— в данном случае изображения. Все <xref:System.Windows.Controls.Primitives.Popup> элементы управления имеют <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> свойству присвоено `image1`, но каждый <xref:System.Windows.Controls.Primitives.Popup> имеет другое значение свойства размещения.  
  
 [!code-xml[PopupPositionSnippet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 На следующем рисунке показано изображение и <xref:System.Windows.Controls.Primitives.Popup> элементов управления  
  
 ![Изображение с четырьмя элементами управления всплывающих окон](../../../../docs/framework/wpf/controls/media/popupplacementintro.png "PopupPlacementIntro")  
Изображение с четырьмя контекстными меню  
  
 В этом простом примере показано, как задать <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> и <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойства, но с помощью <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> свойства, у вас есть еще большего контроля над where <xref:System.Windows.Controls.Primitives.Popup> располагается.  
  
<a name="Definitions"></a>   
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>Определение терминов: Анатомия контекстного меню  
 Следующие термины полезны в понимании того как <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> свойства связаны друг с другом и <xref:System.Windows.Controls.Primitives.Popup>:  
  
-   Целевой объект  
  
-   Целевая область  
  
-   Исходная точка  
  
-   Точка выравнивания всплывающего окна  
  
 Эти термины предоставляют удобный способ для ссылки на различные аспекты <xref:System.Windows.Controls.Primitives.Popup> элементов управления, связанного с ним.  
  
### <a name="target-object"></a>Целевой объект  
 *Целевой объект* является элементом, <xref:System.Windows.Controls.Primitives.Popup> связан. Если <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> свойство задано, оно указывает целевой объект.  Если <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> не задано и <xref:System.Windows.Controls.Primitives.Popup> имеет родителя, родительским является целевым объектом.  Если не <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> значение и родитель, нет целевого объекта и <xref:System.Windows.Controls.Primitives.Popup> расположено относительно экрана.  
  
 В следующем примере создается <xref:System.Windows.Controls.Primitives.Popup> , является дочерним <xref:System.Windows.Controls.Canvas>.  В примере задается <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> свойство <xref:System.Windows.Controls.Primitives.Popup>. Значение по умолчанию для <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode?displayProperty=fullName>, поэтому <xref:System.Windows.Controls.Primitives.Popup> под <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xml[PopupPositionSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 На следующем рисунке показано, что <xref:System.Windows.Controls.Primitives.Popup> расположено относительно <xref:System.Windows.Controls.Canvas>.  
  
 ![Элемент управления всплывающим окном без PlacementTarget](../../../../docs/framework/wpf/controls/media/popupplacementnoplacementtarget.png "PopupPlacementNoPlacementTarget")  
Всплывающее окно без PlacementTarget  
  
 В следующем примере создается <xref:System.Windows.Controls.Primitives.Popup> , является дочерним <xref:System.Windows.Controls.Canvas>, но на этот раз <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> задано значение `ellipse1`, поэтому контекстное меню появляется ниже <xref:System.Windows.Shapes.Ellipse>.  
  
 [!code-xml[PopupPositionSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 На следующем рисунке показано, что <xref:System.Windows.Controls.Primitives.Popup> расположено относительно <xref:System.Windows.Shapes.Ellipse>.  
  
 ![Размещение всплывающего окна относительно эллипса](../../../../docs/framework/wpf/controls/media/popupplacementwithplacementtarget.png "PopupPlacementWithPlacementTarget")  
Всплывающее окно с PlacementTarget  
  
> [!NOTE]
>  Для <xref:System.Windows.Controls.ToolTip>, значение по умолчанию <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode>.  Для <xref:System.Windows.Controls.ContextMenu>, значение по умолчанию <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode>. Эти значения описаны дальше, в «Как свойства работают совместно.»  
  
### <a name="target-area"></a>Целевая область  
 *Целевой области* — это область на экране, <xref:System.Windows.Controls.Primitives.Popup> относительно. В предыдущих примерах <xref:System.Windows.Controls.Primitives.Popup> выравнивается с границами целевого объекта, но в некоторых случаях <xref:System.Windows.Controls.Primitives.Popup> выравнивается по другим границам, даже если <xref:System.Windows.Controls.Primitives.Popup> имеет целевой объект.  Если <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> свойство установлено, целевая область отличается от границ целевого объекта.  
  
 В следующем примере создаются два <xref:System.Windows.Controls.Canvas> объектов, каждый из которых содержит <xref:System.Windows.Shapes.Rectangle> и <xref:System.Windows.Controls.Primitives.Popup>.  В обоих случаях целевым объектом для <xref:System.Windows.Controls.Primitives.Popup> — <xref:System.Windows.Controls.Canvas>. <xref:System.Windows.Controls.Primitives.Popup> в первом <xref:System.Windows.Controls.Canvas> имеет <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> задано, с его <xref:System.Windows.Rect.X%2A>, <xref:System.Windows.Rect.Y%2A>, <xref:System.Windows.Rect.Width%2A>, и <xref:System.Windows.Rect.Height%2A> свойства, равным 50, 50, 50 и 100, соответственно. <xref:System.Windows.Controls.Primitives.Popup> во втором <xref:System.Windows.Controls.Canvas> не имеет <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> значение.  В результате первый <xref:System.Windows.Controls.Primitives.Popup> находится ниже <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , а второй <xref:System.Windows.Controls.Primitives.Popup> находится ниже <xref:System.Windows.Controls.Canvas>. Каждый <xref:System.Windows.Controls.Canvas> также содержит <xref:System.Windows.Shapes.Rectangle> , имеет те же границы как <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> для первого <xref:System.Windows.Controls.Primitives.Popup>.  Обратите внимание, что <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> не создает видимого элемента в приложении; создается <xref:System.Windows.Shapes.Rectangle> для представления <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  
  
 [!code-xml[PopupPositionSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 Ниже показан результат предыдущего примера.  
  
 ![Всплывающее окно с PlacementRectangle и без него](../../../../docs/framework/wpf/controls/media/popupplacementplacementrectangle.png "PopupPlacementPlacementRectangle")  
Всплывающее меню с PlacementRectangle и без него  
  
### <a name="target-origin-and-popup-alignment-point"></a>Начало координат и точка выравнивания всплывающего окна  
 *Целевой источник* и *точка выравнивания всплывающего окна* являются точками ссылок на целевую область и контекстное меню, соответственно, которые используются для позиционирования. Можно использовать <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> свойства для смещения контекстного меню из целевой области.  <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> относительны координат и точка выравнивания всплывающего окна. Значение <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойство определяет, где находятся целевую исходную точку и другую точку выравнивания.  
  
 В следующем примере создается <xref:System.Windows.Controls.Primitives.Popup> и задает <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> свойства до 20.  <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойству <xref:System.Windows.Controls.Primitives.PlacementMode> (по умолчанию), поэтому исходная точка расположена в нижнем левом углу области назначения, а точка выравнивания находится в левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 [!code-xml[PopupPositionSnippet#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 Ниже показан результат предыдущего примера.  
  
 ![Размещение всплывающего окна в точке выравнивания начала цели](../../../../docs/framework/wpf/controls/media/popupplacementtargetoriginalignmentpoint.PNG "PopupPlacementTargetOriginAlignmentPoint")  
Всплывающее окно с HorizontalOffset и VerticalOffset  
  
<a name="How"></a>   
## <a name="how-the-properties-work-together"></a>Работа свойств  
 Значения <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, и <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> должны рассматриваться вместе для выяснения правильной целевой области, исходная точка и точка выравнивания всплывающего окна.  Например если значение <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode>, отсутствует целевой объект <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> игнорируется, и целевая область является границы указателя мыши. С другой стороны Если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode>, <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родитель определяет конечный объект и <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> определяет целевую область.  
  
 В следующей таблице описываются целевой объект, целевая область, исходная точка и точка выравнивания всплывающего окна и указывает, является ли <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> и <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> используются для каждого <xref:System.Windows.Controls.Primitives.PlacementMode> значение перечисления.  
  
|PlacementMode|Целевой объект|Целевая область|Исходная точка|Точка выравнивания всплывающего окна|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|Неприменимо. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> игнорируется.|Экран или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , если оно задано.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> относительно экрана.|Левый верхний угол области назначения.|В левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|Неприменимо. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> игнорируется.|Экран или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , если оно задано.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> относительно экрана.|Левый верхний угол области назначения.|В левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительского.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , если оно задано.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> относительно целевого объекта.|Нижний левый угол области назначения.|В левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительского.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , если оно задано.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> относительно целевого объекта.|Центр целевой области.|Центр <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительского.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , если оно задано.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> относительно целевого объекта.|Определяется <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|Определяется <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительского.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , если оно задано.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> относительно целевого объекта.|Левый верхний угол области назначения.|В правом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|Неприменимо. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> игнорируется.|Границы указателя мыши. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> учитывается.|Нижний левый угол области назначения.|В левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|Неприменимо. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> игнорируется.|Границы указателя мыши. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> учитывается.|Левый верхний угол области назначения.|В левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительского.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , если оно задано.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> относительно целевого объекта.|Левый верхний угол области назначения.|В левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительского.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , если оно задано.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> относительно целевого объекта.|Левый верхний угол области назначения.|В левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительского.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , если оно задано.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> относительно целевого объекта.|Верхний правый угол области назначения.|В левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительского.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , если оно задано.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> относительно целевого объекта.|Левый верхний угол области назначения.|В нижнем левом углу <xref:System.Windows.Controls.Primitives.Popup>.|  
  
 На следующих рисунках <xref:System.Windows.Controls.Primitives.Popup>, целевая область, исходная точка и выравнивания контекстного меню выберите команду для каждого <xref:System.Windows.Controls.Primitives.PlacementMode> значение. В каждом рисунке целевая область является желтый и <xref:System.Windows.Controls.Primitives.Popup> — синим.  
  
 ![Всплывающее окно с абсолютным или AbsolutePoint размещением](../../../../docs/framework/wpf/controls/media/popupplacementabsolute.png "PopupPlacementAbsolute")  
Расположение является абсолютным или AbsolutePoint  
  
 ![Всплывающее окно с нижним размещением](../../../../docs/framework/wpf/controls/media/popupplacementbottom.png "PopupPlacementBottom")  
Расположение — снизу  
  
 ![Всплывающее окно с центральным размещением](../../../../docs/framework/wpf/controls/media/popupplacementcenter.png "PopupPlacementCenter")  
Расположение является центр  
  
 ![Всплывающее окно с левым размещением](../../../../docs/framework/wpf/controls/media/popupplacementleft.png "PopupPlacementLeft")  
Расположение — влево  
  
 ![Всплывающее окно с размещением относительны мыши](../../../../docs/framework/wpf/controls/media/popupplacementmouse.png "PopupPlacementMouse")  
Расположение является мыши  
  
 ![Всплывающее окно с размещением MousePoint](../../../../docs/framework/wpf/controls/media/popupplacementmousepoint.png "PopupPlacementMousePoint")  
Расположение является MousePoint  
  
 ![Всплывающее окно с относительным или RelativePoint размещением](../../../../docs/framework/wpf/controls/media/popupplacementrelative.png "PopupPlacementRelative")  
Расположение является относительным или RelativePoint  
  
 ![Всплывающее окно с правым размещением](../../../../docs/framework/wpf/controls/media/popupplacementright.png "PopupPlacementRight")  
Расположение является вправо  
  
 ![Всплывающее окно с верхним размещением](../../../../docs/framework/wpf/controls/media/popupplacementtop.png "PopupPlacementTop")  
Расположение — начало  
  
<a name="When"></a>   
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Когда меню достигает края экрана  
 По соображениям безопасности <xref:System.Windows.Controls.Primitives.Popup> не могут быть скрыты по краю экрана. Одно из следующих трех действий происходит при <xref:System.Windows.Controls.Primitives.Popup> край экрана:  
  
-   Контекстное меню располагается вдоль края экрана, который мог бы скрыть <xref:System.Windows.Controls.Primitives.Popup>.  
  
-   Контекстное меню использует различные точки выравнивания.  
  
-   Всплывающее окно использует другой целевой объект исходную точку и другую точку выравнивания.  
  
 Эти параметры будут описанные далее в этом разделе.  
  
 Поведение <xref:System.Windows.Controls.Primitives.Popup> при обнаружении края экрана зависит от значения <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойства, а какие краев, контекстное меню встречает экрана. В следующей таблице представлены поведения при <xref:System.Windows.Controls.Primitives.Popup> края экрана для каждого <xref:System.Windows.Controls.Primitives.PlacementMode> значение.  
  
|PlacementMode|Верхний край|Нижний край|Левый край|Правый край|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|Выравнивание по верхнему краю.|Точка выравнивания всплывающего окна меняется на нижний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Точка выравнивания всплывающего окна изменяется в правом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|Выравнивание по верхнему краю.|Изменяет координат в левом верхнем углу области назначения, а точка выравнивания всплывающего окна в нижний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Изменяет исходная точка в верхнем правом углу области назначения, а точка выравнивания по верхнему левому углу <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|Выравнивание по верхнему краю.|Исходная точка изменяется на верхний левый угол области назначения (границы указателя мыши) и точка выравнивания всплывающего окна меняется на нижний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|Выравнивание по верхнему краю.|Точка выравнивания всплывающего окна меняется на нижний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Точка выравнивания всплывающего окна меняется на верхний правый угол всплывающего окна.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|Выравнивание по верхнему краю.|Точка выравнивания всплывающего окна меняется на нижний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Точка выравнивания всплывающего окна меняется на верхний правый угол всплывающего окна.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Изменяет координат в левом верхнем углу области назначения, а точка выравнивания всплывающего окна в правом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode>|Изменяет координат в нижнем левом углу области назначения, а точка выравнивания по верхнему левому углу <xref:System.Windows.Controls.Primitives.Popup>. По сути, это то же самое, как и при <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode>.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
  
### <a name="aligning-to-the-screen-edge"></a>Выравнивание по краю экрана  
 Объект <xref:System.Windows.Controls.Primitives.Popup> можно выровнять по краю экрана путем изменения расположения таким образом вся <xref:System.Windows.Controls.Primitives.Popup> отображается на экране.  В этом случае расстояние между целевой источник и точке выравнивания всплывающего могут отличаться от значения <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>. При <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode>, <xref:System.Windows.Controls.Primitives.PlacementMode>, или <xref:System.Windows.Controls.Primitives.PlacementMode>, <xref:System.Windows.Controls.Primitives.Popup> выравнивается по каждому краю экрана.  Например, предположим, что <xref:System.Windows.Controls.Primitives.Popup> имеет <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> значение <xref:System.Windows.Controls.Primitives.PlacementMode> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> равным 100.  Если нижний край экрана скрывает все или часть <xref:System.Windows.Controls.Primitives.Popup>, <xref:System.Windows.Controls.Primitives.Popup> самостоятельно перемещается вдоль нижнего края экрана и расстояние по вертикали между началом координат целевого объекта и всплывающее окно точка выравнивания находится меньше 100. Это показано ниже.  
  
 ![Всплывающее окно, выравниваемое по краю экрана](../../../../docs/framework/wpf/controls/media/popupplacementrelativescreenedge.png "PopupPlacementRelativeScreenEdge")  
Контекстное меню выравнивается по краю экрана  
  
### <a name="changing-the-popup-alignment-point"></a>Изменение точка выравнивания всплывающего окна  
 Если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode>, <xref:System.Windows.Controls.Primitives.PlacementMode>, или <xref:System.Windows.Controls.Primitives.PlacementMode>, точка выравнивания всплывающего окна изменяется, если контекстное меню встречает нижнего или правого края экрана.  
  
 На следующем рисунке показано, что если нижний край экрана скрывает все или часть <xref:System.Windows.Controls.Primitives.Popup>, точка выравнивания находится в левом нижнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно нижнего края экрана](../../../../docs/framework/wpf/controls/media/popupplacementrelativepointscreenedge.png "PopupPlacementRelativePointScreenEdge")  
Контекстное меню встречает нижний край экрана и изменяет точку выравнивания контекстного меню  
  
 На следующем рисунке показано, что при <xref:System.Windows.Controls.Primitives.Popup> скрыт, правый край экрана, точка выравнивания находится в правом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания всплывающего окна края экрана](../../../../docs/framework/wpf/controls/media/popupplacementrelativepointrightscreenedge.png "PopupPlacementRelativePointRightScreenEdge")  
Контекстное меню встречает правый край экрана и изменяет точку выравнивания контекстного меню  
  
 Если <xref:System.Windows.Controls.Primitives.Popup> обнаруживает нижний и правый край экрана, точка выравнивания находится в нижнем правом углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>Изменение начало координат и точка выравнивания всплывающего окна  
 При <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode>, <xref:System.Windows.Controls.Primitives.PlacementMode>, <xref:System.Windows.Controls.Primitives.PlacementMode>, <xref:System.Windows.Controls.Primitives.PlacementMode>, или <xref:System.Windows.Controls.Primitives.PlacementMode>, выравнивание исходную точку и другую целевой точки изменений при обнаружении определенных краев экрана.  Зависит от края экрана, который вызывает изменение положения <xref:System.Windows.Controls.Primitives.PlacementMode> значение.  
  
 На следующем рисунке показано, что при <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode> и <xref:System.Windows.Controls.Primitives.Popup> встречает нижний край экрана, исходная точка расположена в левом верхнем углу области назначения, а точка выравнивания находится в левом нижнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно нижнего края экрана](../../../../docs/framework/wpf/controls/media/popupplacementbottomscreenedge.png "PopupPlacementBottomScreenEdge")  
Размещение по нижнему краю и контекстное меню встречает нижний край экрана  
  
 На следующем рисунке показано, что при <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode> и <xref:System.Windows.Controls.Primitives.Popup> встречает левый край экрана, исходная точка расположена в верхнем правом углу области назначения, а точка выравнивания находится в левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно левого края экрана](../../../../docs/framework/wpf/controls/media/popupplacementleftscreenedge.png "PopupPlacementLeftScreenEdge")  
Размещение по левому краю и контекстное меню встречает левый край экрана  
  
 На следующем рисунке показано, что при <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode> и <xref:System.Windows.Controls.Primitives.Popup> встречает правый край экрана, исходная точка расположена в левом верхнем углу области назначения, а точка выравнивания находится в правом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно правого края экрана](../../../../docs/framework/wpf/controls/media/popupplacementrightscreenedge.png "PopupPlacementRightScreenEdge")  
Размещение по правому краю и контекстное меню встречает правый край экрана  
  
 На следующем рисунке показано, что при <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode> и <xref:System.Windows.Controls.Primitives.Popup> встречает верхний край экрана, исходная точка расположена в нижнем левом углу области назначения, а точка выравнивания находится в левом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно верхнего края экрана](../../../../docs/framework/wpf/controls/media/popupplacementtopscreenedge.png "PopupPlacementTopScreenEdge")  
Размещение по верхнему краю и контекстное меню встречает верхний край экрана  
  
 На следующем рисунке показано, что при <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode> и <xref:System.Windows.Controls.Primitives.Popup> встречает нижний край экрана, исходная точка расположена в верхнем левом углу области назначения (границы указателя мыши), а точка выравнивания находится в левом нижнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно мыши возле края экрана](../../../../docs/framework/wpf/controls/media/popupplacementmousescreenedge.png "PopupPlacementMouseScreenEdge")  
Размещение указателя мыши и контекстное меню встречает нижний край экрана  
  
### <a name="customizing-popup-placement"></a>Настройка размещения контекстного меню  
 Целевой источник и точке выравнивания всплывающего можно настроить, задав <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойства <xref:System.Windows.Controls.Primitives.PlacementMode>. Затем определите <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> делегат, который возвращает набор возможных точек размещения и основные оси (в порядке предпочтения) для <xref:System.Windows.Controls.Primitives.Popup>. Точка, показывающая наибольшую часть <xref:System.Windows.Controls.Primitives.Popup> выбран.  Положение <xref:System.Windows.Controls.Primitives.Popup> автоматически настраивается, если <xref:System.Windows.Controls.Primitives.Popup> по краю экрана скрыт. Например, в разделе [указать положение всплывающего окна пользовательских](../../../../docs/framework/wpf/controls/how-to-specify-a-custom-popup-position.md).  
  
## <a name="see-also"></a>См. также  
 [Пример размещения всплывающего окна](http://go.microsoft.com/fwlink/?LinkID=160032)