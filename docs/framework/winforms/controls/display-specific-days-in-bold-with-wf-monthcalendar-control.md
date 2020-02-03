---
title: Отображать определенные дни полужирным шрифтом с помощью элемента управления MonthCalendar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- calendars [Windows Forms], displaying dates in bold
- examples [Windows Forms], calendar controls
- GetDayBold event
- MonthCalendar control [Windows Forms], dates displayed in bold
ms.assetid: 8b20db5b-8118-4825-90e8-2c45c186ac7d
ms.openlocfilehash: 377eb76f562fff20aae2136ddb7130516d2d76f7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745881"
---
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="4d8b0-102">Практическое руководство. Отображение определенных дней полужирным шрифтом в элементе управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4d8b0-102">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="4d8b0-103">Элемент управления Windows Forms <xref:System.Windows.Forms.MonthCalendar> может отображать дни полужирным шрифтом в виде отдельных дат или на повторяющейся основе.</span><span class="sxs-lookup"><span data-stu-id="4d8b0-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display days in bold type, either as singular dates or on a repeating basis.</span></span> <span data-ttu-id="4d8b0-104">Это можно сделать, чтобы привлечь внимание к специальным датам, таким как праздники и выходные.</span><span class="sxs-lookup"><span data-stu-id="4d8b0-104">You might do this to draw attention to special dates, such as holidays and weekends.</span></span>  
  
 <span data-ttu-id="4d8b0-105">Эта функция управляется тремя свойствами.</span><span class="sxs-lookup"><span data-stu-id="4d8b0-105">Three properties control this feature.</span></span> <span data-ttu-id="4d8b0-106">Свойство <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> содержит отдельные даты.</span><span class="sxs-lookup"><span data-stu-id="4d8b0-106">The <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> property contains single dates.</span></span> <span data-ttu-id="4d8b0-107">Свойство <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> содержит даты, которые отображаются жирным шрифтом каждый год.</span><span class="sxs-lookup"><span data-stu-id="4d8b0-107">The <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> property contains dates that appear in bold every year.</span></span> <span data-ttu-id="4d8b0-108">Свойство <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> содержит даты, которые отображаются жирным шрифтом каждый месяц.</span><span class="sxs-lookup"><span data-stu-id="4d8b0-108">The <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> property contains dates that appear in bold every month.</span></span> <span data-ttu-id="4d8b0-109">Каждое из этих свойств содержит массив объектов <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="4d8b0-109">Each of these properties contains an array of <xref:System.DateTime> objects.</span></span> <span data-ttu-id="4d8b0-110">Чтобы добавить или удалить дату из одного из этих списков, необходимо добавить или удалить объект <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="4d8b0-110">To add or remove a date from one of these lists, you must add or remove a <xref:System.DateTime> object.</span></span>  
  
### <a name="to-make-a-date-appear-in-bold-type"></a><span data-ttu-id="4d8b0-111">Отображение даты в полужирном типе</span><span class="sxs-lookup"><span data-stu-id="4d8b0-111">To make a date appear in bold type</span></span>  
  
1. <span data-ttu-id="4d8b0-112">Создайте объекты <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="4d8b0-112">Create the <xref:System.DateTime> objects.</span></span>  
  
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
  
2. <span data-ttu-id="4d8b0-113">Чтобы выделить одну дату полужирным шрифтом, вызовите метод <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>или <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> элемента управления <xref:System.Windows.Forms.MonthCalendar>.</span><span class="sxs-lookup"><span data-stu-id="4d8b0-113">Make a single date bold by calling the <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> method of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span>  
  
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
  
     <span data-ttu-id="4d8b0-114">–или–</span><span class="sxs-lookup"><span data-stu-id="4d8b0-114">–or–</span></span>  
  
     <span data-ttu-id="4d8b0-115">Сделайте набор дат жирным, создав массив объектов <xref:System.DateTime> и назначив их одному из свойств.</span><span class="sxs-lookup"><span data-stu-id="4d8b0-115">Make a set of dates bold all at once by creating an array of <xref:System.DateTime> objects and assigning it to one of the properties.</span></span>  
  
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
  
### <a name="to-make-a-date-appear-in-the-regular-font"></a><span data-ttu-id="4d8b0-116">Отображение даты в обычном шрифте</span><span class="sxs-lookup"><span data-stu-id="4d8b0-116">To make a date appear in the regular font</span></span>  
  
1. <span data-ttu-id="4d8b0-117">Чтобы выделить одну полужирную дату в обычном шрифте, вызовите метод <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>или <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A>.</span><span class="sxs-lookup"><span data-stu-id="4d8b0-117">Make a single bolded date appear in the regular font by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> method.</span></span>  
  
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
  
     <span data-ttu-id="4d8b0-118">–или–</span><span class="sxs-lookup"><span data-stu-id="4d8b0-118">–or–</span></span>  
  
     <span data-ttu-id="4d8b0-119">Удалите все даты, выделенные жирным шрифтом, из одного из трех списков, вызвав метод <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>или <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A>.</span><span class="sxs-lookup"><span data-stu-id="4d8b0-119">Remove all the bolded dates from one of the three lists by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2. <span data-ttu-id="4d8b0-120">Обновите внешний вид шрифта, вызвав метод <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A>.</span><span class="sxs-lookup"><span data-stu-id="4d8b0-120">Update the appearance of the font by calling the <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4d8b0-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4d8b0-121">See also</span></span>

- [<span data-ttu-id="4d8b0-122">Элемент управления MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="4d8b0-122">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="4d8b0-123">Практическое руководство. Выбор диапазона дат в элементе управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4d8b0-123">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="4d8b0-124">Практическое руководство. Изменение внешнего вида элемента управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4d8b0-124">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
- [<span data-ttu-id="4d8b0-125">Практическое руководство. Отображение более чем одного месяца в элементе управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4d8b0-125">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
