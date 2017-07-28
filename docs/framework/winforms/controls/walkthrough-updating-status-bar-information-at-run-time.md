---
title: "Пошаговое руководство. Обновление строки состояния во время выполнения | Microsoft Docs"
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
  - "панели, обновление строки состояния"
  - "строки состояния, обновление панелей"
  - "строки состояния, обновление во время выполнения"
  - "StatusBar - элемент управления [Windows Forms], обновление панелей"
ms.assetid: cc2abb06-c082-49f7-a5a3-2fd1bbcb58d1
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Пошаговое руководство. Обновление строки состояния во время выполнения
> [!IMPORTANT]
>  Элементы управления <xref:System.Windows.Forms.StatusStrip> и <xref:System.Windows.Forms.ToolStripStatusLabel> заменяют элементы управления <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> и расширяют их функциональные возможности; однако при необходимости элементы управления <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> можно сохранить для обратной совместимости и использования в будущем.  
  
 Часто при изменении состояния приложения или при вмешательстве пользователя программа требует динамическое обновление содержимого панелей строки состояния во время выполнения.  Обычно это используется для того, чтобы оповестить пользователя о нажатии клавиши CAPS LOCK, NUM LOCK или SCROLL LOCK или в удобном виде представлять сведения о дате или времени.  
  
 В следующем примере будет использовать экземпляр класса <xref:System.Windows.Forms.StatusBarPanel> для размещения часов.  
  
### Чтобы подготовить строку состояния к обновлению  
  
1.  Создание новой формы Windows Forms  
  
2.  Добавьте элемент управления <xref:System.Windows.Forms.StatusBar> в форму.  Дополнительные сведения см. в разделе [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
3.  Добавьте панель строки состояния в элемент управления <xref:System.Windows.Forms.StatusBar>.  Дополнительные сведения см. в разделе [Практическое руководство. Добавление панелей в элемент управления StatusBar](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md).  
  
4.  Свойству <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> элемента управления, добавленного в форму <xref:System.Windows.Forms.StatusBar>, присвойте значение `true`.  
  
5.  Добавьте компонент Windows Forms <xref:System.Windows.Forms.Timer> в форму.  
  
    > [!NOTE]
    >  Компонент Windows Forms <xref:System.Windows.Forms.Timer?displayProperty=fullName> предназначен для среды Windows Forms.  Если требуется таймер для серверной среды, см. раздел [Introduction to Server\-Based Timers](http://msdn.microsoft.com/ru-ru/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
6.  Установите для свойства <xref:System.Windows.Forms.Timer.Enabled%2A> значение `true`.  
  
7.  Установите свойство <xref:System.Windows.Forms.Timer.Interval%2A> элемента <xref:System.Windows.Forms.Timer> в значение 30000.  
  
    > [!NOTE]
    >  Для свойства <xref:System.Windows.Forms.Timer.Interval%2A> компонента <xref:System.Windows.Forms.Timer> задано значение "30 секунд" \(30000 миллисекунд\), чтобы гарантировать отображение точного времени.  
  
### Чтобы реализовать обновление таймера в строке состояния  
  
1.  Чтобы обновить панель элемента управления <xref:System.Windows.Forms.StatusBar>, вставьте в обработчик событий компонента <xref:System.Windows.Forms.Timer> следующий код.  
  
    ```vb  
    Private Sub Timer1_Tick(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
       StatusBar1.Panels(0).Text = Now.ToShortTimeString  
    End Sub  
  
    ```  
  
    ```csharp  
    private void timer1_Tick(object sender, System.EventArgs e)  
    {  
       statusBar1.Panels[0].Text = DateTime.Now.ToShortTimeString();  
    }  
  
    ```  
  
    ```cpp  
    private:  
      System::Void timer1_Tick(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        statusBar1->Panels[0]->Text =  
          DateTime::Now.ToShortTimeString();  
      }  
    ```  
  
     Теперь все готово к запуску приложения. Необходимо понаблюдать за часами, работающими в панели строки состояния.  
  
### Тестирование приложения  
  
1.  Запустите отладку приложения и нажмите клавишу F5 для запуска приложения.  Дополнительные сведения об отладке см. в разделе [Отладка в Visual Studio](../Topic/Debugging%20in%20Visual%20Studio.md).  
  
    > [!NOTE]
    >  Часы появятся в строке состояния примерно через 30 секунд.  Это необходимо для отображения наиболее точного времени.  С другой стороны, чтобы часы появились раньше, можно уменьшить значение свойства <xref:System.Windows.Forms.Timer.Interval%2A>, которое было задано на шаге 7 в предыдущей процедуры.  
  
## См. также  
 <xref:System.Windows.Forms.StatusBar>   
 <xref:System.Windows.Forms.ToolStripStatusLabel>   
 [Практическое руководство. Добавление панелей в элемент управления StatusBar](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md)   
 [Практическое руководство. Идентификация панели элемента управления StatusBar, которую щелкнул пользователь, в Windows Forms](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)   
 [Общие сведения об элементе управления StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)