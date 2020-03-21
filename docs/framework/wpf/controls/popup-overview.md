---
title: Общие сведения о контекстном меню
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Popup
- Popup control [WPF], about Popup control
ms.assetid: 774f53ca-bff8-470e-9ce9-3928b4cf3d4c
ms.openlocfilehash: 911130d52744c5ba54750f214829a5d1900e083c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185955"
---
# <a name="popup-overview"></a>Общие сведения о контекстном меню
Элемент <xref:System.Windows.Controls.Primitives.Popup> управления обеспечивает способ отображения содержимого в отдельном окне, которое плавает над текущим окном приложения по отношению к обозначенному элементу или координату экрана. Эта тема вводит <xref:System.Windows.Controls.Primitives.Popup> элемент управления и предоставляет информацию о его использовании.  

<a name="What_Is_a_Popup_"></a>
## <a name="what-is-a-popup"></a>Что такое контекстное меню?  
 Элемент <xref:System.Windows.Controls.Primitives.Popup> управления отображает содержимое в отдельном окне по отношению к элементу или точке на экране. <xref:System.Windows.Controls.Primitives.Popup> Когда объект виден, <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> свойство `true`устанавливается на .  
  
> [!NOTE]
> A <xref:System.Windows.Controls.Primitives.Popup> автоматически не открывается, когда указатель мыши перемещается по родительскому объекту. Если вы <xref:System.Windows.Controls.Primitives.Popup> хотите автоматически открыть, <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> используйте или класс. Дополнительные сведения см. в разделе [Общие сведения о всплывающих подсказках](tooltip-overview.md).  
  
