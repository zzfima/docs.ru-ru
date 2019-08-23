---
title: Общие сведения о контекстном меню
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Popup
- Popup control [WPF], about Popup control
ms.assetid: 774f53ca-bff8-470e-9ce9-3928b4cf3d4c
ms.openlocfilehash: 7e6977737d362fd0df6321702bb8a1ac6cad66e0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951431"
---
# <a name="popup-overview"></a>Общие сведения о контекстном меню
<xref:System.Windows.Controls.Primitives.Popup> Элемент управления предоставляет способ отображения содержимого в отдельном окне, расположенном поверх текущего окна приложения относительно назначенного элемента или экранной координаты. В <xref:System.Windows.Controls.Primitives.Popup> этом разделе описывается элемент управления и предоставляются сведения об его использовании.  

<a name="What_Is_a_Popup_"></a>   
## <a name="what-is-a-popup"></a>Что такое контекстное меню?  
 <xref:System.Windows.Controls.Primitives.Popup> Элемент управления отображает содержимое в отдельном окне относительно элемента или точки на экране. Если отображается, свойство имеет значение `true`. <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> <xref:System.Windows.Controls.Primitives.Popup>  
  
> [!NOTE]
> Объект <xref:System.Windows.Controls.Primitives.Popup> не открывается автоматически при наведении указателя мыши на родительский объект. Если нужно, <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> чтобы автоматически открывался, используйте класс или. <xref:System.Windows.Controls.Primitives.Popup> Дополнительные сведения см. в разделе [Общие сведения о всплывающих подсказках](tooltip-overview.md).  
  
