---
title: Отображение более одного месяца в элементе управления MonthCalendar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- calendars [Windows Forms], formatting display
- examples [Windows Forms], calendar controls
- calendars [Windows Forms], multiple months
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d197caa2-38a5-4cb4-acc3-562130c2ace3
ms.openlocfilehash: 5d3925bc19ddcd67742f0ab8b5b2e45530820f38
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745896"
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a>Практическое руководство. Отображение более чем одного месяца в элементе управления MonthCalendar в Windows Forms
Элемент управления <xref:System.Windows.Forms.MonthCalendar> Windows Forms может отображать до 12 месяцев за раз. По умолчанию элемент управления отображает только один месяц, но можно указать, сколько месяцев отображается и как они упорядочены внутри элемента управления. При изменении размеров календаря размер элемента управления изменяется, поэтому убедитесь, что в форме достаточно места для новых измерений.  
  
### <a name="to-display-multiple-months"></a>Отображение нескольких месяцев  
  
- Задайте для свойства <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> число месяцев, отображаемых горизонтально и вертикально.  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a>См. также раздел

- [Элемент управления MonthCalendar](monthcalendar-control-windows-forms.md)
- [Практическое руководство. Выбор диапазона дат в элементе управления MonthCalendar в Windows Forms](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Практическое руководство. Изменение внешнего вида элемента управления MonthCalendar в Windows Forms](how-to-change-monthcalendar-control-appearance.md)
