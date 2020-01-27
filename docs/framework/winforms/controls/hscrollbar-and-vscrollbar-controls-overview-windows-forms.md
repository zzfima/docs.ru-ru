---
title: Общие сведения об элементах управления HScrollBar и VScrollBar
ms.date: 03/30/2017
f1_keywords:
- HScrollBar
- VScrollBar
helpviewer_keywords:
- ScrollBar control [Windows Forms]
- HScrollBar control [Windows Forms], about HScrollBar
- VScrollBar control [Windows Forms], about VScrollBar control
- ScrollBar control [Windows Forms], about ScrollBar control
- scroll bars [Windows Forms], about scroll bars
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
ms.openlocfilehash: abe0c8da9723f17cb80715454f6ab7297724a21f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728162"
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a>Общие сведения об элементах управления HScrollBar и VScrollBar (Windows Forms)
Windows Forms элементы управления <xref:System.Windows.Forms.ScrollBar> используются для удобного перемещения по длинному списку элементов или большому объему информации путем прокрутки по горизонтали или вертикали в пределах приложения или элемента управления. Полосы прокрутки являются общим элементом интерфейса Windows, поэтому элемент управления <xref:System.Windows.Forms.ScrollBar> часто используется с элементами управления, которые не являются производными от класса <xref:System.Windows.Forms.ScrollableControl>. Аналогичным образом многие разработчики выбирают элемент управления <xref:System.Windows.Forms.ScrollBar> при создании собственных пользовательских элементов управления.  
  
 Элементы управления <xref:System.Windows.Forms.HScrollBar> (горизонтально) и <xref:System.Windows.Forms.VScrollBar> (вертикально) работают независимо от других элементов управления и имеют собственный набор событий, свойств и методов. <xref:System.Windows.Forms.ScrollBar> элементы управления не совпадают со встроенными полосами прокрутки, присоединенными к текстовым полям, спискам, полям со списком или формами MDI (элемент управления <xref:System.Windows.Forms.TextBox> имеет свойство <xref:System.Windows.Forms.TextBox.ScrollBars%2A> для отображения или скрытия полос прокрутки, присоединенных к элементу управления).  
  
 Элементы управления <xref:System.Windows.Forms.ScrollBar> используют событие <xref:System.Windows.Forms.ScrollBar.Scroll> для отслеживания перемещения ползунка прокрутки (иногда называемого бегунком) вдоль полосы прокрутки. Использование события <xref:System.Windows.Forms.ScrollBar.Scroll> предоставляет доступ к значению полосы прокрутки при его перетаскивании.  
  
## <a name="value-property"></a>Свойство Value  
 Свойство <xref:System.Windows.Forms.ScrollBar.Value%2A> (по умолчанию — 0) — это `integer` значение, соответствующее положению ползунка в полосе прокрутки. Если расположение ползунка находится в минимальном значении, оно перемещается в крайнее левое расположение (для горизонтальных полос прокрутки) или в верхнюю точку (для вертикальных полос прокрутки). Если ползунок находится в максимальном значении, поле прокрутки переместится к крайней правой или нижней позиции. Аналогично, значение, расположенное в середине от нижнего и верхнего края диапазона, помещает передний край ползунка в середине полосы прокрутки.  
  
 В дополнение к использованию щелчков мыши для изменения значения полосы прокрутки пользователь может также перетащить ползунок в любую точку на полосе. Результирующее значение зависит от расположения поля прокрутки, но всегда находится в диапазоне <xref:System.Windows.Forms.ScrollBar.Minimum%2A> для <xref:System.Windows.Forms.ScrollBar.Maximum%2A> свойств, заданных пользователем.  
  
## <a name="largechange-and-smallchange-properties"></a>Свойства LargeChange и SmallChange  
 Когда пользователь нажимает на страницу вверх или вниз или щелкает мышью на полосе прокрутки с любой стороны ползунка, свойство <xref:System.Windows.Forms.ScrollBar.Value%2A> изменяется в соответствии со значением, заданным в свойстве <xref:System.Windows.Forms.ScrollBar.LargeChange%2A>.  
  
 Когда пользователь нажимает один из клавиш со стрелками или щелкает одну из кнопок полосы прокрутки, свойство <xref:System.Windows.Forms.ScrollBar.Value%2A> изменяется в соответствии со значением, заданным в свойстве <xref:System.Windows.Forms.ScrollBar.SmallChange%2A>.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.HScrollBar>
- <xref:System.Windows.Forms.VScrollBar>
- [Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)
