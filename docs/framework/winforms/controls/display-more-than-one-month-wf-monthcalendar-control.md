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
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="cf665-102">Практическое руководство. Отображение более чем одного месяца в элементе управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cf665-102">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="cf665-103">Элемент управления <xref:System.Windows.Forms.MonthCalendar> Windows Forms может отображать до 12 месяцев за раз.</span><span class="sxs-lookup"><span data-stu-id="cf665-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display up to 12 months at a time.</span></span> <span data-ttu-id="cf665-104">По умолчанию элемент управления отображает только один месяц, но можно указать, сколько месяцев отображается и как они упорядочены внутри элемента управления.</span><span class="sxs-lookup"><span data-stu-id="cf665-104">By default, the control displays only one month, but you can specify how many months are displayed and how they are arranged within the control.</span></span> <span data-ttu-id="cf665-105">При изменении размеров календаря размер элемента управления изменяется, поэтому убедитесь, что в форме достаточно места для новых измерений.</span><span class="sxs-lookup"><span data-stu-id="cf665-105">When you change the calendar dimensions, the control is resized, so be sure there is enough room on the form for the new dimensions.</span></span>  
  
### <a name="to-display-multiple-months"></a><span data-ttu-id="cf665-106">Отображение нескольких месяцев</span><span class="sxs-lookup"><span data-stu-id="cf665-106">To display multiple months</span></span>  
  
- <span data-ttu-id="cf665-107">Задайте для свойства <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> число месяцев, отображаемых горизонтально и вертикально.</span><span class="sxs-lookup"><span data-stu-id="cf665-107">Set the <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> property to the number of months to display horizontally and vertically.</span></span>  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cf665-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="cf665-108">See also</span></span>

- [<span data-ttu-id="cf665-109">Элемент управления MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="cf665-109">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="cf665-110">Практическое руководство. Выбор диапазона дат в элементе управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cf665-110">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="cf665-111">Практическое руководство. Изменение внешнего вида элемента управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cf665-111">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
