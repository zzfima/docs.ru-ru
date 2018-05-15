---
title: Практическое руководство. Отображение определенных дней полужирным шрифтом в элементе управления MonthCalendar в Windows Forms
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
ms.openlocfilehash: 0ee89fb4cfb6ddbf975eb0e85e7dd1bab30f08d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="7ce11-102">Практическое руководство. Отображение определенных дней полужирным шрифтом в элементе управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ce11-102">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="7ce11-103">Windows Forms <xref:System.Windows.Forms.MonthCalendar> элемент управления может отображать дни полужирным шрифтом, как существительные даты или на периодической основе.</span><span class="sxs-lookup"><span data-stu-id="7ce11-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display days in bold type, either as singular dates or on a repeating basis.</span></span> <span data-ttu-id="7ce11-104">Это может сделать для привлечения внимания к определенные даты, например праздников и выходных дней.</span><span class="sxs-lookup"><span data-stu-id="7ce11-104">You might do this to draw attention to special dates, such as holidays and weekends.</span></span>  
  
 <span data-ttu-id="7ce11-105">Эта функция трех свойств.</span><span class="sxs-lookup"><span data-stu-id="7ce11-105">Three properties control this feature.</span></span> <span data-ttu-id="7ce11-106"><xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> Свойство содержит отдельные даты.</span><span class="sxs-lookup"><span data-stu-id="7ce11-106">The <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> property contains single dates.</span></span> <span data-ttu-id="7ce11-107"><xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> Свойство содержит даты, которые отображаются полужирным шрифтом каждый год.</span><span class="sxs-lookup"><span data-stu-id="7ce11-107">The <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> property contains dates that appear in bold every year.</span></span> <span data-ttu-id="7ce11-108"><xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> Свойство содержит даты, которые отображаются полужирным шрифтом каждый месяц.</span><span class="sxs-lookup"><span data-stu-id="7ce11-108">The <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> property contains dates that appear in bold every month.</span></span> <span data-ttu-id="7ce11-109">Каждое из этих свойств содержит массив <xref:System.DateTime> объектов.</span><span class="sxs-lookup"><span data-stu-id="7ce11-109">Each of these properties contains an array of <xref:System.DateTime> objects.</span></span> <span data-ttu-id="7ce11-110">Чтобы добавить или удалить дату из одного из этих списков, необходимо добавить или удалить <xref:System.DateTime> объекта.</span><span class="sxs-lookup"><span data-stu-id="7ce11-110">To add or remove a date from one of these lists, you must add or remove a <xref:System.DateTime> object.</span></span>  
  
### <a name="to-make-a-date-appear-in-bold-type"></a><span data-ttu-id="7ce11-111">Выделяются полужирным шрифтом даты</span><span class="sxs-lookup"><span data-stu-id="7ce11-111">To make a date appear in bold type</span></span>  
  
1.  <span data-ttu-id="7ce11-112">Создание <xref:System.DateTime> объектов.</span><span class="sxs-lookup"><span data-stu-id="7ce11-112">Create the <xref:System.DateTime> objects.</span></span>  
  
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
  
2.  <span data-ttu-id="7ce11-113">Выделение полужирным шрифтом дату путем вызова <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, или <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> метод <xref:System.Windows.Forms.MonthCalendar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7ce11-113">Make a single date bold by calling the <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> method of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span>  
  
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
  
     <span data-ttu-id="7ce11-114">– или –</span><span class="sxs-lookup"><span data-stu-id="7ce11-114">–or–</span></span>  
  
     <span data-ttu-id="7ce11-115">Выделите дат полужирным за один раз, создав массив <xref:System.DateTime> объекты и присвоение одного из свойств.</span><span class="sxs-lookup"><span data-stu-id="7ce11-115">Make a set of dates bold all at once by creating an array of <xref:System.DateTime> objects and assigning it to one of the properties.</span></span>  
  
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
  
### <a name="to-make-a-date-appear-in-the-regular-font"></a><span data-ttu-id="7ce11-116">Для отображения даты обычным шрифтом</span><span class="sxs-lookup"><span data-stu-id="7ce11-116">To make a date appear in the regular font</span></span>  
  
1.  <span data-ttu-id="7ce11-117">Один выделенный полужирным шрифтом даты отображаются обычным шрифтом, вызвав <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, или <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="7ce11-117">Make a single bolded date appear in the regular font by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> method.</span></span>  
  
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
  
     <span data-ttu-id="7ce11-118">– или –</span><span class="sxs-lookup"><span data-stu-id="7ce11-118">–or–</span></span>  
  
     <span data-ttu-id="7ce11-119">Удалите все выделенные полужирным шрифтом даты из одной из трех списков путем вызова <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>, или <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="7ce11-119">Remove all the bolded dates from one of the three lists by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2.  <span data-ttu-id="7ce11-120">Обновить внешний вид шрифта, вызвав <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="7ce11-120">Update the appearance of the font by calling the <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7ce11-121">См. также</span><span class="sxs-lookup"><span data-stu-id="7ce11-121">See Also</span></span>  
 [<span data-ttu-id="7ce11-122">Элемент управления MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="7ce11-122">MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [<span data-ttu-id="7ce11-123">Практическое руководство. Выбор диапазона дат в элементе управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ce11-123">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 [<span data-ttu-id="7ce11-124">Практическое руководство. Изменение внешнего вида элемента управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ce11-124">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)  
 [<span data-ttu-id="7ce11-125">Практическое руководство. Отображение более чем одного месяца в элементе управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ce11-125">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
