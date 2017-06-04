---
title: "Практическое руководство. Отображение определенных дней полужирным шрифтом в элементе управления MonthCalendar в Windows Forms | Microsoft Docs"
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
  - "календари, отображение дат полужирным шрифтом"
  - "примеры [Windows Forms], Calendar - элементы управления"
  - "событие GetDayBold"
  - "MonthCalendar - элемент управления [Windows Forms], даты, отображаемые полужирным шрифтом"
ms.assetid: 8b20db5b-8118-4825-90e8-2c45c186ac7d
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Отображение определенных дней полужирным шрифтом в элементе управления MonthCalendar в Windows Forms
Элемент управления Windows Forms <xref:System.Windows.Forms.MonthCalendar> позволяет отображать дни полужирным шрифтом, причем или в качестве отдельных дат, или на периодической основе.  Это можно сделать, чтобы особо выделить определенные даты, например праздники и выходные.  
  
 Эта возможность реализуется с помощью трех свойств.  Свойство <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> содержит отдельные даты.  Свойство <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> включает даты, которые отображаются полужирным шрифтом каждый год.  Свойство <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> включает даты, которые отображаются полужирным шрифтом каждый месяц.  Каждое из этих свойств содержит массив объектов <xref:System.DateTime>.  Чтобы добавить даты в один из этих списков или удалить их оттуда, необходимо добавить или удалить объект <xref:System.DateTime>.  
  
### Отображение даты полужирным шрифтом  
  
1.  Создайте объекты <xref:System.DateTime>.  
  
    ```vb  
    Dim myVacation1 As Date = New DateTime(2001, 6, 10)  
    Dim myVacation2 As Date = New DateTime(2001, 6, 17)  
  
    ```  
  
    ```csharp  
    DateTime myVacation1 = new DateTime(2001, 6, 10);  
    DateTime myVacation2 = new DateTime(2001, 6, 17);  
  
    ```  
  
    ```cpp  
    DateTime myVacation1 = DateTime(2001, 6, 10);  
    DateTime myVacation2 = DateTime(2001, 6, 17);  
    ```  
  
2.  Выделите отдельную дату полужирным шрифтом, вызвав метод <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A> или <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> элемента управления <xref:System.Windows.Forms.MonthCalendar>.  
  
    ```vb  
    MonthCalendar1.AddBoldedDate(myVacation1)  
    MonthCalendar1.AddBoldedDate(myVacation2)  
  
    ```  
  
    ```csharp  
    monthCalendar1.AddBoldedDate(myVacation1);  
    monthCalendar1.AddBoldedDate(myVacation2);  
  
    ```  
  
    ```cpp  
    monthCalendar1->AddBoldedDate(myVacation1);  
    monthCalendar1->AddBoldedDate(myVacation2);  
    ```  
  
     —либо—  
  
     Выделите полужирным шрифтом сразу несколько дат, создав массив объектов <xref:System.DateTime> и присвоив его одному из этих свойств.  
  
    ```vb  
    Dim VacationDates As DateTime() = {myVacation1, myVacation2}  
    MonthCalendar1.BoldedDates = VacationDates  
  
    ```  
  
    ```csharp  
    DateTime[] VacationDates = {myVacation1, myVacation2};  
    monthCalendar1.BoldedDates = VacationDates;  
  
    ```  
  
    ```cpp  
    Array<DateTime>^ VacationDates = {myVacation1, myVacation2};  
    monthCalendar1->BoldedDates = VacationDates;  
    ```  
  
### Отображение даты обычным шрифтом  
  
1.  Отмените выделение полужирным шрифтом отдельной даты и отобразите ее обычным шрифтом, вызвав метод <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A> или <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A>.  
  
    ```vb  
    MonthCalendar1.RemoveBoldedDate(myVacation1)  
    MonthCalendar1.RemoveBoldedDate(myVacation2)  
  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveBoldedDate(myVacation1);  
    monthCalendar1.RemoveBoldedDate(myVacation2);  
  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveBoldedDate(myVacation1);  
    monthCalendar1->RemoveBoldedDate(myVacation2);  
    ```  
  
     —либо—  
  
     Удалите все выделенные полужирным шрифтом даты из одного из трех списков, вызвав метод <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A> или <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A>.  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2.  Обновите внешний вид шрифта, вызвав метод <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A>.  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## См. также  
 [Элемент управления MonthCalendar](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)   
 [Практическое руководство. Выбор диапазона дат в элементе управления MonthCalendar в Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)   
 [Практическое руководство. Изменение внешнего вида элемента управления MonthCalendar в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)   
 [Практическое руководство. Отображение более чем одного месяца в элементе управления MonthCalendar в Windows Forms](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)