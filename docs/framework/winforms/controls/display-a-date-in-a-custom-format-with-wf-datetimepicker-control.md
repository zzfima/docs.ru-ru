---
title: Практическое руководство. Отображение даты в пользовательском формате с элемента управления DateTimePicker в Windows Forms
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
ms.openlocfilehash: c201455acaa9bde521afd623424d0cfc403b1bff
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705883"
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="106d3-102">Практическое руководство. Отображение даты в пользовательском формате с элемента управления DateTimePicker в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="106d3-102">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="106d3-103">Windows Forms <xref:System.Windows.Forms.DateTimePicker> управления обеспечивает гибкость при форматировании отображение дат и времени в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="106d3-103">The Windows Forms <xref:System.Windows.Forms.DateTimePicker> control gives you flexibility in formatting the display of dates and times in the control.</span></span> <span data-ttu-id="106d3-104"><xref:System.Windows.Forms.DateTimePicker.Format%2A> Свойство позволяет выбрать из предопределенных форматов, перечисленных в <xref:System.Windows.Forms.DateTimePickerFormat>.</span><span class="sxs-lookup"><span data-stu-id="106d3-104">The <xref:System.Windows.Forms.DateTimePicker.Format%2A> property allows you to select from predefined formats, listed in the <xref:System.Windows.Forms.DateTimePickerFormat>.</span></span> <span data-ttu-id="106d3-105">Если ни один из них не подходит для ваших целей, можно создать собственный стиль формата, используя символы форматирования, перечисленные в <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span><span class="sxs-lookup"><span data-stu-id="106d3-105">If none of these is adequate for your purposes, you can create your own format style using format characters listed in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span></span>  
  
### <a name="to-display-a-custom-format"></a><span data-ttu-id="106d3-106">Для отображения в пользовательском формате</span><span class="sxs-lookup"><span data-stu-id="106d3-106">To display a custom format</span></span>  
  
1.  <span data-ttu-id="106d3-107">Задайте для свойства <xref:System.Windows.Forms.DateTimePicker.Format%2A> значение `DateTimePickerFormat.Custom`.</span><span class="sxs-lookup"><span data-stu-id="106d3-107">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to `DateTimePickerFormat.Custom`.</span></span>  
  
2.  <span data-ttu-id="106d3-108">Задать <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> свойства в строку формата.</span><span class="sxs-lookup"><span data-stu-id="106d3-108">Set the <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> property to a format string.</span></span>  
  
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
  
### <a name="to-add-text-to-the-formatted-value"></a><span data-ttu-id="106d3-109">Добавление текста на отформатированное значение</span><span class="sxs-lookup"><span data-stu-id="106d3-109">To add text to the formatted value</span></span>  
  
1.  <span data-ttu-id="106d3-110">Использовать одинарные кавычки для заключения в них любой символ, который не является символ форматирования, такие как «M» или разделителями, например «:».</span><span class="sxs-lookup"><span data-stu-id="106d3-110">Use single quotation marks to enclose any character that is not a format character like "M" or a delimiter like ":".</span></span> <span data-ttu-id="106d3-111">Например, строка формата отображает текущую дату в формате «сегодня является: 05:30:31 марта пятница 02, 2012" английского языка (США).</span><span class="sxs-lookup"><span data-stu-id="106d3-111">For example, the format string below displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span>  
  
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
  
     <span data-ttu-id="106d3-112">В зависимости от языка и региональных параметров, можно изменить любые символы, не заключаются в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="106d3-112">Depending on the culture setting, any characters not enclosed in single quotation marks may be changed.</span></span> <span data-ttu-id="106d3-113">Например, строка формата отображает текущую дату в формате «сегодня является: 05:30:31 марта пятница 02, 2012" английского языка (США).</span><span class="sxs-lookup"><span data-stu-id="106d3-113">For example, the format string above displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span> <span data-ttu-id="106d3-114">Обратите внимание на то, что первое двоеточие заключено в одинарные кавычки, поскольку он не используется в разделителя, как в «чч: мм:».</span><span class="sxs-lookup"><span data-stu-id="106d3-114">Note that the first colon is enclosed in single quotation marks, because it is not intended to be a delimiting character as it is in "hh:mm:ss".</span></span> <span data-ttu-id="106d3-115">В другой язык и региональные параметры, формат может отображаться как «сегодня является: 05.30.31 пятница март 02, 2012".</span><span class="sxs-lookup"><span data-stu-id="106d3-115">In another culture, the format might appear as "Today is: 05.30.31 Friday March 02, 2012".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="106d3-116">См. также</span><span class="sxs-lookup"><span data-stu-id="106d3-116">See also</span></span>
- [<span data-ttu-id="106d3-117">Элемент управления DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="106d3-117">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
- [<span data-ttu-id="106d3-118">Практическое руководство. Задайте и возвращаемого значения дат с помощью элемента управления DateTimePicker в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="106d3-118">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
