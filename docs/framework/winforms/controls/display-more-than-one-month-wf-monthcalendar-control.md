---
title: Как выполнить Отображение более чем одного месяца в элементе управления Windows Forms MonthCalendar
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
ms.openlocfilehash: 164369ab1a94249470b57e546db64be8e17b99bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582036"
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a>Как выполнить Отображение более чем одного месяца в элементе управления Windows Forms MonthCalendar
Windows Forms <xref:System.Windows.Forms.MonthCalendar> элемент управления может отображать до 12 месяцев, за раз. По умолчанию элемент управления отображает только один месяц, но можно указать количество месяцев, отображаются и их размещение в элементе управления. Когда вы изменяете размеры календаря, размер, поэтому убедитесь, что имеется достаточно места в форме для новых измерений.  
  
### <a name="to-display-multiple-months"></a>Чтобы отобразить несколько месяцев  
  
-   Задайте <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> количество месяцев, отображаемых по горизонтали и вертикали.  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a>См. также
- [Элемент управления MonthCalendar](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)
- [Практическое руководство. Выбор диапазона дат в элементе управления Windows Forms MonthCalendar](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Практическое руководство. Изменение внешнего вида управления Windows Forms MonthCalendar](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)
