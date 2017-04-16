---
title: "Практическое руководство. Отображение даты в пользовательском формате с помощью элемента управления DateTimePicker в Windows Forms | Microsoft Docs"
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
  - "даты, отображение в элементе управления DateTimePicker"
  - "DateTimePicker - элемент управления [Windows Forms], стиль отображения"
  - "примеры [Windows Forms], DateTimePicker - элемент управления"
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Отображение даты в пользовательском формате с помощью элемента управления DateTimePicker в Windows Forms
Элемент управления Windows Forms <xref:System.Windows.Forms.DateTimePicker> обеспечивает гибкие возможности форматирования отображаемых в этом элементе управления дат и времени.  Свойство <xref:System.Windows.Forms.DateTimePicker.Format%2A> позволяет выбрать готовые форматы, перечисленные в <xref:System.Windows.Forms.DateTimePickerFormat>.  Если ни один из них не подходит для данных целей, имеется возможность создания собственного стиля формата, при помощи знаков формата, перечисленных в разделе <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.  
  
### Чтобы отобразить пользовательский формат  
  
1.  Установите для свойства <xref:System.Windows.Forms.DateTimePicker.Format%2A> значение `DateTimePickerFormat.Custom`.  
  
2.  Свойству <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> присвойте строковое значение формата.  
  
    ```vb  
    DateTimePicker1.Format = DateTimePickerFormat.Custom  
    ' Display the date as "Mon 27 Feb 2012".  
    DateTimePicker1.CustomFormat = "ddd dd MMM yyyy"  
  
    ```  
  
    ```csharp  
    dateTimePicker1.Format = DateTimePickerFormat.Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1.CustomFormat = "ddd dd MMM yyyy";  
  
    ```  
  
    ```cpp  
    dateTimePicker1->Format = DateTimePickerFormat::Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1->CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
### Добавление текста к форматированному значению  
  
1.  Для заключения знаков, которые не являются знаками формата, например "M", или разделителями, например, ":", используйте кавычки.  Например, данная форматирующая строка отображает текущую дату для английского языка \(США\) в формате "Today is: 05:30:31 Friday March 02, 2012".  
  
    ```vb  
    DateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy"  
  
    ```  
  
    ```csharp  
    dateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
  
    ```  
  
    ```cpp  
    dateTimePicker1->CustomFormat =  
       "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
     В зависимости от настройки языка и региональных параметров имеется возможность изменения любого знака, не заключенного в одинарные кавычки.  Например, данная форматирующая строка отображает текущую дату для английского языка \(США\) в формате "Today is: 05:30:31 Friday March 02, 2012".  Обратите внимание, что первое двоеточие заключено в одинарные кавычки, поскольку оно не используется в качестве разделителя, как в случае "hh:mm:ss".  При другой настройке языка и региональных параметров формат может быть следующим "Today is: 05.30.31 Friday March 02, 2012".  
  
## См. также  
 [Элемент управления DateTimePicker](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)   
 [Практическое руководство. Отображение и ввод дат с помощью элемента управления DateTimePicker в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)