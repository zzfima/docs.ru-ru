---
title: "Практическое руководство. Отображение более чем одного месяца в элементе управления MonthCalendar в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "календари, форматирование изображения"
  - "календари, несколько месяцев"
  - "примеры [Windows Forms], Calendar - элементы управления"
  - "MonthCalendar - элемент управления [Windows Forms], форматирование изображения"
ms.assetid: d197caa2-38a5-4cb4-acc3-562130c2ace3
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Отображение более чем одного месяца в элементе управления MonthCalendar в Windows Forms
Элемент управления Windows Forms <xref:System.Windows.Forms.MonthCalendar> позволяет отображать на экране одновременно до 12 месяцев.  По умолчанию в этом элементе управления отображается только один месяц, однако имеется возможность указать количество месяцев, которые будут отображаться на экране, и их размещение в данном элементе управления.  Чтобы обеспечить достаточное количество места в форме для новой размерности, при изменении диапазона календаря изменяются размеры элемента управления.  
  
### Чтобы отобразить несколько месяцев  
  
-   Задайте для свойства <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> значение, равное числу месяцев, отображаемых по горизонтали и вертикали.  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## См. также  
 [Элемент управления MonthCalendar](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)   
 [Практическое руководство. Выбор диапазона дат в элементе управления MonthCalendar в Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)   
 [Практическое руководство. Изменение внешнего вида элемента управления MonthCalendar в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)