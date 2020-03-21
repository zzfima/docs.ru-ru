---
title: Ассоциированное меню ярлыка с компонентом NotifyIcon
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], for background processes
- NotifyIcon component [Windows Forms], associating shortcut menus
- shortcut menus [Windows Forms], for background processes
ms.assetid: d68f3926-08d3-4f7d-949f-1981b29cf188
ms.openlocfilehash: 15a4a06726de348745e5eef03217d693db496a42
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182255"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a>Практическое руководство. Связывание контекстного меню с компонентом NotifyIcon в Windows Forms
> [!NOTE]
> Хотя <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> и заменить и <xref:System.Windows.Forms.MainMenu> добавить функциональность и <xref:System.Windows.Forms.ContextMenu> элементы управления предыдущих версий, <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> сохраняются как для обратной совместимости и будущего использования, если вы выбираете.  
  
 Компонент <xref:System.Windows.Forms.NotifyIcon> отображает значок в области уведомления о состоянии панели задач. Как правило, приложения позволяют нажать на эту иконку, чтобы отправить команды в приложение, которое оно представляет. Связывая <xref:System.Windows.Forms.ContextMenu> компонент с <xref:System.Windows.Forms.NotifyIcon> компонентом, можно добавить эту функциональность в приложения.  
  
> [!NOTE]
> Если вы хотите, чтобы ваше приложение было сведено к <xref:System.Windows.Forms.NotifyIcon> минимуму при запуске при отображении <xref:System.Windows.Forms.Form.WindowState%2A> экземпляра компонента в панели задач, установите свойство основной формы <xref:System.Windows.Forms.FormWindowState.Minimized> и убедитесь, что свойство <xref:System.Windows.Forms.NotifyIcon> компонента <xref:System.Windows.Forms.NotifyIcon.Visible%2A> настроено на `true`.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a>Связать меню ярлыка с компонентом NotifyIcon во время проектирования  
  
1. Добавьте <xref:System.Windows.Forms.NotifyIcon> компонент в форму и установите важные <xref:System.Windows.Forms.NotifyIcon.Icon%2A> <xref:System.Windows.Forms.NotifyIcon.Visible%2A> свойства, такие как свойства и свойства.  
  
     Для получения дополнительной информации [см. Как: Добавить значки приложений в панель задач с компонентом NotifyIcon Windows.](app-icons-to-the-taskbar-with-wf-notifyicon.md)  
  
2. Добавьте <xref:System.Windows.Forms.ContextMenu> компонент в форму Windows.  
  
     Добавьте элементы меню в меню ярлыка, представляющие команды, которые вы хотите сделать доступными во время выполнения. Это также хорошее время, чтобы добавить улучшения меню к этим пунктам меню, таким как ключи доступа.  
  
3. Установите <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> свойство <xref:System.Windows.Forms.NotifyIcon> компонента в меню ярлыка, которое вы добавили.  
  
     С помощью этого набора свойств меню ярлыка будет отображаться при нажатии значка на панели задач.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a>Связать меню ярлыка с компонентом NotifyIcon программно  
  
1. Создайте экземпляр <xref:System.Windows.Forms.NotifyIcon> класса и <xref:System.Windows.Forms.ContextMenu> класса с любыми настройками свойств,<xref:System.Windows.Forms.NotifyIcon.Icon%2A> <xref:System.Windows.Forms.NotifyIcon.Visible%2A> необходимыми <xref:System.Windows.Forms.NotifyIcon> для приложения (и <xref:System.Windows.Forms.ContextMenu> свойствами для компонента, пунктами меню для компонента).  
  
2. Установите <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> свойство <xref:System.Windows.Forms.NotifyIcon> компонента в меню ярлыка, которое вы добавили.  
  
     С помощью этого набора свойств меню ярлыка будет отображаться при нажатии значка на панели задач.  
  
    > [!NOTE]
    > Следующий пример кода создает основную структуру меню. Вам нужно будет настроить выбор меню для тех, которые соответствуют приложению, которое вы разрабатываете. Кроме того, вы хотите написать <xref:System.Windows.Forms.MenuItem.Click> код для обработки событий для этих элементов меню.  
  
    ```vb  
    Public ContextMenu1 As New ContextMenu  
    Public NotifyIcon1 As New NotifyIcon  
  
    Public Sub CreateIconMenuStructure()  
       ' Add menu items to shortcut menu.  
       ContextMenu1.MenuItems.Add("&Open Application")  
       ContextMenu1.MenuItems.Add("S&uspend Application")  
       ContextMenu1.MenuItems.Add("E&xit")  
  
       ' Set properties of NotifyIcon component.  
       NotifyIcon1.Icon = New System.Drawing.Icon _
          (System.Environment.GetFolderPath _
          (System.Environment.SpecialFolder.Personal)  _
          & "\Icon.ico")  
       NotifyIcon1.Text = "Right-click me!"  
       NotifyIcon1.Visible = True  
       NotifyIcon1.ContextMenu = ContextMenu1  
    End Sub  
    ```  
  
```csharp  
public NotifyIcon notifyIcon1 = new NotifyIcon();  
public ContextMenu contextMenu1 = new ContextMenu();  
  
public void createIconMenuStructure()  
{  
   // Add menu items to shortcut menu.  
   contextMenu1.MenuItems.Add("&Open Application");  
   contextMenu1.MenuItems.Add("S&uspend Application");  
   contextMenu1.MenuItems.Add("E&xit");  
  
   // Set properties of NotifyIcon component.  
   notifyIcon1.Icon = new System.Drawing.Icon  
      (System.Environment.GetFolderPath  
      (System.Environment.SpecialFolder.Personal)  
      + @"\Icon.ico");  
   notifyIcon1.Visible = true;  
   notifyIcon1.Text = "Right-click me!";  
   notifyIcon1.Visible = true;  
   notifyIcon1.ContextMenu = contextMenu1;  
}  
```  
  
```cpp  
public:  
   System::Windows::Forms::NotifyIcon ^ notifyIcon1;  
   System::Windows::Forms::ContextMenu ^ contextMenu1;  
  
   void createIconMenuStructure()  
   {  
      // Add menu items to shortcut menu.  
      contextMenu1->MenuItems->Add("&Open Application");  
      contextMenu1->MenuItems->Add("S&uspend Application");  
      contextMenu1->MenuItems->Add("E&xit");  
  
      // Set properties of NotifyIcon component.  
      notifyIcon1->Icon = gcnew System::Drawing::Icon  
          (String::Concat(System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::Personal),  
          "\\Icon.ico"));  
      notifyIcon1->Text = "Right-click me!";  
      notifyIcon1->Visible = true;  
      notifyIcon1->ContextMenu = contextMenu1;  
   }  
```  
  
> [!NOTE]
> Вы должны `notifyIcon1` инициализировать и `contextMenu1,` что вы можете сделать, включив следующие утверждения в конструктор вашей формы:  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [Практическое руководство. Добавление значков приложения на панель задач с помощью компонента NotifyIcon в Windows Forms](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [Компонент NotifyIcon](notifyicon-component-windows-forms.md)
- [Общие сведения о компоненте управления NotifyIcon](notifyicon-component-overview-windows-forms.md)
