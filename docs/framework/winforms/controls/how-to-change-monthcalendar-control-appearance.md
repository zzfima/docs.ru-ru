---
title: Как выполнить Изменение внешнего вида управления Windows Forms MonthCalendar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
ms.openlocfilehash: b7f321c1557bc7ea19213f2fc67767fe56328cf4
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55258931"
---
# <a name="how-to-change-the-windows-forms-monthcalendar-controls-appearance"></a><span data-ttu-id="40272-102">Как выполнить Изменение внешнего вида управления Windows Forms MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="40272-102">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>
<span data-ttu-id="40272-103">Windows Forms <xref:System.Windows.Forms.MonthCalendar> элемент управления позволяет настраивать внешний вид календаря во многих отношениях.</span><span class="sxs-lookup"><span data-stu-id="40272-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control allows you to customize the calendar's appearance in many ways.</span></span> <span data-ttu-id="40272-104">Например можно установить цветовую схему и выберите для отображения или скрытия номеров недель или текущей даты.</span><span class="sxs-lookup"><span data-stu-id="40272-104">For example, you can set the color scheme and choose to display or hide week numbers and the current date.</span></span>  
  
### <a name="to-change-the-month-calendars-color-scheme"></a><span data-ttu-id="40272-105">Чтобы изменить цветовую схему месячный календарь</span><span class="sxs-lookup"><span data-stu-id="40272-105">To change the month calendar's color scheme</span></span>  
  
-   <span data-ttu-id="40272-106">Задать такие свойства как <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> и <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="40272-106">Set properties such as <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> and <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span></span> <span data-ttu-id="40272-107"><xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> Также определяет цвет шрифта для дней недели.</span><span class="sxs-lookup"><span data-stu-id="40272-107">The <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> property also determines the font color for the days of the week.</span></span> <span data-ttu-id="40272-108"><xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> Свойство определяет цвет дат, которые предшествуют и следуют за месяц, отображаемый или месяцев.</span><span class="sxs-lookup"><span data-stu-id="40272-108">The <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> property determines the color of the dates that precede and follow the displayed month or months.</span></span>  
  
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
    >  <span data-ttu-id="40272-109">Начиная с Windows Vista и в зависимости от темы, настроить некоторые параметры могут не изменяться внешний вид календаря.</span><span class="sxs-lookup"><span data-stu-id="40272-109">Starting with Windows Vista and depending on the theme, setting some properties might not change the appearance of the calendar.</span></span> <span data-ttu-id="40272-110">Например, если Windows настроен на использование темы Aero, установка <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, или <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> свойства не влияет.</span><span class="sxs-lookup"><span data-stu-id="40272-110">For example, if Windows is set to use the Aero theme, setting the <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, or <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> properties has no effect.</span></span> <span data-ttu-id="40272-111">Это обусловлено обновленную версию календаря визуализируется с внешний вид, который является производным от текущей темы операционной системы во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="40272-111">This is because an updated version of the calendar is rendered with an appearance that is derived at run time from the current operating system theme.</span></span> <span data-ttu-id="40272-112">Если вы хотите использовать эти свойства и включить более раннюю версию календаря, можно отключить визуальные стили для приложения.</span><span class="sxs-lookup"><span data-stu-id="40272-112">If you want to use these properties and enable the earlier version of the calendar, you can disable visual styles for your application.</span></span> <span data-ttu-id="40272-113">Отключение визуальных стилей может повлиять на внешний вид и поведение других элементов управления в приложении.</span><span class="sxs-lookup"><span data-stu-id="40272-113">Disabling visual styles might affect the appearance and behavior of other controls in your application.</span></span> <span data-ttu-id="40272-114">Чтобы отключить визуальные стили в Visual Basic, откройте конструктор проектов и снимите флажок **включить визуальные стили XP** "флажок".</span><span class="sxs-lookup"><span data-stu-id="40272-114">To disable visual styles in Visual Basic, open the Project Designer and uncheck the **Enable XP visual styles** check box.</span></span> <span data-ttu-id="40272-115">Чтобы отключить визуальные стили в C#, откройте файл Program.cs и закомментируйте `Application.EnableVisualStyles();`.</span><span class="sxs-lookup"><span data-stu-id="40272-115">To disable visual styles in C#, open Program.cs and comment out `Application.EnableVisualStyles();`.</span></span> <span data-ttu-id="40272-116">Дополнительные сведения о стилях см. в разделе [как: Включение визуальных стилей Windows XP](https://msdn.microsoft.com/library/0a038ade-31cf-4e56-9cfe-7a1e6b83b57f).</span><span class="sxs-lookup"><span data-stu-id="40272-116">For more information about visual styles, see [How to: Enable Windows XP Visual Styles](https://msdn.microsoft.com/library/0a038ade-31cf-4e56-9cfe-7a1e6b83b57f).</span></span>  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a><span data-ttu-id="40272-117">Чтобы отобразить текущую дату в нижней части элемента управления</span><span class="sxs-lookup"><span data-stu-id="40272-117">To display the current date at the bottom of the control</span></span>  
  
-   <span data-ttu-id="40272-118">Задайте для свойства <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="40272-118">Set the <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> property to `true`.</span></span> <span data-ttu-id="40272-119">В приведенном ниже примере переключение между отображением и скрытием текущей даты, когда форма будет выполнен двойной щелчок.</span><span class="sxs-lookup"><span data-stu-id="40272-119">The example below toggles between displaying and omitting today's date when the form is double-clicked.</span></span>  
  
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
  
     <span data-ttu-id="40272-120">(Visual C# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="40272-120">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a><span data-ttu-id="40272-121">Для отображения номера недель</span><span class="sxs-lookup"><span data-stu-id="40272-121">To display week numbers</span></span>  
  
-   <span data-ttu-id="40272-122">Задайте для свойства <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="40272-122">Set the <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> property to `true`.</span></span> <span data-ttu-id="40272-123">Это свойство можно задать в коде или в окне «Свойства».</span><span class="sxs-lookup"><span data-stu-id="40272-123">You can set this property either in code or in the Properties window.</span></span>  
  
     <span data-ttu-id="40272-124">Номера недель отображаются в отдельном столбце слева от первого дня недели.</span><span class="sxs-lookup"><span data-stu-id="40272-124">Week numbers appear in a separate column to the left of the first day of the week.</span></span>  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="40272-125">См. также</span><span class="sxs-lookup"><span data-stu-id="40272-125">See also</span></span>
- [<span data-ttu-id="40272-126">Элемент управления MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="40272-126">MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="40272-127">Практическое руководство. Выбор диапазона дат в элементе управления Windows Forms MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="40272-127">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="40272-128">Практическое руководство. Отображение определенных дней полужирным шрифтом с Windows Forms в элементе управления MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="40272-128">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [<span data-ttu-id="40272-129">Практическое руководство. Отображение более чем одного месяца в элементе управления Windows Forms MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="40272-129">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
