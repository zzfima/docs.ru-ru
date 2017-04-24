---
title: "Общие сведения о контекстном меню | Microsoft Docs"
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
  - "элементы управления, Всплывающее окно"
  - "Popup - элемент управления [WPF], сведения об элементе управления Popup"
ms.assetid: 774f53ca-bff8-470e-9ce9-3928b4cf3d4c
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# Общие сведения о контекстном меню
Элемент управления <xref:System.Windows.Controls.Primitives.Popup> предоставляет способ отображения содержимого в отдельном окне, расположенном поверх текущего окна приложения относительно обозначенного элемента или экранных координат.  В этом разделе рассматриваются элементы управления <xref:System.Windows.Controls.Primitives.Popup> и содержатся сведения об их использовании.  
  
   
  
<a name="What_Is_a_Popup_"></a>   
## Что такое контекстное меню?  
 Элемент управления <xref:System.Windows.Controls.Primitives.Popup> отображает содержимое в отдельном окне относительно элемента или точки на экране.  Когда <xref:System.Windows.Controls.Primitives.Popup> является видимым, свойство <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> устанавливается в значение `true`.  
  
> [!NOTE]
>  <xref:System.Windows.Controls.Primitives.Popup> не открывается автоматически при наведении указателя мыши на родительский объект.  Если требуется, чтобы <xref:System.Windows.Controls.Primitives.Popup> открывалось автоматически, то следует использовать класс <xref:System.Windows.Controls.ToolTip> или <xref:System.Windows.Controls.ToolTipService>.  Дополнительные сведения см. в разделе [Общие сведения о всплывающих подсказках](../../../../docs/framework/wpf/controls/tooltip-overview.md).  
  
