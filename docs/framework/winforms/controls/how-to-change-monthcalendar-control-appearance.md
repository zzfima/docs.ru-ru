---
title: Практическое руководство. Изменение внешнего вида элемента управления MonthCalendar в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
ms.openlocfilehash: 5582624d881b2d8039bcd5e8ac45e548c7b38f57
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929051"
---
# <a name="how-to-change-the-windows-forms-monthcalendar-controls-appearance"></a><span data-ttu-id="75a98-102">Практическое руководство. Изменение внешнего вида элемента управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="75a98-102">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>
<span data-ttu-id="75a98-103">Элемент управления <xref:System.Windows.Forms.MonthCalendar> Windows Forms позволяет настраивать внешний вид календаря различными способами.</span><span class="sxs-lookup"><span data-stu-id="75a98-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control allows you to customize the calendar's appearance in many ways.</span></span> <span data-ttu-id="75a98-104">Например, можно задать цветовую схему и выбрать отображение или скрытие номеров недель и текущей даты.</span><span class="sxs-lookup"><span data-stu-id="75a98-104">For example, you can set the color scheme and choose to display or hide week numbers and the current date.</span></span>  
  
### <a name="to-change-the-month-calendars-color-scheme"></a><span data-ttu-id="75a98-105">Изменение цветовой схемы календаря на месяц</span><span class="sxs-lookup"><span data-stu-id="75a98-105">To change the month calendar's color scheme</span></span>  
  
