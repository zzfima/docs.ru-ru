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
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="f1e3d-102">Как выполнить Отображение более чем одного месяца в элементе управления Windows Forms MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="f1e3d-102">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="f1e3d-103">Windows Forms <xref:System.Windows.Forms.MonthCalendar> элемент управления может отображать до 12 месяцев, за раз.</span><span class="sxs-lookup"><span data-stu-id="f1e3d-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display up to 12 months at a time.</span></span> <span data-ttu-id="f1e3d-104">По умолчанию элемент управления отображает только один месяц, но можно указать количество месяцев, отображаются и их размещение в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="f1e3d-104">By default, the control displays only one month, but you can specify how many months are displayed and how they are arranged within the control.</span></span> <span data-ttu-id="f1e3d-105">Когда вы изменяете размеры календаря, размер, поэтому убедитесь, что имеется достаточно места в форме для новых измерений.</span><span class="sxs-lookup"><span data-stu-id="f1e3d-105">When you change the calendar dimensions, the control is resized, so be sure there is enough room on the form for the new dimensions.</span></span>  
  
### <a name="to-display-multiple-months"></a><span data-ttu-id="f1e3d-106">Чтобы отобразить несколько месяцев</span><span class="sxs-lookup"><span data-stu-id="f1e3d-106">To display multiple months</span></span>  
  
-   <span data-ttu-id="f1e3d-107">Задайте <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> количество месяцев, отображаемых по горизонтали и вертикали.</span><span class="sxs-lookup"><span data-stu-id="f1e3d-107">Set the <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> property to the number of months to display horizontally and vertically.</span></span>  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f1e3d-108">См. также</span><span class="sxs-lookup"><span data-stu-id="f1e3d-108">See also</span></span>
- [<span data-ttu-id="f1e3d-109">Элемент управления MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="f1e3d-109">MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="f1e3d-110">Практическое руководство. Выбор диапазона дат в элементе управления Windows Forms MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="f1e3d-110">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="f1e3d-111">Практическое руководство. Изменение внешнего вида управления Windows Forms MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="f1e3d-111">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)
