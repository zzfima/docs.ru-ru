---
title: Задание и возврат дат с помощью элемента управления DateTimePicker
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- dates [Windows Forms], setting in DateTimePicker
- DateTimePicker control [Windows Forms], setting and returning dates
- examples [Windows Forms], DateTimePicker control
ms.assetid: a8a48d68-e4b5-426e-9764-51230fc9acd2
ms.openlocfilehash: 1e0aa58e98748ccde9411f0f4871adbae3a5f14d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747109"
---
# <a name="how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="d5be1-102">Практическое руководство. Отображение и ввод дат с помощью элемента управления DateTimePicker в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d5be1-102">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="d5be1-103">Текущая выбранная дата или время в элементе управления Windows Forms <xref:System.Windows.Forms.DateTimePicker> определяется свойством <xref:System.Windows.Forms.DateTimePicker.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="d5be1-103">The currently selected date or time in the Windows Forms <xref:System.Windows.Forms.DateTimePicker> control is determined by the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property.</span></span> <span data-ttu-id="d5be1-104">Перед отображением элемента управления можно задать свойство <xref:System.Windows.Forms.DateTimePicker.Value%2A> (например, во время разработки или в виде событий <xref:System.Windows.Forms.Form.Load>) для определения даты, которая изначально будет выбрана в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="d5be1-104">You can set the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property before the control is displayed (for example, at design time or in the form's <xref:System.Windows.Forms.Form.Load> event) to determine which date will be initially selected in the control.</span></span> <span data-ttu-id="d5be1-105">По умолчанию в свойстве <xref:System.Windows.Forms.DateTimePicker.Value%2A> элемента управления установлена текущая дата.</span><span class="sxs-lookup"><span data-stu-id="d5be1-105">By default, the control's <xref:System.Windows.Forms.DateTimePicker.Value%2A> is set to the current date.</span></span> <span data-ttu-id="d5be1-106">Если свойство <xref:System.Windows.Forms.DateTimePicker.Value%2A> элемента управления изменяется в коде, элемент управления автоматически обновляется, отображая новое значение в форме.</span><span class="sxs-lookup"><span data-stu-id="d5be1-106">If you change the control's <xref:System.Windows.Forms.DateTimePicker.Value%2A> in code, the control is automatically updated on the form to reflect the new setting.</span></span>  
  
 <span data-ttu-id="d5be1-107">Свойство <xref:System.Windows.Forms.DateTimePicker.Value%2A> возвращает структуру <xref:System.DateTime>, которая является его значением.</span><span class="sxs-lookup"><span data-stu-id="d5be1-107">The <xref:System.Windows.Forms.DateTimePicker.Value%2A> property returns a <xref:System.DateTime> structure as its value.</span></span> <span data-ttu-id="d5be1-108">Существует несколько свойств структуры <xref:System.DateTime>, возвращающих определенные сведения об отображаемой дате.</span><span class="sxs-lookup"><span data-stu-id="d5be1-108">There are several properties of the <xref:System.DateTime> structure that return specific information about the displayed date.</span></span> <span data-ttu-id="d5be1-109">Эти свойства можно использовать только для возврата значения; не используйте их для задания значения.</span><span class="sxs-lookup"><span data-stu-id="d5be1-109">These properties can only be used to return a value; do not use them to set a value.</span></span>  
  
- <span data-ttu-id="d5be1-110">Для значений даты свойства <xref:System.DateTime.Month%2A>, <xref:System.DateTime.Day%2A> и <xref:System.DateTime.Year%2A> возвращают целочисленные значения в единицах времени выбранной даты.</span><span class="sxs-lookup"><span data-stu-id="d5be1-110">For date values, the <xref:System.DateTime.Month%2A>, <xref:System.DateTime.Day%2A>, and <xref:System.DateTime.Year%2A> properties return integer values for those time units of the selected date.</span></span> <span data-ttu-id="d5be1-111">Свойство <xref:System.DateTime.DayOfWeek%2A> возвращает значение, указывающее выбранный день недели (возможные значения указаны в перечислении <xref:System.DayOfWeek>).</span><span class="sxs-lookup"><span data-stu-id="d5be1-111">The <xref:System.DateTime.DayOfWeek%2A> property returns a value indicating the selected day of the week (possible values are listed in the <xref:System.DayOfWeek> enumeration).</span></span>  
  
