---
title: Отображение даты в пользовательском формате с помощью элемента управления DateTimePicker
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DateTimePicker control [Windows Forms], display styles
- examples [Windows Forms], DateTimePicker control
- dates [Windows Forms], displaying in DateTimePicker control
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
ms.openlocfilehash: a27dbe737b81af86c0ac50b791bcd87bafe05b4f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745934"
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a>Практическое руководство. Отображение даты в пользовательском формате с помощью элемента управления DateTimePicker в Windows Forms
Элемент управления Windows Forms <xref:System.Windows.Forms.DateTimePicker> позволяет гибко форматировать отображение дат и времени в элементе управления. Свойство <xref:System.Windows.Forms.DateTimePicker.Format%2A> позволяет выбрать стандартные форматы, перечисленные в <xref:System.Windows.Forms.DateTimePickerFormat>. Если ни один из этих средств не подходит для ваших целей, можно создать собственный стиль форматирования, используя символы формата, перечисленные в <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.  
  
### <a name="to-display-a-custom-format"></a>Отображение пользовательского формата  
  
1. Установите свойство <xref:System.Windows.Forms.DateTimePicker.Format%2A> в значение `DateTimePickerFormat.Custom`.  
  
2. Задайте для свойства <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> строку формата.  
  
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
  
### <a name="to-add-text-to-the-formatted-value"></a>Добавление текста к отформатированному значению  
  
1. Используйте одинарные кавычки для заключения любого символа, который не является символом формата, например "M", или разделителя, например ":". Например, приведенная ниже строка форматирования отображает текущую дату в формате "сегодня: 05:30:31 пятница марта 02, 2012" в английской (США) культуре.  
  
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
  
     В зависимости от настройки языка и региональных параметров все символы, не заключенные в одинарные кавычки, могут быть изменены. Например, приведенная выше строка форматирования отображает текущую дату в формате "сегодня: 05:30:31 пятница марта 02, 2012" в английской (США) культуре. Обратите внимание, что первое двоеточие заключено в одинарные кавычки, так как оно не должно быть символом-разделителем, как в «чч: мм: СС». В другом языке и региональных параметрах формат может выглядеть как "сегодня: 05.30.31 пятница, 02 марта, 2012".  
  
## <a name="see-also"></a>См. также раздел

- [Элемент управления DateTimePicker](datetimepicker-control-windows-forms.md)
- [Практическое руководство. Отображение и ввод дат с помощью элемента управления DateTimePicker в Windows Forms](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