<a name="APopupExample"></a>   
## <a name="creating-a-popup"></a>Создание всплывающего окна  
 В следующем примере показано, как определить <xref:System.Windows.Controls.Primitives.Popup> элемент управления, который является дочерним элементом <xref:System.Windows.Controls.Button> элемента управления. Так как <xref:System.Windows.Controls.Button> у элемента может быть только один дочерний элемент, в этом примере <xref:System.Windows.Controls.Button> текст для <xref:System.Windows.Controls.Primitives.Popup> элементов управления <xref:System.Windows.Controls.StackPanel>и заносится в. Содержимое <xref:System.Windows.Controls.Primitives.Popup> элемента отображается <xref:System.Windows.Controls.TextBlock> в элементе управления, который отображает его текст в отдельном окне, расположенном над окном приложения рядом с соответствующим <xref:System.Windows.Controls.Button> элементом управления.  
  
 [!code-xaml[PopupSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#1)]  
  
 [!code-xaml[PopupSimple#CreatePopupCodeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#createpopupcodexaml)]  
  
<a name="PopupUses"></a>   
## <a name="controls-that-implement-a-popup"></a>Элементы управления, реализующие контекстное меню  
 Элементы управления можно <xref:System.Windows.Controls.Primitives.Popup> создавать в других элементах управления. Следующие элементы управления реализуют <xref:System.Windows.Controls.Primitives.Popup> элемент управления для конкретных применений.  
  
- <xref:System.Windows.Controls.ToolTip>. Если необходимо создать подсказку для элемента, используйте <xref:System.Windows.Controls.ToolTip> классы и. <xref:System.Windows.Controls.ToolTipService> Дополнительные сведения см. в разделе [Общие сведения о всплывающих подсказках](tooltip-overview.md).  
  
- <xref:System.Windows.Controls.ContextMenu>. Если необходимо создать контекстное меню для элемента, используйте <xref:System.Windows.Controls.ContextMenu> элемент управления. Дополнительные сведения см. в разделе [Общие сведения об элементе управления ContextMenu](contextmenu-overview.md).  
  
- <xref:System.Windows.Controls.ComboBox>. Если необходимо создать элемент управления выбора с раскрывающимся списком, который можно отобразить или скрыть, используйте <xref:System.Windows.Controls.ComboBox> элемент управления.  
  
- <xref:System.Windows.Controls.Expander>. Если необходимо создать элемент управления, отображающий заголовок с сворачиваемой областью отображения содержимого, используйте <xref:System.Windows.Controls.Expander> элемент управления. Дополнительные сведения см. в разделе [Общие сведения об элементе управления Expander](expander-overview.md).  
  
<a name="PopupBehaviorandAppearance"></a>   
## <a name="popup-behavior-and-appearance"></a>Внешний вид и поведение контекстного меню  
 <xref:System.Windows.Controls.Primitives.Popup> Элемент управления предоставляет функциональные возможности, позволяющие настраивать его поведение и внешний вид. Например, можно задать поведение открытия и закрытия, анимацию, эффекты непрозрачности и растровых <xref:System.Windows.Controls.Primitives.Popup> эффектов, а также размер и расположение.  
  
<a name="OpenandCloseBehavior"></a>   
### <a name="open-and-close-behavior"></a>Поведение открытия и закрытия  
 Элемент управления отображает его содержимое, <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> если свойство имеет значение `true`. <xref:System.Windows.Controls.Primitives.Popup> По умолчанию <xref:System.Windows.Controls.Primitives.Popup> остается открытым <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> до тех пор, пока свойство `false`не будет установлено в значение. Однако поведение по умолчанию можно изменить, задав <xref:System.Windows.Controls.Primitives.Popup.StaysOpen%2A> для `false`свойства значение. Если задать для `false`этого свойства значение <xref:System.Windows.Controls.Primitives.Popup> , окно содержимого будет иметь захват мыши. Теряется захват мыши, и окно закрывается при возникновении события мыши <xref:System.Windows.Controls.Primitives.Popup> вне окна. <xref:System.Windows.Controls.Primitives.Popup>  
  
 События и <xref:System.Windows.Controls.Primitives.Popup.Closed>вызываются , когда окно содержимогооткрытоилизакрыто.<xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Primitives.Popup.Opened>  
  
<a name="Animation"></a>   
### <a name="animation"></a>Анимация  
 Этот <xref:System.Windows.Controls.Primitives.Popup> элемент управления имеет встроенную поддержку анимаций, которые обычно связаны с такими поведениями, как выцветание и скольжение. Эти анимации можно включить, задав <xref:System.Windows.Controls.Primitives.Popup.PopupAnimation%2A> <xref:System.Windows.Controls.Primitives.PopupAnimation> для свойства значение перечисления. Для <xref:System.Windows.Controls.Primitives.Popup> правильной работы анимации необходимо <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> задать для `true`свойства значение.  
  
 Можно также применить анимацию, <xref:System.Windows.Media.Animation.Storyboard> например, <xref:System.Windows.Controls.Primitives.Popup> к элементу управления.  
  
<a name="OpacityandBitmapEffects"></a>   
### <a name="opacity-and-bitmap-effects"></a>Прозрачность и эффекты для точечных рисунков  
 <xref:System.Windows.UIElement.Opacity%2A> Свойство<xref:System.Windows.Controls.Primitives.Popup> элемента управления не влияет на его содержимое. По умолчанию <xref:System.Windows.Controls.Primitives.Popup> окно содержимого является непрозрачным. Чтобы создать прозрачный <xref:System.Windows.Controls.Primitives.Popup>объект, <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> присвойте свойству `true`значение.  
  
 Содержимое <xref:System.Windows.Controls.Primitives.Popup> объекта не наследует эффекты точечного рисунка, такие как <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>, которые непосредственно задаются для <xref:System.Windows.Controls.Primitives.Popup> элемента управления или любого другого элемента в родительском окне. Чтобы эффекты точечных рисунков отображались на содержимом <xref:System.Windows.Controls.Primitives.Popup>, необходимо задать эффект точечного рисунка непосредственно для его содержимого. Например, если дочерний элемент a <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.StackPanel>является, установите эффекты точечного рисунка на <xref:System.Windows.Controls.StackPanel>.  
  
<a name="PopupSize"></a>   
### <a name="popup-size"></a>Размер контекстного меню  
 По умолчанию <xref:System.Windows.Controls.Primitives.Popup> размер автоматически изменяется в соответствии с содержимым. При возникновении автоматического изменения размера некоторые эффекты растрового изображения могут быть скрыты, так как размер области экрана по умолчанию, <xref:System.Windows.Controls.Primitives.Popup> определенный для содержимого, не предоставляет достаточно места для отображения эффектов растрового изображения.  
  
 <xref:System.Windows.Controls.Primitives.Popup>содержимое также может быть скрыто при задании <xref:System.Windows.UIElement.RenderTransform%2A> для содержимого. В этом случае часть содержимого может быть скрыта, если содержимое преобразованного <xref:System.Windows.Controls.Primitives.Popup> элемента выходит за пределы области исходного. <xref:System.Windows.Controls.Primitives.Popup> Если для растрового изображения или преобразования требуется больше пространства, можно определить поле вокруг <xref:System.Windows.Controls.Primitives.Popup> содержимого, чтобы предоставить больше областей для элемента управления.  
  
<a name="DefiningPopupPosition"></a>   
## <a name="defining-the-popup-position"></a>Определение положения контекстного меню  
 Всплывающее окно можно разместить <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, задав свойства <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>,, и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffsetProperty> . Дополнительные сведения см. в разделе [Поведение при размещении контекстного меню](popup-placement-behavior.md). Когда <xref:System.Windows.Controls.Primitives.Popup> отображается на экране, он не перемещает себя при перемещении его родительского элемента.  
  
<a name="CustomizingPopupPlacement"></a>   
### <a name="customizing-popup-placement"></a>Настройка размещения контекстного меню  
 Размещение <xref:System.Windows.Controls.Primitives.Popup> элемента управления можно настроить, указав набор координат, относительный относительно того, <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> где <xref:System.Windows.Controls.Primitives.Popup> должен отображаться элемент.  
  
 Чтобы настроить размещение, присвойте <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>свойству значение. Затем определите <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> делегат, возвращающий набор возможных точек размещения и основных осей (в порядке предпочтения) <xref:System.Windows.Controls.Primitives.Popup>для. Точка, на которой показана самая крупная <xref:System.Windows.Controls.Primitives.Popup> часть элемента, выбирается автоматически. См. пример в разделе [Указание пользовательского расположения контекстного меню](how-to-specify-a-custom-popup-position.md).  
  
<a name="PopupandtheVisualTree"></a>   
## <a name="popup-and-the-visual-tree"></a>Контекстное меню и визуальное дерево  
 Элемент управления не имеет собственного визуального дерева; вместо этого он возвращает размер 0 (нуль) <xref:System.Windows.Controls.Primitives.Popup.MeasureOverride%2A> при вызове метода для <xref:System.Windows.Controls.Primitives.Popup>. <xref:System.Windows.Controls.Primitives.Popup> Однако если <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> <xref:System.Windows.Controls.Primitives.Popup> для свойствазаданозначение,тосоздаетсяновоеокнососвоимсобственнымвизуальнымдеревом.`true` Новое окно содержит <xref:System.Windows.Controls.Primitives.Popup.Child%2A> <xref:System.Windows.Controls.Primitives.Popup>содержимое. Ширина и высота нового окна не могут превышать 75 процентов от ширины или высоты экрана.  
  
 Элемент управления хранит ссылку на его <xref:System.Windows.Controls.Primitives.Popup.Child%2A> содержимое как логический дочерний объект. <xref:System.Windows.Controls.Primitives.Popup> При создании нового окна содержимое <xref:System.Windows.Controls.Primitives.Popup> становится визуальным дочерним элементом окна и остается логическим <xref:System.Windows.Controls.Primitives.Popup>дочерним элементом. И наоборот, <xref:System.Windows.Controls.Primitives.Popup> остается логическим родителем своего <xref:System.Windows.Controls.Primitives.Popup.Child%2A> содержимого.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.Primitives.Popup>
- <xref:System.Windows.Controls.Primitives.PopupPrimaryAxis>
- <xref:System.Windows.Controls.Primitives.PlacementMode>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [Разделы практического руководства](popup-how-to-topics.md)
- [Разделы практического руководства](tooltip-how-to-topics.md)
