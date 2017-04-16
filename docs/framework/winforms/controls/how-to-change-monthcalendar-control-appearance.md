---
title: "Практическое руководство. Изменение внешнего вида элемента управления MonthCalendar в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "примеры [Windows Forms], Calendar - элементы управления"
  - "MonthBackColor - свойство"
  - "MonthCalendar - элемент управления [Windows Forms], форматирование изображения"
  - "TitleBackColor - свойство"
  - "TitleForeColor - свойство"
  - "TrailingForeColor - свойство"
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Практическое руководство. Изменение внешнего вида элемента управления MonthCalendar в Windows Forms
Предусмотрено множество возможностей настройки внешнего вида элемента управления Windows Forms <xref:System.Windows.Forms.MonthCalendar>.  Например, предоставляется возможность выбора цветовой схемы, а также отображения или скрытия номеров недель или текущей даты.  
  
### Чтобы изменить цветовую схему календаря  
  
-   Установите свойства <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> и <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.  Свойство <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> также определяет цвет шрифта для дней недели.  Свойство <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> определяет цвет дат, предшествующих и следующих за отображаемым месяцем или месяцами.  
  
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
    >  Начиная с Windows Vista и в зависимости от темы, при задании некоторых свойств внешний вид календаря может не изменяться.  Например, если ОС Windows настроена для использования темы Aero, задание свойств <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> или <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> не оказывает никакого влияния.  Это объясняется тем, что отображается внешний вид обновленной версии календаря, полученный во время выполнения от текущей темы операционной системы.  Если требуется использовать эти свойства и включить более раннюю версию календаря, можно отключить стили форматирования приложения.  Отключение стилей форматирования может повлиять на внешний вид и поведение других элементов управления приложения.  Чтобы отключить стили форматирования в Visual Basic, откройте конструктор проектов и снимите флажок **Включить XP\-стили визуального представления**.  Чтобы отключить стили форматирования в C\#, откройте Program.cs и закомментируйте `Application.EnableVisualStyles();`.  Дополнительные сведения о стилях форматирования см. в разделе [How to: Enable Windows XP Visual Styles](http://msdn.microsoft.com/ru-ru/0a038ade-31cf-4e56-9cfe-7a1e6b83b57f).  
  
### Чтобы отобразить текущую дату внизу элемента управления  
  
-   Задайте для свойства <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> значение `true`.  В приведенном ниже примере переключение между отображением и скрытием текущей даты происходит при выполнении двойного щелчка на форме.  
  
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
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Добавьте в конструктор формы следующий код, чтобы зарегистрировать обработчик событий.  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### Чтобы отобразить номера недель  
  
-   Задайте для свойства <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> значение `true`.  Это свойство можно задать в коде или в окне "Свойства".  
  
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
  
## См. также  
 [Элемент управления MonthCalendar](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)   
 [Практическое руководство. Выбор диапазона дат в элементе управления MonthCalendar в Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)   
 [Практическое руководство. Отображение определенных дней полужирным шрифтом в элементе управления MonthCalendar в Windows Forms](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)   
 [Практическое руководство. Отображение более чем одного месяца в элементе управления MonthCalendar в Windows Forms](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)