---
title: "Практическое руководство. Отображение даты в пользовательском формате с помощью элемента управления DateTimePicker в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DateTimePicker control [Windows Forms], display styles
- examples [Windows Forms], DateTimePicker control
- dates [Windows Forms], displaying in DateTimePicker control
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a5f5c7d856991ae8e0bf7caff656bf7010255628
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="49691-102">Практическое руководство. Отображение даты в пользовательском формате с помощью элемента управления DateTimePicker в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="49691-102">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="49691-103">Windows Forms <xref:System.Windows.Forms.DateTimePicker> управления обеспечивает гибкие возможности форматирования отображаемых данных даты и времени в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="49691-103">The Windows Forms <xref:System.Windows.Forms.DateTimePicker> control gives you flexibility in formatting the display of dates and times in the control.</span></span> <span data-ttu-id="49691-104"><xref:System.Windows.Forms.DateTimePicker.Format%2A> Свойства можно выбрать из стандартных форматов, перечисленных в <xref:System.Windows.Forms.DateTimePickerFormat>.</span><span class="sxs-lookup"><span data-stu-id="49691-104">The <xref:System.Windows.Forms.DateTimePicker.Format%2A> property allows you to select from predefined formats, listed in the <xref:System.Windows.Forms.DateTimePickerFormat>.</span></span> <span data-ttu-id="49691-105">Если ни один из них не подходит для ваших целей, можно создать собственный стиль формата, с помощью символов формата, перечисленные в <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span><span class="sxs-lookup"><span data-stu-id="49691-105">If none of these is adequate for your purposes, you can create your own format style using format characters listed in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span></span>  
  
### <a name="to-display-a-custom-format"></a><span data-ttu-id="49691-106">Чтобы отобразить пользовательский формат</span><span class="sxs-lookup"><span data-stu-id="49691-106">To display a custom format</span></span>  
  
1.  <span data-ttu-id="49691-107">Задайте для свойства <xref:System.Windows.Forms.DateTimePicker.Format%2A> значение `DateTimePickerFormat.Custom`.</span><span class="sxs-lookup"><span data-stu-id="49691-107">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to `DateTimePickerFormat.Custom`.</span></span>  
  
2.  <span data-ttu-id="49691-108">Задать <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> свойства в строке формата.</span><span class="sxs-lookup"><span data-stu-id="49691-108">Set the <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> property to a format string.</span></span>  
  
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
  
### <a name="to-add-text-to-the-formatted-value"></a><span data-ttu-id="49691-109">Добавление текста в форматированное значение</span><span class="sxs-lookup"><span data-stu-id="49691-109">To add text to the formatted value</span></span>  
  
1.  <span data-ttu-id="49691-110">Использовать одинарные кавычки для заключения знаков, которые не являются знаками формата, например «M» или разделителями, например «:».</span><span class="sxs-lookup"><span data-stu-id="49691-110">Use single quotation marks to enclose any character that is not a format character like "M" or a delimiter like ":".</span></span> <span data-ttu-id="49691-111">Например, строка формата отображает текущую дату в формате «сегодня: 05:30:31 пятница 02 марта 2012 г.» Английский (США) язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="49691-111">For example, the format string below displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span>  
  
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
  
     <span data-ttu-id="49691-112">В зависимости от языка и региональных параметров, можно изменить любые символы, которые не заключаются в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="49691-112">Depending on the culture setting, any characters not enclosed in single quotation marks may be changed.</span></span> <span data-ttu-id="49691-113">Например, строка формата отображает текущую дату в формате «сегодня: 05:30:31 пятница 02 марта 2012 г.» Английский (США) язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="49691-113">For example, the format string above displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span> <span data-ttu-id="49691-114">Обратите внимание, что первое двоеточие заключено в одинарные кавычки, поскольку он не предназначен для символа-разделителя, как в «чч».</span><span class="sxs-lookup"><span data-stu-id="49691-114">Note that the first colon is enclosed in single quotation marks, because it is not intended to be a delimiting character as it is in "hh:mm:ss".</span></span> <span data-ttu-id="49691-115">В другой язык и региональные параметры, формат может быть как «сегодня: 05.30.31 пятница 02 марта 2012 г.».</span><span class="sxs-lookup"><span data-stu-id="49691-115">In another culture, the format might appear as "Today is: 05.30.31 Friday March 02, 2012".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49691-116">См. также</span><span class="sxs-lookup"><span data-stu-id="49691-116">See Also</span></span>  
 [<span data-ttu-id="49691-117">Элемент управления DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="49691-117">DateTimePicker Control</span></span>](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)  
 [<span data-ttu-id="49691-118">Практическое руководство. Отображение и ввод дат с помощью элемента управления DateTimePicker в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="49691-118">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
