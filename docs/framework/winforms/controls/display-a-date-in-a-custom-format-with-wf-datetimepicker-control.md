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
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="63f16-102">Практическое руководство. Отображение даты в пользовательском формате с помощью элемента управления DateTimePicker в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="63f16-102">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="63f16-103">Элемент управления Windows Forms <xref:System.Windows.Forms.DateTimePicker> позволяет гибко форматировать отображение дат и времени в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="63f16-103">The Windows Forms <xref:System.Windows.Forms.DateTimePicker> control gives you flexibility in formatting the display of dates and times in the control.</span></span> <span data-ttu-id="63f16-104">Свойство <xref:System.Windows.Forms.DateTimePicker.Format%2A> позволяет выбрать стандартные форматы, перечисленные в <xref:System.Windows.Forms.DateTimePickerFormat>.</span><span class="sxs-lookup"><span data-stu-id="63f16-104">The <xref:System.Windows.Forms.DateTimePicker.Format%2A> property allows you to select from predefined formats, listed in the <xref:System.Windows.Forms.DateTimePickerFormat>.</span></span> <span data-ttu-id="63f16-105">Если ни один из этих средств не подходит для ваших целей, можно создать собственный стиль форматирования, используя символы формата, перечисленные в <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span><span class="sxs-lookup"><span data-stu-id="63f16-105">If none of these is adequate for your purposes, you can create your own format style using format characters listed in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span></span>  
  
### <a name="to-display-a-custom-format"></a><span data-ttu-id="63f16-106">Отображение пользовательского формата</span><span class="sxs-lookup"><span data-stu-id="63f16-106">To display a custom format</span></span>  
  
1. <span data-ttu-id="63f16-107">Задайте для свойства <xref:System.Windows.Forms.DateTimePicker.Format%2A> значение `DateTimePickerFormat.Custom`.</span><span class="sxs-lookup"><span data-stu-id="63f16-107">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to `DateTimePickerFormat.Custom`.</span></span>  
  
2. <span data-ttu-id="63f16-108">Задайте для свойства <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> строку формата.</span><span class="sxs-lookup"><span data-stu-id="63f16-108">Set the <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> property to a format string.</span></span>  
  
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
  
### <a name="to-add-text-to-the-formatted-value"></a><span data-ttu-id="63f16-109">Добавление текста к отформатированному значению</span><span class="sxs-lookup"><span data-stu-id="63f16-109">To add text to the formatted value</span></span>  
  
1. <span data-ttu-id="63f16-110">Используйте одинарные кавычки для заключения любого символа, который не является символом формата, например "M", или разделителя, например ":".</span><span class="sxs-lookup"><span data-stu-id="63f16-110">Use single quotation marks to enclose any character that is not a format character like "M" or a delimiter like ":".</span></span> <span data-ttu-id="63f16-111">Например, приведенная ниже строка форматирования отображает текущую дату в формате "сегодня: 05:30:31 пятница марта 02, 2012" в английской (США) культуре.</span><span class="sxs-lookup"><span data-stu-id="63f16-111">For example, the format string below displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span>  
  
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
  
     <span data-ttu-id="63f16-112">В зависимости от настройки языка и региональных параметров все символы, не заключенные в одинарные кавычки, могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="63f16-112">Depending on the culture setting, any characters not enclosed in single quotation marks may be changed.</span></span> <span data-ttu-id="63f16-113">Например, приведенная выше строка форматирования отображает текущую дату в формате "сегодня: 05:30:31 пятница марта 02, 2012" в английской (США) культуре.</span><span class="sxs-lookup"><span data-stu-id="63f16-113">For example, the format string above displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span> <span data-ttu-id="63f16-114">Обратите внимание, что первое двоеточие заключено в одинарные кавычки, так как оно не должно быть символом-разделителем, как в «чч: мм: СС».</span><span class="sxs-lookup"><span data-stu-id="63f16-114">Note that the first colon is enclosed in single quotation marks, because it is not intended to be a delimiting character as it is in "hh:mm:ss".</span></span> <span data-ttu-id="63f16-115">В другом языке и региональных параметрах формат может выглядеть как "сегодня: 05.30.31 пятница, 02 марта, 2012".</span><span class="sxs-lookup"><span data-stu-id="63f16-115">In another culture, the format might appear as "Today is: 05.30.31 Friday March 02, 2012".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63f16-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="63f16-116">See also</span></span>

- [<span data-ttu-id="63f16-117">Элемент управления DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="63f16-117">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
- [<span data-ttu-id="63f16-118">Практическое руководство. Отображение и ввод дат с помощью элемента управления DateTimePicker в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="63f16-118">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
