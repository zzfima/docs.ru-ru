---
title: Практическое руководство. Отображение более чем одного месяца в элементе управления MonthCalendar в Windows Forms
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
ms.openlocfilehash: a71f85af2d51faf37160aba7fa89a8421b4523d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="0aa49-102">Практическое руководство. Отображение более чем одного месяца в элементе управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0aa49-102">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="0aa49-103">Windows Forms <xref:System.Windows.Forms.MonthCalendar> элемент управления может отображать до 12 месяцев одновременно.</span><span class="sxs-lookup"><span data-stu-id="0aa49-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display up to 12 months at a time.</span></span> <span data-ttu-id="0aa49-104">По умолчанию элемент управления отображается только один месяц, но можно указать количество месяцев, отображаются и их размещение в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="0aa49-104">By default, the control displays only one month, but you can specify how many months are displayed and how they are arranged within the control.</span></span> <span data-ttu-id="0aa49-105">При изменении измерения «календарь», размер, поэтому убедитесь, что имеется достаточно места для новых измерений в форме.</span><span class="sxs-lookup"><span data-stu-id="0aa49-105">When you change the calendar dimensions, the control is resized, so be sure there is enough room on the form for the new dimensions.</span></span>  
  
### <a name="to-display-multiple-months"></a><span data-ttu-id="0aa49-106">Чтобы отобразить несколько месяцев</span><span class="sxs-lookup"><span data-stu-id="0aa49-106">To display multiple months</span></span>  
  
-   <span data-ttu-id="0aa49-107">Задать <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> количество месяцев, отображаемых по горизонтали и вертикали.</span><span class="sxs-lookup"><span data-stu-id="0aa49-107">Set the <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> property to the number of months to display horizontally and vertically.</span></span>  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0aa49-108">См. также</span><span class="sxs-lookup"><span data-stu-id="0aa49-108">See Also</span></span>  
 [<span data-ttu-id="0aa49-109">Элемент управления MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="0aa49-109">MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [<span data-ttu-id="0aa49-110">Практическое руководство. Выбор диапазона дат в элементе управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0aa49-110">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 [<span data-ttu-id="0aa49-111">Практическое руководство. Изменение внешнего вида элемента управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0aa49-111">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)
