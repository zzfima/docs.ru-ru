---
title: "Как: изменение элемента управления Windows Forms MonthCalendar &#39; s внешний вид"
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
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b9c401532fa7a5f09462cf12084f32bca3f721cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-windows-forms-monthcalendar-control39s-appearance"></a><span data-ttu-id="69cbc-102">Как: изменение элемента управления Windows Forms MonthCalendar &#39; s внешний вид</span><span class="sxs-lookup"><span data-stu-id="69cbc-102">How to: Change the Windows Forms MonthCalendar Control&#39;s Appearance</span></span>
<span data-ttu-id="69cbc-103">Windows Forms <xref:System.Windows.Forms.MonthCalendar> управления позволяет настраивать внешний вид календаря различными способами.</span><span class="sxs-lookup"><span data-stu-id="69cbc-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control allows you to customize the calendar's appearance in many ways.</span></span> <span data-ttu-id="69cbc-104">Например можно задать цвет и вывести на экран или скрытия номеров недель или текущей даты.</span><span class="sxs-lookup"><span data-stu-id="69cbc-104">For example, you can set the color scheme and choose to display or hide week numbers and the current date.</span></span>  
  
### <a name="to-change-the-month-calendars-color-scheme"></a><span data-ttu-id="69cbc-105">Чтобы изменить цветовую схему месячный календарь</span><span class="sxs-lookup"><span data-stu-id="69cbc-105">To change the month calendar's color scheme</span></span>  
  
-   <span data-ttu-id="69cbc-106">Задайте свойства, такие как <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> и <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="69cbc-106">Set properties such as <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> and <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span></span> <span data-ttu-id="69cbc-107"><xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> Свойство определяет цвет шрифта для дней недели.</span><span class="sxs-lookup"><span data-stu-id="69cbc-107">The <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> property also determines the font color for the days of the week.</span></span> <span data-ttu-id="69cbc-108"><xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> Свойство определяет цвет дат, которые предшествуют и следуют за отображаемый месяц или месяцы.</span><span class="sxs-lookup"><span data-stu-id="69cbc-108">The <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> property determines the color of the dates that precede and follow the displayed month or months.</span></span>  
  
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
    >  <span data-ttu-id="69cbc-109">Начиная с Windows Vista и в зависимости от темы, установки некоторых свойств может не изменить внешний вид календаря.</span><span class="sxs-lookup"><span data-stu-id="69cbc-109">Starting with Windows Vista and depending on the theme, setting some properties might not change the appearance of the calendar.</span></span> <span data-ttu-id="69cbc-110">Например, если Windows настроена на использование темы Aero, задание <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, или <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> свойства не оказывает влияния.</span><span class="sxs-lookup"><span data-stu-id="69cbc-110">For example, if Windows is set to use the Aero theme, setting the <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, or <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> properties has no effect.</span></span> <span data-ttu-id="69cbc-111">Это происходит потому обновленную версию календаря визуализируется с внешний вид, который является производным от текущей темы операционной системы во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="69cbc-111">This is because an updated version of the calendar is rendered with an appearance that is derived at run time from the current operating system theme.</span></span> <span data-ttu-id="69cbc-112">Если вы хотите использовать эти свойства и включить более раннюю версию календаря, можно отключить визуальные стили для приложения.</span><span class="sxs-lookup"><span data-stu-id="69cbc-112">If you want to use these properties and enable the earlier version of the calendar, you can disable visual styles for your application.</span></span> <span data-ttu-id="69cbc-113">Отключение визуальных стилей может повлиять на внешний вид и поведение других элементов управления в приложении.</span><span class="sxs-lookup"><span data-stu-id="69cbc-113">Disabling visual styles might affect the appearance and behavior of other controls in your application.</span></span> <span data-ttu-id="69cbc-114">Чтобы отключить визуальные стили в Visual Basic, откройте конструктор проектов и снимите флажки **включить визуальные стили XP** флажок.</span><span class="sxs-lookup"><span data-stu-id="69cbc-114">To disable visual styles in Visual Basic, open the Project Designer and uncheck the **Enable XP visual styles** check box.</span></span> <span data-ttu-id="69cbc-115">Чтобы отключить визуальные стили в C#, откройте файл Program.cs и закомментируйте `Application.EnableVisualStyles();`.</span><span class="sxs-lookup"><span data-stu-id="69cbc-115">To disable visual styles in C#, open Program.cs and comment out `Application.EnableVisualStyles();`.</span></span> <span data-ttu-id="69cbc-116">Дополнительные сведения о стилях см. в разделе [как: включить визуальные стили XP Windows](http://msdn.microsoft.com/en-us/0a038ade-31cf-4e56-9cfe-7a1e6b83b57f).</span><span class="sxs-lookup"><span data-stu-id="69cbc-116">For more information about visual styles, see [How to: Enable Windows XP Visual Styles](http://msdn.microsoft.com/en-us/0a038ade-31cf-4e56-9cfe-7a1e6b83b57f).</span></span>  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a><span data-ttu-id="69cbc-117">Для отображения текущей даты в нижней части элемента управления</span><span class="sxs-lookup"><span data-stu-id="69cbc-117">To display the current date at the bottom of the control</span></span>  
  
-   <span data-ttu-id="69cbc-118">Задайте для свойства <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="69cbc-118">Set the <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> property to `true`.</span></span> <span data-ttu-id="69cbc-119">В приведенном ниже примере переключение между отображением и скрытием текущей даты происходит при двойном щелчке формы.</span><span class="sxs-lookup"><span data-stu-id="69cbc-119">The example below toggles between displaying and omitting today's date when the form is double-clicked.</span></span>  
  
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
  
     <span data-ttu-id="69cbc-120">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="69cbc-120">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a><span data-ttu-id="69cbc-121">Чтобы отображать номера недель</span><span class="sxs-lookup"><span data-stu-id="69cbc-121">To display week numbers</span></span>  
  
-   <span data-ttu-id="69cbc-122">Задайте для свойства <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="69cbc-122">Set the <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> property to `true`.</span></span> <span data-ttu-id="69cbc-123">Это свойство можно задать в коде или в окне «Свойства».</span><span class="sxs-lookup"><span data-stu-id="69cbc-123">You can set this property either in code or in the Properties window.</span></span>  
  
     <span data-ttu-id="69cbc-124">Номера недель отображаются в отдельном столбце слева от первого дня недели.</span><span class="sxs-lookup"><span data-stu-id="69cbc-124">Week numbers appear in a separate column to the left of the first day of the week.</span></span>  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="69cbc-125">См. также</span><span class="sxs-lookup"><span data-stu-id="69cbc-125">See Also</span></span>  
 [<span data-ttu-id="69cbc-126">Элемент управления MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="69cbc-126">MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [<span data-ttu-id="69cbc-127">Практическое руководство. Выбор диапазона дат в элементе управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="69cbc-127">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 [<span data-ttu-id="69cbc-128">Практическое руководство. Отображение определенных дней полужирным шрифтом в элементе управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="69cbc-128">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)  
 [<span data-ttu-id="69cbc-129">Практическое руководство. Отображение более чем одного месяца в элементе управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="69cbc-129">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