<a name="APopupExample"></a>   
## Создание контекстного меню  
 В следующем примере показано определение элемента управления <xref:System.Windows.Controls.Primitives.Popup>, являющегося дочерним элементом элемента управления <xref:System.Windows.Controls.Button>.  Поскольку <xref:System.Windows.Controls.Button> может иметь только один дочерний элемент, в этом примере текст для элементов управления <xref:System.Windows.Controls.Button> и <xref:System.Windows.Controls.Primitives.Popup> размещается в <xref:System.Windows.Controls.StackPanel>.  Содержимое <xref:System.Windows.Controls.Primitives.Popup> появляется в элементе управления <xref:System.Windows.Controls.TextBlock>, отображающем текст в отдельном окне, расположенном поверх окна приложения около связанного элемента управления <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[PopupSimple#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#1)]  
  
 [!code-xml[PopupSimple#CreatePopupCodeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#createpopupcodexaml)]  
  
<a name="PopupUses"></a>   
## Элементы управления, реализующие контекстное меню  
 Можно встраивать элементы управления <xref:System.Windows.Controls.Primitives.Popup> в другие элементы управления.  Следующие элементы управления реализуют элемент управления <xref:System.Windows.Controls.Primitives.Popup> для определенных целей:  
  
-   <xref:System.Windows.Controls.ToolTip>.  Если необходимо создать подсказку для элемента, то следует использовать классы <xref:System.Windows.Controls.ToolTip> и <xref:System.Windows.Controls.ToolTipService>.  Дополнительные сведения см. в разделе [Общие сведения о всплывающих подсказках](../../../../docs/framework/wpf/controls/tooltip-overview.md).  
  
-   <xref:System.Windows.Controls.ContextMenu>.  Если требуется создать контекстное меню для элемента, то следует использовать элемент управления <xref:System.Windows.Controls.ContextMenu>.  Дополнительные сведения см. в разделе [Общие сведения о ContextMenu](../../../../docs/framework/wpf/controls/contextmenu-overview.md).  
  
-   <xref:System.Windows.Controls.ComboBox>.  Если требуется создать элемент управления, предназначенный для выбора значения и имеющий раскрывающийся список, который можно отображать и скрывать, то следует использовать элемент управления <xref:System.Windows.Controls.ComboBox>.  
  
-   <xref:System.Windows.Controls.Expander>.  Если требуется создать элемент управления, отображающий заголовок со сворачиваемой областью отображения содержимого, то следует использовать элемент управления <xref:System.Windows.Controls.Expander>.  Дополнительные сведения см. в разделе [Общие сведения об элементе управления Expander](../../../../docs/framework/wpf/controls/expander-overview.md).  
  
<a name="PopupBehaviorandAppearance"></a>   
## Поведение и вид контекстного меню  
 Элемент управления <xref:System.Windows.Controls.Primitives.Popup> предоставляет функциональные возможности, которые позволяют настраивать его внешний вид и поведение.  Например, можно настроить поведение при открытии и закрытии, анимацию, эффекты прозрачности и размытия, а также размер и положение <xref:System.Windows.Controls.Primitives.Popup>.  
  
<a name="OpenandCloseBehavior"></a>   
### Поведение при открытии и закрытии  
 Элемент управления <xref:System.Windows.Controls.Primitives.Popup> отображает свое содержимое при установке свойства <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> в значение `true`.  По умолчанию <xref:System.Windows.Controls.Primitives.Popup> остается открытым до установки свойства <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> в `false`.  Однако можно изменить поведение по умолчанию, задав для свойства <xref:System.Windows.Controls.Primitives.Popup.StaysOpen%2A> значение `false`.  При установке этого свойства в значение `false`, содержимое окна <xref:System.Windows.Controls.Primitives.Popup> имеет захват указателя мыши.  <xref:System.Windows.Controls.Primitives.Popup> теряет захват указателя мыши и окно закрывается, если возникает событие мыши вне окна <xref:System.Windows.Controls.Primitives.Popup>.  
  
 События <xref:System.Windows.Controls.Primitives.Popup.Opened> и <xref:System.Windows.Controls.Primitives.Popup.Closed> вызываются при открытии или закрытии окна содержимого <xref:System.Windows.Controls.Primitives.Popup>.  
  
<a name="Animation"></a>   
### Анимация  
 Элемент управления <xref:System.Windows.Controls.Primitives.Popup> имеет встроенную поддержку анимаций, которые обычно связаны с таким поведением, как "постепенное проявление" или "выезд из\-за кадра"  Эти эффекты анимации можно включить, задав для свойства <xref:System.Windows.Controls.Primitives.Popup.PopupAnimation%2A> одно из значений перечисления <xref:System.Windows.Controls.Primitives.PopupAnimation>.  Для правильной работы анимации <xref:System.Windows.Controls.Primitives.Popup> необходимо установить значение свойства <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> в `true`.  
  
 Можно также применить анимацию по типу <xref:System.Windows.Media.Animation.Storyboard> к элементу управления <xref:System.Windows.Controls.Primitives.Popup>.  
  
<a name="OpacityandBitmapEffects"></a>   
### Эффекты прозрачности и размытия  
 Свойство <xref:System.Windows.UIElement.Opacity%2A> элемента управления <xref:System.Windows.Controls.Primitives.Popup> не влияет на его содержимое.  По умолчанию окно содержимого <xref:System.Windows.Controls.Primitives.Popup> является непрозрачным.  Для создания прозрачного <xref:System.Windows.Controls.Primitives.Popup> задайте для свойства <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> значение `true`.  
  
 Содержимое <xref:System.Windows.Controls.Primitives.Popup> не наследует эффекты размытия, такие как <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>, которые непосредственно устанавливаются в элементе управления <xref:System.Windows.Controls.Primitives.Popup> или любом другом элементе родительского окна.  Для отображения эффектов размытия в содержимом <xref:System.Windows.Controls.Primitives.Popup> необходимо задать эффект размытия непосредственно для его содержимого.  Например, если дочерний элемент <xref:System.Windows.Controls.Primitives.Popup> является <xref:System.Windows.Controls.StackPanel>, то следует задать эффект размытия для <xref:System.Windows.Controls.StackPanel>.  
  
<a name="PopupSize"></a>   
### Размер контекстного меню  
 По умолчанию <xref:System.Windows.Controls.Primitives.Popup> автоматически изменяет размер в соответствии с содержимым.  При автоматической регулировке размеров некоторые эффекты размытия могут быть скрыты, поскольку размер области экрана по умолчанию, который определен для содержимого <xref:System.Windows.Controls.Primitives.Popup>, не предоставляет достаточно места для отображения эффектов размытия.  
  
 Содержимое <xref:System.Windows.Controls.Primitives.Popup> может быть скрыто при задании <xref:System.Windows.UIElement.RenderTransform%2A> для содержимого.  В этом случае часть содержимого может быть скрыта, если содержимое преобразованного <xref:System.Windows.Controls.Primitives.Popup> выходит за пределы области исходного <xref:System.Windows.Controls.Primitives.Popup>.  Если для эффекта размытия или преобразования требуется больше места, то можно определить поля вокруг содержимого <xref:System.Windows.Controls.Primitives.Popup> для предоставления элементу управления дополнительного пространства.  
  
<a name="DefiningPopupPosition"></a>   
## Определение положения контекстного меню  
 Позиция всплывающего окна определяется свойствами <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffsetProperty>.  Дополнительные сведения см. в разделе [Поведение при размещении контекстного меню](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).  При отображении <xref:System.Windows.Controls.Primitives.Popup> на экране оно остается на прежнем месте, даже если изменилось положение его родительского элемента.  
  
<a name="CustomizingPopupPlacement"></a>   
### Пользовательская настройка размещения контекстного меню  
 Можно настроить размещение элемента управления <xref:System.Windows.Controls.Primitives.Popup>, указав набор координат, относящихся к <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, в которых необходимо отобразить <xref:System.Windows.Controls.Primitives.Popup>.  
  
 Чтобы настроить размещение, следует задать для свойства <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> значение <xref:System.Windows.Controls.Primitives.PlacementMode>.  Затем определите делегат <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>, который для <xref:System.Windows.Controls.Primitives.Popup> возвращает набор возможных точек размещения и основные оси \(в порядке приоритета\).  Точка, показывающая наибольшую часть <xref:System.Windows.Controls.Primitives.Popup>, выбирается автоматически.  Пример см. в разделе [Указание пользовательского расположения контекстного меню](../../../../docs/framework/wpf/controls/how-to-specify-a-custom-popup-position.md).  
  
<a name="PopupandtheVisualTree"></a>   
## Контекстное меню и визуальное дерево  
 Элемент управления <xref:System.Windows.Controls.Primitives.Popup> не имеет своего собственного [визуального дерева](GTMT). Вместо этого он возвращает размер 0 \(ноль\) при вызове метода <xref:System.Windows.Controls.Primitives.Popup.MeasureOverride%2A> для <xref:System.Windows.Controls.Primitives.Popup>.  Однако при задании свойства <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> для <xref:System.Windows.Controls.Primitives.Popup> в `true` создается новое окно со своим собственным визуальным деревом.  Новое окно включает содержимое <xref:System.Windows.Controls.Primitives.Popup.Child%2A> <xref:System.Windows.Controls.Primitives.Popup>.  Ширина и высота нового окна не может превышать 75 процентов от ширины или высоты окна.  
  
 Элемент управления <xref:System.Windows.Controls.Primitives.Popup> содержит ссылку на его содержимое <xref:System.Windows.Controls.Primitives.Popup.Child%2A> как на логический дочерний элемент.  При создании нового окна содержимое <xref:System.Windows.Controls.Primitives.Popup> становится визуальным дочерним элементом окна и остается логическим дочерним элементом <xref:System.Windows.Controls.Primitives.Popup>.  И наоборот <xref:System.Windows.Controls.Primitives.Popup> остается логическим родительским элементом содержимого <xref:System.Windows.Controls.Primitives.Popup.Child%2A>.  
  
## См. также  
 <xref:System.Windows.Controls.Primitives.Popup>   
 <xref:System.Windows.Controls.Primitives.PopupPrimaryAxis>   
 <xref:System.Windows.Controls.Primitives.PlacementMode>   
 <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>   
 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>   
 <xref:System.Windows.Controls.ToolTip>   
 <xref:System.Windows.Controls.ToolTipService>   
 [Практические руководства](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)   
 [Практические руководства](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)