- <span data-ttu-id="75a98-106">Задайте свойства, такие <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>как <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> , <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>и.</span><span class="sxs-lookup"><span data-stu-id="75a98-106">Set properties such as <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> and <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span></span> <span data-ttu-id="75a98-107"><xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> Свойство также определяет цвет шрифта для дней недели.</span><span class="sxs-lookup"><span data-stu-id="75a98-107">The <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> property also determines the font color for the days of the week.</span></span> <span data-ttu-id="75a98-108"><xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> Свойство определяет цвет дат, которые предшествуют отображаемому месяцу или месяцам и следуют за ним.</span><span class="sxs-lookup"><span data-stu-id="75a98-108">The <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> property determines the color of the dates that precede and follow the displayed month or months.</span></span>  
  
    ```vb  
    MonthCalendar1.TitleBackColor = System.Drawing.Color.Blue  
    MonthCalendar1.TrailingForeColor = System.Drawing.Color.Red  
    MonthCalendar1.TitleForeColor = System.Drawing.Color.Yellow  
    ```  
  
    ```csharp  
    monthCalendar1.TitleBackColor = System.Drawing.Color.Blue;  
    monthCalendar1.TrailingForeColor = System.Drawing.Color.Red;  
    monthCalendar1.TitleForeColor = System.Drawing.Color.Yellow;  
    ```  
  
    ```cpp  
    monthCalendar1->TitleBackColor = System::Drawing::Color::Blue;  
    monthCalendar1->TrailingForeColor = System::Drawing::Color::Red;  
    monthCalendar1->TitleForeColor = System::Drawing::Color::Yellow;  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="75a98-109">Начиная с Windows Vista и в зависимости от темы, установка некоторых свойств может не изменить внешний вид календаря.</span><span class="sxs-lookup"><span data-stu-id="75a98-109">Starting with Windows Vista and depending on the theme, setting some properties might not change the appearance of the calendar.</span></span> <span data-ttu-id="75a98-110">Например, если в <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>Windows настроено использование темы Aero, установка свойств, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>или <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="75a98-110">For example, if Windows is set to use the Aero theme, setting the <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, or <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> properties has no effect.</span></span> <span data-ttu-id="75a98-111">Это связано с тем, что обновленная версия календаря отображается с внешним видом, полученным во время выполнения из текущей темы операционной системы.</span><span class="sxs-lookup"><span data-stu-id="75a98-111">This is because an updated version of the calendar is rendered with an appearance that is derived at run time from the current operating system theme.</span></span> <span data-ttu-id="75a98-112">Если вы хотите использовать эти свойства и включить более раннюю версию календаря, можно отключить стили оформления для приложения.</span><span class="sxs-lookup"><span data-stu-id="75a98-112">If you want to use these properties and enable the earlier version of the calendar, you can disable visual styles for your application.</span></span> <span data-ttu-id="75a98-113">Отключение стилей оформления может повлиять на внешний вид и поведение других элементов управления в приложении.</span><span class="sxs-lookup"><span data-stu-id="75a98-113">Disabling visual styles might affect the appearance and behavior of other controls in your application.</span></span> <span data-ttu-id="75a98-114">Чтобы отключить стили оформления в Visual Basic, откройте конструктор проектов и снимите флажок **включить стили Visual XP** .</span><span class="sxs-lookup"><span data-stu-id="75a98-114">To disable visual styles in Visual Basic, open the Project Designer and uncheck the **Enable XP visual styles** check box.</span></span> <span data-ttu-id="75a98-115">Чтобы отключить стили оформления в C#, откройте Program.cs и закомментируйте комментарий `Application.EnableVisualStyles();`.</span><span class="sxs-lookup"><span data-stu-id="75a98-115">To disable visual styles in C#, open Program.cs and comment out `Application.EnableVisualStyles();`.</span></span> <span data-ttu-id="75a98-116">Дополнительные сведения о стилях оформления см. в разделе [Включение визуальных стилей](/windows/desktop/controls/cookbook-overview).</span><span class="sxs-lookup"><span data-stu-id="75a98-116">For more information about visual styles, see [Enabling Visual Styles](/windows/desktop/controls/cookbook-overview).</span></span>  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a><span data-ttu-id="75a98-117">Отображение текущей даты в нижней части элемента управления</span><span class="sxs-lookup"><span data-stu-id="75a98-117">To display the current date at the bottom of the control</span></span>  
  
- <span data-ttu-id="75a98-118">Задайте для свойства <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="75a98-118">Set the <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> property to `true`.</span></span> <span data-ttu-id="75a98-119">Приведенный ниже пример переключает отображение и пропуск текущей даты при двойном щелчке на форме.</span><span class="sxs-lookup"><span data-stu-id="75a98-119">The example below toggles between displaying and omitting today's date when the form is double-clicked.</span></span>  
  
    ```vb  
    Private Sub Form1_DoubleClick(ByVal sender As Object, _  
    ByVal e As System.EventArgs) Handles MyBase.DoubleClick  
       ' Toggle between True and False.  
       MonthCalendar1.ShowToday = Not MonthCalendar1.ShowToday  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_DoubleClick(object sender, System.EventArgs e)  
    {  
       // Toggle between True and False.  
       monthCalendar1.ShowToday = !monthCalendar1.ShowToday;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void Form1_DoubleClick(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          // Toggle between True and False.  
          monthCalendar1->ShowToday = !monthCalendar1->ShowToday;  
       }  
    ```  
  
     <span data-ttu-id="75a98-120">(Визуальный C#элемент C++, визуальный элемент) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="75a98-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a><span data-ttu-id="75a98-121">Отображение номеров недель</span><span class="sxs-lookup"><span data-stu-id="75a98-121">To display week numbers</span></span>  
  
- <span data-ttu-id="75a98-122">Задайте для свойства <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="75a98-122">Set the <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> property to `true`.</span></span> <span data-ttu-id="75a98-123">Это свойство можно задать либо в коде, либо в окно свойств.</span><span class="sxs-lookup"><span data-stu-id="75a98-123">You can set this property either in code or in the Properties window.</span></span>  
  
     <span data-ttu-id="75a98-124">Номера недель отображаются в отдельном столбце слева от первого дня недели.</span><span class="sxs-lookup"><span data-stu-id="75a98-124">Week numbers appear in a separate column to the left of the first day of the week.</span></span>  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="75a98-125">См. также</span><span class="sxs-lookup"><span data-stu-id="75a98-125">See also</span></span>

- [<span data-ttu-id="75a98-126">Элемент управления MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="75a98-126">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="75a98-127">Практическое руководство. Выбор диапазона дат в элементе управления Windows Forms MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="75a98-127">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="75a98-128">Практическое руководство. Отображение отдельных дней полужирным шрифтом с помощью элемента управления Windows Forms MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="75a98-128">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [<span data-ttu-id="75a98-129">Практическое руководство. Отображение более одного месяца в элементе управления Windows Forms MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="75a98-129">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
