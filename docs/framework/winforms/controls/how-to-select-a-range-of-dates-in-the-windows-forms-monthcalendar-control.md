---
title: Выбор диапазона дат в элементе управления MonthCalendar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- dates [Windows Forms], selecting range in calendar controls
- examples [Windows Forms], calendar controls
- calendars [Windows Forms], selecting date range
- MonthCalendar control [Windows Forms], selecting date range
ms.assetid: 95d9ab95-b0f8-4c19-9f63-b5cd4593a5d0
ms.openlocfilehash: bda96af21a8f86a54d5c0fe0204546b980076d26
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732893"
---
# <a name="how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="2aab8-102">Практическое руководство. Выбор диапазона дат в элементе управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2aab8-102">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="2aab8-103">Важной особенностью элемента управления Windows Forms <xref:System.Windows.Forms.MonthCalendar> является то, что пользователь может выбрать диапазон дат.</span><span class="sxs-lookup"><span data-stu-id="2aab8-103">An important feature of the Windows Forms <xref:System.Windows.Forms.MonthCalendar> control is that the user can select a range of dates.</span></span> <span data-ttu-id="2aab8-104">Эта функция является улучшением по сравнению с функцией выбора даты элемента управления <xref:System.Windows.Forms.DateTimePicker>, которая позволяет пользователю выбрать только одно значение даты и времени.</span><span class="sxs-lookup"><span data-stu-id="2aab8-104">This feature is an improvement over the date-selection feature of the <xref:System.Windows.Forms.DateTimePicker> control, which only enables the user to select a single date/time value.</span></span> <span data-ttu-id="2aab8-105">Можно задать диапазон дат или получить диапазон выбора, заданный пользователем, с помощью свойств элемента управления <xref:System.Windows.Forms.MonthCalendar>.</span><span class="sxs-lookup"><span data-stu-id="2aab8-105">You can set a range of dates or get a selection range set by the user by using properties of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span> <span data-ttu-id="2aab8-106">В следующем примере кода показано, как задать диапазон выбора.</span><span class="sxs-lookup"><span data-stu-id="2aab8-106">The following code example demonstrates how to set a selection range.</span></span>  
  
### <a name="to-select-a-range-of-dates"></a><span data-ttu-id="2aab8-107">Выбор диапазона дат</span><span class="sxs-lookup"><span data-stu-id="2aab8-107">To select a range of dates</span></span>  
  
1. <span data-ttu-id="2aab8-108">Создание <xref:System.DateTime> объектов, представляющих первую и последнюю даты в диапазоне.</span><span class="sxs-lookup"><span data-stu-id="2aab8-108">Create <xref:System.DateTime> objects that represent the first and last dates in a range.</span></span>  
  
    ```vb  
    Dim projectStart As Date = New DateTime(2001, 2, 13)  
    Dim projectEnd As Date = New DateTime(2001, 2, 28)  
    ```  
  
    ```csharp  
    DateTime projectStart = new DateTime(2001, 2, 13);  
    DateTime projectEnd = new DateTime(2001, 2, 28);  
    ```  
  
    ```cpp  
    DateTime projectStart = DateTime(2001, 2, 13);  
    DateTime projectEnd = DateTime(2001, 2, 28);  
    ```  
  
2. <span data-ttu-id="2aab8-109">Задайте свойство <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>.</span><span class="sxs-lookup"><span data-stu-id="2aab8-109">Set the <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> property.</span></span>  
  
    ```vb  
    MonthCalendar1.SelectionRange = New SelectionRange(projectStart, projectEnd)  
    ```  
  
    ```csharp  
    monthCalendar1.SelectionRange = new SelectionRange(projectStart, projectEnd);  
    ```  
  
    ```cpp  
    monthCalendar1->SelectionRange = gcnew  
       SelectionRange(projectStart, projectEnd);  
    ```  
  
     <span data-ttu-id="2aab8-110">–или–</span><span class="sxs-lookup"><span data-stu-id="2aab8-110">–or–</span></span>  
  
     <span data-ttu-id="2aab8-111">Укажите свойства <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> и <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A>.</span><span class="sxs-lookup"><span data-stu-id="2aab8-111">Set the <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> and <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A> properties.</span></span>  
  
    ```vb  
    MonthCalendar1.SelectionStart = projectStart  
    MonthCalendar1.SelectionEnd = projectEnd  
    ```  
  
    ```csharp  
    monthCalendar1.SelectionStart = projectStart;  
    monthCalendar1.SelectionEnd = projectEnd;  
    ```  
  
    ```cpp  
    monthCalendar1->SelectionStart = projectStart;  
    monthCalendar1->SelectionEnd = projectEnd;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2aab8-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2aab8-112">See also</span></span>

- [<span data-ttu-id="2aab8-113">Элемент управления MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="2aab8-113">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="2aab8-114">Практическое руководство. Изменение внешнего вида элемента управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2aab8-114">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
- [<span data-ttu-id="2aab8-115">Практическое руководство. Отображение определенных дней полужирным шрифтом в элементе управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2aab8-115">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [<span data-ttu-id="2aab8-116">Практическое руководство. Отображение более чем одного месяца в элементе управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2aab8-116">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
