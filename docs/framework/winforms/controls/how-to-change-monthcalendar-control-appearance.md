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
# <a name="how-to-change-the-windows-forms-monthcalendar-controls-appearance"></a>Практическое руководство. Изменение внешнего вида элемента управления MonthCalendar в Windows Forms
Элемент управления <xref:System.Windows.Forms.MonthCalendar> Windows Forms позволяет настраивать внешний вид календаря различными способами. Например, можно задать цветовую схему и выбрать отображение или скрытие номеров недель и текущей даты.  
  
### <a name="to-change-the-month-calendars-color-scheme"></a>Изменение цветовой схемы календаря на месяц  
  
- Задайте свойства, такие <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>как <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> , <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>и. <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> Свойство также определяет цвет шрифта для дней недели. <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> Свойство определяет цвет дат, которые предшествуют отображаемому месяцу или месяцам и следуют за ним.  
  
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
    > Начиная с Windows Vista и в зависимости от темы, установка некоторых свойств может не изменить внешний вид календаря. Например, если в <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>Windows настроено использование темы Aero, установка свойств, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>или <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> не оказывает никакого влияния. Это связано с тем, что обновленная версия календаря отображается с внешним видом, полученным во время выполнения из текущей темы операционной системы. Если вы хотите использовать эти свойства и включить более раннюю версию календаря, можно отключить стили оформления для приложения. Отключение стилей оформления может повлиять на внешний вид и поведение других элементов управления в приложении. Чтобы отключить стили оформления в Visual Basic, откройте конструктор проектов и снимите флажок **включить стили Visual XP** . Чтобы отключить стили оформления в C#, откройте Program.cs и закомментируйте комментарий `Application.EnableVisualStyles();`. Дополнительные сведения о стилях оформления см. в разделе [Включение визуальных стилей](/windows/desktop/controls/cookbook-overview).  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a>Отображение текущей даты в нижней части элемента управления  
  
- Задайте для свойства <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> значение `true`. Приведенный ниже пример переключает отображение и пропуск текущей даты при двойном щелчке на форме.  
  
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
  
     (Визуальный C#элемент C++, визуальный элемент) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a>Отображение номеров недель  
  
- Задайте для свойства <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> значение `true`. Это свойство можно задать либо в коде, либо в окно свойств.  
  
     Номера недель отображаются в отдельном столбце слева от первого дня недели.  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a>См. также

- [Элемент управления MonthCalendar](monthcalendar-control-windows-forms.md)
- [Практическое руководство. Выбор диапазона дат в элементе управления Windows Forms MonthCalendar](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Практическое руководство. Отображение отдельных дней полужирным шрифтом с помощью элемента управления Windows Forms MonthCalendar](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [Практическое руководство. Отображение более одного месяца в элементе управления Windows Forms MonthCalendar](display-more-than-one-month-wf-monthcalendar-control.md)
