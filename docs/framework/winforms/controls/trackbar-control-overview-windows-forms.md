---
title: Общие сведения об элементе управления TrackBar
ms.date: 03/30/2017
f1_keywords:
- TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
ms.openlocfilehash: 6901405100df4633c84850757f55b756bc9a0199
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741466"
---
# <a name="trackbar-control-overview-windows-forms"></a>Общие сведения об элементе управления TrackBar (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.TrackBar> (также иногда называемый элементом управления "ползунок") используется для навигации по большому объему информации или для визуальной настройки числового параметра. Элемент управления <xref:System.Windows.Forms.TrackBar> состоит из двух частей: бегунка, также называемого ползунком, и делений. Бегунок — это часть, которую можно изменить. Его расположение соответствует свойству <xref:System.Windows.Forms.TrackBar.Value%2A>. Деления — это визуальные индикаторы с регулярным интервалом. Линейка перемещается с указанным шагом приращения и может быть выравниваться по горизонтали или по вертикали. Например, полоса прокрутки может использоваться для управления скоростью мерцания курсора или скоростью мыши для системы.  
  
## <a name="key-properties"></a>Ключевые свойства  
 Ключевыми свойствами элемента управления <xref:System.Windows.Forms.TrackBar> являются <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>и <xref:System.Windows.Forms.TrackBar.Maximum%2A>. <xref:System.Windows.Forms.TrackBar.TickFrequency%2A> — интервалы тактов. <xref:System.Windows.Forms.TrackBar.Minimum%2A> и <xref:System.Windows.Forms.TrackBar.Maximum%2A> — это наименьшие и максимальные значения, которые могут быть представлены на полосе прокрутки.  
  
 Два других важных свойства — <xref:System.Windows.Forms.TrackBar.SmallChange%2A> и <xref:System.Windows.Forms.TrackBar.LargeChange%2A>. Значение свойства <xref:System.Windows.Forms.TrackBar.SmallChange%2A> — число позиций, на которое перемещается бегунок в ответ на нажатие клавиши со стрелкой влево или вправо. Значение свойства <xref:System.Windows.Forms.TrackBar.LargeChange%2A> — число позиций, на которое перемещается бегунок в ответ на нажатие клавиши PAGE UP или PAGE DOWN или в ответ на щелчок мыши на полосе прокрутки с любой стороны бегунка.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.TrackBar>
- [Элемент управления TrackBar](trackbar-control-windows-forms.md)
