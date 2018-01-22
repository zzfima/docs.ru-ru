---
title: "Общие сведения об элементах управления HScrollBar и VScrollBar (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8fbdb3778959d1691200cde49e485d8a63c6e645
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a>Общие сведения об элементах управления HScrollBar и VScrollBar (Windows Forms)
Windows Forms <xref:System.Windows.Forms.ScrollBar> элементы управления используются для обеспечения удобного просмотра длинных списков элементов или данные большого объема с либо горизонтальной или вертикальной прокрутки окна приложения или элемента управления. Полосы прокрутки — это распространенный элемент интерфейса Windows, поэтому <xref:System.Windows.Forms.ScrollBar> управления часто используется с элементами управления, которые не являются производными от <xref:System.Windows.Forms.ScrollableControl> класса. Аналогично, многие разработчики выберите для включения <xref:System.Windows.Forms.ScrollBar> управления своих собственных пользовательских элементов управления.  
  
 <xref:System.Windows.Forms.HScrollBar> (Горизонтально) и <xref:System.Windows.Forms.VScrollBar> (по вертикали) элементы управления работают независимо от других элементов управления и имеют свой собственный набор событий, свойств и методов. <xref:System.Windows.Forms.ScrollBar>элементы управления не совпадает с встроенными полосами прокрутки, вложенные в текстовые поля, списки, поля со списком или MDI-форм ( <xref:System.Windows.Forms.TextBox> управления имеет <xref:System.Windows.Forms.TextBox.ScrollBars%2A> свойство для отображения или скрытия полос прокрутки, прикрепленных к элементу управления).  
  
 <xref:System.Windows.Forms.ScrollBar> Элементы управления используют <xref:System.Windows.Forms.ScrollBar.Scroll> событий для отслеживания перемещения ползунка (иногда называется бегунком) по полосе прокрутки. С помощью <xref:System.Windows.Forms.ScrollBar.Scroll> событие предоставляет доступ к значению панель прокрутки при его перетаскивании.  
  
## <a name="value-property"></a>Свойство Value  
 <xref:System.Windows.Forms.ScrollBar.Value%2A> (Который по умолчанию равно 0) задано `integer` значение, соответствующее положение ползунка полосы прокрутки. Когда положения ползунка минимальное значение, он перемещает позицию слева (на горизонтальной полосе прокрутки) или верхней позиции (на вертикальной полосе прокрутки). Когда поле находится в максимальное значение, ползунка справа или нижнюю позицию. Аналогично значение в середине диапазона между минимальным и максимальным пределами помещает переднего края ползунка в середине полосы прокрутки.  
  
 Помимо использования щелчки мышью для изменения значения панель прокрутки, пользователь также можно перетаскивать полосы прокрутки в любой момент на полосе. Результирующее значение зависит от положения ползунка, но он всегда находится в диапазоне от <xref:System.Windows.Forms.ScrollBar.Minimum%2A> для <xref:System.Windows.Forms.ScrollBar.Maximum%2A> свойства, установленные пользователем.  
  
## <a name="largechange-and-smallchange-properties"></a>LargeChange и свойства SmallChange  
 Когда пользователь нажимает клавишу PAGE UP или PAGE DOWN или щелкает в полосы прокрутки с обеих сторон ползунка, <xref:System.Windows.Forms.ScrollBar.Value%2A> изменяется в соответствии со значением <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> свойство.  
  
 Когда пользователь щелкает стрелку ключей или нажимает одну из кнопок полосы прокрутки, <xref:System.Windows.Forms.ScrollBar.Value%2A> изменяется в соответствии со значением <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> свойство.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.HScrollBar>  
 <xref:System.Windows.Forms.VScrollBar>  
 [Дополнения в Windows Forms для платформы .NET Framework 2.0](http://msdn.microsoft.com/library/c61a923d-3d6a-4c8c-820c-e94c83f3f9a8)  
 [Элементы управления для использования в Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
