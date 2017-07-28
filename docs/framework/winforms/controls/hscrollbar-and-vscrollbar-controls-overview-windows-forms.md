---
title: "Общие сведения об элементах управления HScrollBar и VScrollBar (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "HScrollBar"
  - "VScrollBar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "HScrollBar - элемент управления [Windows Forms], сведения об элементе управления HScrollBar"
  - "полосы прокрутки, сведения о полосах прокрутки"
  - "ScrollBar - элемент управления [Windows Forms]"
  - "ScrollBar - элемент управления [Windows Forms], сведения об элементе управления ScrollBar"
  - "VScrollBar - элемент управления [Windows Forms], сведения об элементе управления VScrollBar"
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Общие сведения об элементах управления HScrollBar и VScrollBar (Windows Forms)
Элементы управления форм Windows Forms <xref:System.Windows.Forms.ScrollBar> обеспечивают удобный просмотр длинных списков и больших массивов информации с помощью горизонтальной или вертикальной прокрутки окна приложения или элемента управления.  Полосы прокрутки — это распространенный элемент интерфейса Windows, поэтому элемент управления <xref:System.Windows.Forms.ScrollBar> часто используется вместе с элементами управления, не являющимися производными от класса <xref:System.Windows.Forms.ScrollableControl>.  Многие разработчики включают элемент управления <xref:System.Windows.Forms.ScrollBar> в состав своих собственных пользовательских элементов управления.  
  
 Элементы управления <xref:System.Windows.Forms.HScrollBar> \(горизонтальная прокрутка\) и <xref:System.Windows.Forms.VScrollBar> \(вертикальная прокрутка\) действуют независимо от остальных элементов управления и имеют свой собственный набор событий, свойств и методов.  Элементы управления <xref:System.Windows.Forms.ScrollBar> не следует путать с вложенными полосами прокрутки, используемыми в текстовых полях, полях со списками или MDI\-формах \(у элемента управления <xref:System.Windows.Forms.TextBox> имеется свойство <xref:System.Windows.Forms.TextBox.ScrollBars%2A>, которое позволяет отобразить или скрыть полосы прокрутки, используемые в элементе управления\).  
  
 Элементы управления <xref:System.Windows.Forms.ScrollBar> используют событие <xref:System.Windows.Forms.ScrollBar.Scroll> для контроля за перемещением ползунка \(иногда его называют движком или бегунком\) по полосе прокрутки.  Использование события <xref:System.Windows.Forms.ScrollBar.Scroll> обеспечивает доступ к значению позиции ползунка полосы прокрутки во время его перемещения.  
  
## Значение свойства  
 Свойство <xref:System.Windows.Forms.ScrollBar.Value%2A> \(которое по умолчанию равно нулю\) принимает значения типа `integer`, определяющие местоположение ползунка на полосе прокрутки.  Минимальное значение соответствует крайней левой позиции ползунка \(на горизонтальной полосе прокрутки\) или крайней верхней позиции \(на вертикальной полосе прокрутки\).  Наибольшее значение соответствует крайней правой или крайней нижней позиции ползунка.  Значение в середине диапазона между минимальным и максимальным пределами соответствует положению переднего края ползунка в середине полосы прокрутки.  
  
 Для того чтобы переместить ползунок в любую позицию на полосе прокрутки, можно щелкнуть мышью в этом месте или перетащить туда ползунок.  Значение свойства зависит от положения ползунка, но оно всегда находится в диапазоне между значениями свойств <xref:System.Windows.Forms.ScrollBar.Minimum%2A> и <xref:System.Windows.Forms.ScrollBar.Maximum%2A>, задаваемыми пользователем.  
  
## Свойства LargeChange и SmallChange  
 Когда пользователь нажимает клавиши PAGE UP или PAGE DOWN либо щелкает область линейки с любой стороны от ползунка, свойство <xref:System.Windows.Forms.ScrollBar.Value%2A> изменяется в соответствии со значением свойства <xref:System.Windows.Forms.ScrollBar.LargeChange%2A>.  
  
 Когда пользователь нажимает одну из клавиш со стрелками или щелкает одну из кнопок полосы прокрутки, свойство <xref:System.Windows.Forms.ScrollBar.Value%2A> изменяется в соответствии со значением, установленным в свойстве <xref:System.Windows.Forms.ScrollBar.SmallChange%2A>.  
  
## См. также  
 <xref:System.Windows.Forms.HScrollBar>   
 <xref:System.Windows.Forms.VScrollBar>   
 [Additions to Windows Forms for the .NET Framework 2.0](http://msdn.microsoft.com/ru-ru/c61a923d-3d6a-4c8c-820c-e94c83f3f9a8)   
 [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)