- <span data-ttu-id="d5be1-112">Для значений времени свойства <xref:System.DateTime.Hour%2A>, <xref:System.DateTime.Minute%2A>, <xref:System.DateTime.Second%2A> и <xref:System.DateTime.Millisecond%2A> возвращают целочисленные значения для единиц времени.</span><span class="sxs-lookup"><span data-stu-id="d5be1-112">For time values, the <xref:System.DateTime.Hour%2A>, <xref:System.DateTime.Minute%2A>, <xref:System.DateTime.Second%2A>, and <xref:System.DateTime.Millisecond%2A> properties return integer values for those time units.</span></span> <span data-ttu-id="d5be1-113">Чтобы настроить отображение времени в элементе управления, см. раздел [как отобразить время с помощью элемента управления DateTimePicker](how-to-display-time-with-the-datetimepicker-control.md).</span><span class="sxs-lookup"><span data-stu-id="d5be1-113">To configure the control to display times, see [How to: Display Time with the DateTimePicker Control](how-to-display-time-with-the-datetimepicker-control.md).</span></span>  
  
### <a name="to-set-the-date-and-time-value-of-the-control"></a><span data-ttu-id="d5be1-114">Указание значения даты и времени элемента управления</span><span class="sxs-lookup"><span data-stu-id="d5be1-114">To set the date and time value of the control</span></span>  
  
- <span data-ttu-id="d5be1-115">Установите для свойства <xref:System.Windows.Forms.DateTimePicker.Value%2A> значение даты или времени.</span><span class="sxs-lookup"><span data-stu-id="d5be1-115">Set the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property to a date or time value.</span></span>  
  
    ```vb  
    DateTimePicker1.Value = New DateTime(2001, 10, 20)  
    ```  
  
    ```csharp  
    dateTimePicker1.Value = new DateTime(2001, 10, 20);  
    ```  
  
    ```cpp  
    dateTimePicker1->Value = DateTime(2001, 10, 20);  
    ```  
  
### <a name="to-return-the-date-and-time-value"></a><span data-ttu-id="d5be1-116">Возврат значения даты и времени</span><span class="sxs-lookup"><span data-stu-id="d5be1-116">To return the date and time value</span></span>  
  
- <span data-ttu-id="d5be1-117">Вызовите свойство <xref:System.Windows.Forms.DateTimePicker.Text%2A> для возврата всего значения в формате элемента управления или вызовите соответствующий метод свойства <xref:System.Windows.Forms.DateTimePicker.Value%2A> для возврата части значения.</span><span class="sxs-lookup"><span data-stu-id="d5be1-117">Call the <xref:System.Windows.Forms.DateTimePicker.Text%2A> property to return the entire value as formatted in the control, or call the appropriate method of the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property to return a part of the value.</span></span> <span data-ttu-id="d5be1-118">Используйте <xref:System.Windows.Forms.DateTimePicker.ToString%2A> для преобразования данных в строку, которую можно вывести пользователю.</span><span class="sxs-lookup"><span data-stu-id="d5be1-118">Use <xref:System.Windows.Forms.DateTimePicker.ToString%2A> to convert the information into a string that can be displayed to the user.</span></span>  
  
    ```vb  
    MessageBox.Show("The selected value is ", DateTimePicker1.Text)  
    MessageBox.Show("The day of the week is ",   
       DateTimePicker1.Value.DayOfWeek.ToString)  
    MessageBox.Show("Millisecond is: ",   
       DateTimePicker1.Value.Millisecond.ToString)  
    ```  
  
    ```csharp  
    MessageBox.Show ("The selected value is " +   
       dateTimePicker1.Text);  
    MessageBox.Show ("The day of the week is " +   
       dateTimePicker1.Value.DayOfWeek.ToString());  
    MessageBox.Show("Millisecond is: " +   
       dateTimePicker1.Value.Millisecond.ToString());  
    ```  
  
    ```cpp  
    MessageBox::Show (String::Concat("The selected value is ",  
       dateTimePicker1->Text));  
    MessageBox::Show (String::Concat("The day of the week is ",  
       dateTimePicker1->Value.DayOfWeek.ToString()));  
    MessageBox::Show(String::Concat("Millisecond is: ",  
       dateTimePicker1->Value.Millisecond.ToString()));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d5be1-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d5be1-119">See also</span></span>

- [<span data-ttu-id="d5be1-120">Элемент управления DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="d5be1-120">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
- [<span data-ttu-id="d5be1-121">Практическое руководство. Отображение даты в пользовательском формате с помощью элемента управления DateTimePicker в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d5be1-121">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)