<a name="APopupExample"></a>
## <a name="creating-a-popup"></a>Создание всплывающего окна  
 В следующем примере показано, как определить <xref:System.Windows.Controls.Primitives.Popup> элемент <xref:System.Windows.Controls.Button> элемента элемента элемента элемента элемента управления. Поскольку <xref:System.Windows.Controls.Button> может иметь только один элемент ребенка, <xref:System.Windows.Controls.Button> этот <xref:System.Windows.Controls.Primitives.Popup> пример <xref:System.Windows.Controls.StackPanel>помещает текст для и элементов управления в . Содержимое <xref:System.Windows.Controls.Primitives.Popup> отображается в <xref:System.Windows.Controls.TextBlock> элементе управления, который отображает его текст в отдельном окне, которое плавает над окном приложения рядом с соответствующим <xref:System.Windows.Controls.Button> элементом управления.  
  
 [!code-xaml[PopupSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#1)]  
  
 [!code-xaml[PopupSimple#CreatePopupCodeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#createpopupcodexaml)]  
  
<a name="PopupUses"></a>
## <a name="controls-that-implement-a-popup"></a>Элементы управления, реализующие контекстное меню  
 Вы можете <xref:System.Windows.Controls.Primitives.Popup> построить элементы управления в другие элементы управления. Следующие элементы <xref:System.Windows.Controls.Primitives.Popup> управления реализуют элемент управления для конкретных целей:  
  
- <xref:System.Windows.Controls.ToolTip>. Если вы хотите создать набор инструментов для <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> элемента, используйте и классы. Дополнительные сведения см. в разделе [Общие сведения о всплывающих подсказках](tooltip-overview.md).  
  
- <xref:System.Windows.Controls.ContextMenu>. Если требуется создать контекстное меню для <xref:System.Windows.Controls.ContextMenu> элемента, используйте элемент управления. Дополнительные сведения см. в разделе [Общие сведения об элементе управления ContextMenu](contextmenu-overview.md).  
  
- <xref:System.Windows.Controls.ComboBox>. Если вы хотите создать элемент управления выбора, который имеет окно списка выпадающих, которое может быть отображено или скрыто, используйте <xref:System.Windows.Controls.ComboBox> элемент управления.  
  
- <xref:System.Windows.Controls.Expander>. Если требуется создать элемент управления, отображая заголовок с складной <xref:System.Windows.Controls.Expander> областью, отображающая содержимое, используйте элемент управления. Дополнительные сведения см. в разделе [Общие сведения об элементе управления Expander](expander-overview.md).  
  
<a name="PopupBehaviorandAppearance"></a>
## <a name="popup-behavior-and-appearance"></a>Внешний вид и поведение контекстного меню  
 Элемент <xref:System.Windows.Controls.Primitives.Popup> управления обеспечивает функциональность, которая позволяет настроить его поведение и внешний вид. Например, можно установить открытое и близкое поведение, анимацию, эффекты непрозрачности и биткарты, <xref:System.Windows.Controls.Primitives.Popup> а также размер и положение.  
  
<a name="OpenandCloseBehavior"></a>
### <a name="open-and-close-behavior"></a>Поведение открытия и закрытия  
 Элемент <xref:System.Windows.Controls.Primitives.Popup> управления отображает его <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> содержимое при `true`установке свойства. По умолчанию остается <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> открытым до `false`тех пор, пока свойство не будет установлено. Однако можно изменить поведение по <xref:System.Windows.Controls.Primitives.Popup.StaysOpen%2A> умолчанию, установив свойство на `false`. При настройке этого `false`свойства <xref:System.Windows.Controls.Primitives.Popup> в окне содержимого есть захват мыши. Потеря <xref:System.Windows.Controls.Primitives.Popup> мышь захвата и окно закрывается, когда <xref:System.Windows.Controls.Primitives.Popup> событие мыши происходит за окном.  
  
 События <xref:System.Windows.Controls.Primitives.Popup.Opened> <xref:System.Windows.Controls.Primitives.Popup.Closed> и события поднимаются, когда окно содержимого <xref:System.Windows.Controls.Primitives.Popup> открыто или закрыто.  
  
<a name="Animation"></a>
### <a name="animation"></a>Анимация  
 Элемент <xref:System.Windows.Controls.Primitives.Popup> управления имеет встроенную поддержку анимаций, которые обычно связаны с поведением, таким как fade-in и slide-in. Вы можете включить эти анимации, установив свойство <xref:System.Windows.Controls.Primitives.Popup.PopupAnimation%2A> к значению <xref:System.Windows.Controls.Primitives.PopupAnimation> перечисления. Чтобы <xref:System.Windows.Controls.Primitives.Popup> анимация работала правильно, необходимо <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> настроить `true`свойство.  
  
 Вы также можете применить <xref:System.Windows.Media.Animation.Storyboard> анимацию, как к управлению. <xref:System.Windows.Controls.Primitives.Popup>  
  
<a name="OpacityandBitmapEffects"></a>
### <a name="opacity-and-bitmap-effects"></a>Прозрачность и эффекты для точечных рисунков  
 Свойство <xref:System.Windows.UIElement.Opacity%2A> <xref:System.Windows.Controls.Primitives.Popup> для управления не влияет на его содержание. По умолчанию <xref:System.Windows.Controls.Primitives.Popup> окно содержимого непрозрачно. Чтобы создать <xref:System.Windows.Controls.Primitives.Popup>прозрачный, <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> установите свойство. `true`  
  
 Содержимое <xref:System.Windows.Controls.Primitives.Popup> не наследует эффекты bitmap, такие как, <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> <xref:System.Windows.Controls.Primitives.Popup> что вы непосредственно установить на элемент управления или на любой другой элемент в родительском окне. Для того, чтобы эффекты bitmap отображались на <xref:System.Windows.Controls.Primitives.Popup>содержимом, необходимо установить эффект bitmap непосредственно на его содержание. Например, если ребенок <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.StackPanel>является, установите эффект bitmap <xref:System.Windows.Controls.StackPanel>на .  
  
<a name="PopupSize"></a>
### <a name="popup-size"></a>Размер контекстного меню  
 По умолчанию <xref:System.Windows.Controls.Primitives.Popup> a автоматически размерируется с его содержанием. При автоматическом размере эффекты могут быть скрыты, поскольку размер экрана по <xref:System.Windows.Controls.Primitives.Popup> умолчанию, который определяется для содержимого, не обеспечивает достаточно места для отображения эффектов биткарты.  
  
 <xref:System.Windows.Controls.Primitives.Popup>содержимое также может быть скрыто <xref:System.Windows.UIElement.RenderTransform%2A> при установке содержимого. В этом сценарии некоторое содержимое может <xref:System.Windows.Controls.Primitives.Popup> быть скрыто, если содержимое преобразованного выходит за пределы области оригинала. <xref:System.Windows.Controls.Primitives.Popup> Если эффект биткарты или преобразование требует больше места, можно определить маржу вокруг содержимого, <xref:System.Windows.Controls.Primitives.Popup> чтобы обеспечить больше площади для управления.  
  
<a name="DefiningPopupPosition"></a>
## <a name="defining-the-popup-position"></a>Определение положения контекстного меню  
 Вы можете позиционировать всплывающее <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>окно, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> <xref:System.Windows.Controls.Primitives.Popup.VerticalOffsetProperty> <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>установив, и свойства. Дополнительные сведения см. в разделе [Поведение при размещении контекстного меню](popup-placement-behavior.md). Когда <xref:System.Windows.Controls.Primitives.Popup> отображается на экране, он не перепозиционируется, если его родитель перепозиционируется.  
  
<a name="CustomizingPopupPlacement"></a>
### <a name="customizing-popup-placement"></a>Настройка размещения всплывающего окна  
 Вы можете настроить размещение <xref:System.Windows.Controls.Primitives.Popup> элемента управления, указав набор координат, которые относительно того, <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> где вы хотите <xref:System.Windows.Controls.Primitives.Popup> отойти.  
  
 Чтобы настроить размещение, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> установите <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>свойство на . Затем определите делегата, <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> который возвращает набор возможных точек размещения и <xref:System.Windows.Controls.Primitives.Popup>основных осей (в порядке предпочтения) для . Точка, отображаемый самой большой частью выбранной <xref:System.Windows.Controls.Primitives.Popup> части. См. пример в разделе [Указание пользовательского расположения всплывающего окна](how-to-specify-a-custom-popup-position.md).  
  
<a name="PopupandtheVisualTree"></a>
## <a name="popup-and-the-visual-tree"></a>Контекстное меню и визуальное дерево  
 Элемент <xref:System.Windows.Controls.Primitives.Popup> управления не имеет собственного визуального дерева; вместо этого он возвращает размер 0 <xref:System.Windows.Controls.Primitives.Popup.MeasureOverride%2A> (ноль), когда метод для <xref:System.Windows.Controls.Primitives.Popup> называется. Однако, когда <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> вы <xref:System.Windows.Controls.Primitives.Popup> устанавливаете свойство, чтобы, `true`новое окно с собственным визуальным деревом создается. Новое окно содержит <xref:System.Windows.Controls.Primitives.Popup.Child%2A> содержание <xref:System.Windows.Controls.Primitives.Popup>. Ширина и высота нового окна не могут превышать 75 процентов от ширины или высоты экрана.  
  
 Элемент <xref:System.Windows.Controls.Primitives.Popup> управления сохраняет ссылку <xref:System.Windows.Controls.Primitives.Popup.Child%2A> на его содержимое в качестве логического ребенка. Когда создается новое окно, <xref:System.Windows.Controls.Primitives.Popup> содержание становится визуальным ребенком окна и <xref:System.Windows.Controls.Primitives.Popup>остается логичным ребенком . И наоборот, <xref:System.Windows.Controls.Primitives.Popup> остается <xref:System.Windows.Controls.Primitives.Popup.Child%2A> логическим родителем его содержания.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.Primitives.Popup>
- <xref:System.Windows.Controls.Primitives.PopupPrimaryAxis>
- <xref:System.Windows.Controls.Primitives.PlacementMode>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [Как-к темам](popup-how-to-topics.md)
- [Как-к темам](tooltip-how-to-topics.md)
