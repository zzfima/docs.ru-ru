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
ms.openlocfilehash: 670746a1b964a85bc5136d976d831c6848466797
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930988"
---
# <a name="walkthrough-updating-status-bar-information-at-run-time"></a>Пошаговое руководство. Обновление строки состояния во время выполнения
> [!IMPORTANT]
> <xref:System.Windows.Forms.StatusBarPanel> <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBarPanel> Элементы управления <xref:System.Windows.Forms.ToolStripStatusLabel> и заменяют и добавляют функциональные возможности в элементы управления и, однако, элементы управления и сохраняются для обратной совместимости и использования в будущем, если <xref:System.Windows.Forms.StatusStrip> выбрали.  
  
 Часто программа требует динамического обновления содержимого панелей строки состояния в среде выполнения с учетом изменений в состоянии приложения или других взаимодействий с пользователем. Это обычный способ сообщить пользователям о том, что CAPS LOCK, NUM LOCK или SCROLL LOCK включен, или сообщить ему дату или время в удобном формате.  
  
 В следующем примере для размещения часов будет использоваться экземпляр <xref:System.Windows.Forms.StatusBarPanel> класса.  
  
### <a name="to-get-the-status-bar-ready-for-updating"></a>Получение строки состояния, готовой для обновления  
  
1. Создание новой формы Windows Forms.  
  
2. Добавьте элемент управления <xref:System.Windows.Forms.StatusBar> в форму. Подробную информацию см. в разделе [Практическое руководство. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.  
  
3. Добавьте панель строки состояния в <xref:System.Windows.Forms.StatusBar> элемент управления. Подробную информацию см. в разделе [Практическое руководство. Добавление панелей в элемент управления](how-to-add-panels-to-a-statusbar-control.md)StatusBar.  
  
4. Для элемента управления, добавленного в форму, <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> задайте для `true`свойства значение. <xref:System.Windows.Forms.StatusBar>  
  
5. Добавьте в форму <xref:System.Windows.Forms.Timer> компонент Windows Forms.  
  
    > [!NOTE]
    > Компонент Windows Forms <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> предназначен для среды Windows Forms. Если вам требуется таймер, подходящий для серверной среды, см. раздел [Общие сведения о серверных таймерах](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
6. Задайте для свойства <xref:System.Windows.Forms.Timer.Enabled%2A> значение `true`.  
  
7. <xref:System.Windows.Forms.Timer> Присвойте <xref:System.Windows.Forms.Timer.Interval%2A> свойству значение 30000.  
  
    > [!NOTE]
    > Для <xref:System.Windows.Forms.Timer.Interval%2A> свойства<xref:System.Windows.Forms.Timer> компонента устанавливается значение 30 секунд (30 000 миллисекунд), чтобы гарантировать, что в отображаемое время отображается точное время.  
  
### <a name="to-implement-the-timer-to-update-the-status-bar"></a>Реализация таймера для обновления строки состояния  
  
1. Вставьте следующий код в обработчик <xref:System.Windows.Forms.Timer> событий компонента, чтобы обновить панель <xref:System.Windows.Forms.StatusBar> элемента управления.  
  
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
  
1. Выполните отладку приложения и нажмите клавишу F5, чтобы его запустить. Дополнительные сведения об отладке см. в разделе [Отладка в Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).  
  
    > [!NOTE]
    > Часы появятся в строке состояния примерно через 30 секунд. Это необходимо для того, чтобы время отображалось максимально точно. И наоборот, чтобы часы отображались быстрее, можно уменьшить значение <xref:System.Windows.Forms.Timer.Interval%2A> свойства, заданное на шаге 7 в предыдущей процедуре.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Практическое руководство. Добавление панелей в элемент управления StatusBar](how-to-add-panels-to-a-statusbar-control.md)
- [Практическое руководство. Определите, какая панель элемента управления Windows Forms StatusBar была нажата](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [Общие сведения об элементе управления StatusBar](statusbar-control-overview-windows-forms.md)
