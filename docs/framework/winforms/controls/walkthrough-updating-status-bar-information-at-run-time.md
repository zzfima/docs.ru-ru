---
title: Пошаговое руководство. Обновление строки состояния во время выполнения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], updating at run time
- status bars [Windows Forms], refreshing panels
- StatusBar control [Windows Forms], refreshing panels
- panels [Windows Forms], refreshing status bar
ms.assetid: cc2abb06-c082-49f7-a5a3-2fd1bbcb58d1
ms.openlocfilehash: f1d22079dfa3a6452efb74ef57530bb43e059a4a
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197105"
---
# <a name="walkthrough-updating-status-bar-information-at-run-time"></a>Пошаговое руководство. Обновление строки состояния во время выполнения
> [!IMPORTANT]
> <xref:System.Windows.Forms.StatusStrip> и <xref:System.Windows.Forms.ToolStripStatusLabel> элементы управления заменяют и добавляют функции в элементы управления <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel>. Однако элементы управления <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> сохраняются как для обратной совместимости, так и для будущего использования, если вы решили.  
  
 Часто программа требует динамического обновления содержимого панелей строки состояния в среде выполнения с учетом изменений в состоянии приложения или других взаимодействий с пользователем. Это обычный способ сообщить пользователям о том, что CAPS LOCK, NUM LOCK или SCROLL LOCK включен, или сообщить ему дату или время в удобном формате.  
  
 В следующем примере для размещения часов будет использоваться экземпляр класса <xref:System.Windows.Forms.StatusBarPanel>.  
  
### <a name="to-get-the-status-bar-ready-for-updating"></a>Получение строки состояния, готовой для обновления  
  
1. Создание новой формы Windows Forms.  
  
2. Добавьте элемент управления <xref:System.Windows.Forms.StatusBar> в форму. Дополнительные сведения см. в разделе [Практическое руководство. Добавление элементов управления в формы Windows Forms](how-to-add-controls-to-windows-forms.md).  
  
3. Добавьте панель строки состояния в элемент управления <xref:System.Windows.Forms.StatusBar>. Дополнительные сведения см. в разделе [Практическое руководство. Добавление панелей в элемент управления StatusBar](how-to-add-panels-to-a-statusbar-control.md).  
  
4. Для элемента управления <xref:System.Windows.Forms.StatusBar>, добавленного в форму, задайте для свойства <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> значение `true`.  
  
5. Добавьте в форму компонент <xref:System.Windows.Forms.Timer> Windows Forms.  
  
    > [!NOTE]
    > Компонент <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> Windows Forms предназначен для среды Windows Forms. Если вам требуется таймер, подходящий для серверной среды, см. раздел [Общие сведения о серверных таймерах](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
6. Задайте для свойства <xref:System.Windows.Forms.Timer.Enabled%2A> значение `true`.  
  
7. Задайте для свойства <xref:System.Windows.Forms.Timer.Interval%2A> <xref:System.Windows.Forms.Timer> значение 30000.  
  
    > [!NOTE]
    > Для свойства <xref:System.Windows.Forms.Timer.Interval%2A> компонента <xref:System.Windows.Forms.Timer> устанавливается значение 30 секунд (30 000 миллисекунд), чтобы гарантировать, что в отображаемое время отображается точное время.  
  
### <a name="to-implement-the-timer-to-update-the-status-bar"></a>Реализация таймера для обновления строки состояния  
  
1. Вставьте следующий код в обработчик событий компонента <xref:System.Windows.Forms.Timer>, чтобы обновить панель элемента управления <xref:System.Windows.Forms.StatusBar>.  
  
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
  
     Теперь вы готовы запустить приложение и увидеть, как работают часы в панели строки состояния.  
  
### <a name="to-test-the-application"></a>Тестирование приложения  
  
1. Выполните отладку приложения и нажмите клавишу F5, чтобы его запустить. Дополнительные сведения об отладке см. в разделе [Отладка в Visual Studio](/visualstudio/debugger/debugger-feature-tour).  
  
    > [!NOTE]
    > Часы появятся в строке состояния примерно через 30 секунд. Это необходимо для того, чтобы время отображалось максимально точно. И наоборот, чтобы часы появились раньше, можно уменьшить значение свойства <xref:System.Windows.Forms.Timer.Interval%2A>, установленного на шаге 7 в предыдущей процедуре.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Практическое руководство. Добавление панелей в элемент управления StatusBar](how-to-add-panels-to-a-statusbar-control.md)
- [Практическое руководство. Идентификация панели элемента управления StatusBar, которую щелкнул пользователь, в Windows Forms](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [Общие сведения об элементе управления StatusBar](statusbar-control-overview-windows-forms.md)
