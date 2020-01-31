---
title: Связывание контекстного меню с компонентом NotifyIcon
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
ms.openlocfilehash: 392c04f73feaec201033ad76f9419a0e070bec70
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742045"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a>Практическое руководство. Связывание контекстного меню с компонентом NotifyIcon в Windows Forms
> [!NOTE]
> Хотя <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenuStrip> заменить и добавить функции в <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> элементы управления предыдущих версий, <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> сохраняются для обратной совместимости и использования в будущем при выборе.  
  
 Компонент <xref:System.Windows.Forms.NotifyIcon> отображает значок в области уведомления о состоянии панели задач. Обычно приложения позволяют щелкнуть этот значок правой кнопкой мыши, чтобы отправить команды в приложение, которое оно представляет. Связав компонент <xref:System.Windows.Forms.ContextMenu> с компонентом <xref:System.Windows.Forms.NotifyIcon>, можно добавить эту функцию в приложения.  
  
> [!NOTE]
> Если необходимо, чтобы приложение было свернуто при запуске при отображении экземпляра компонента <xref:System.Windows.Forms.NotifyIcon> на панели задач, установите для свойства <xref:System.Windows.Forms.Form.WindowState%2A> главной формы значение <xref:System.Windows.Forms.FormWindowState.Minimized> и убедитесь, что для свойства <xref:System.Windows.Forms.NotifyIcon.Visible%2A> компонента <xref:System.Windows.Forms.NotifyIcon> задано значение `true`.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a>Связывание контекстного меню с компонентом NotifyIcon во время разработки  
  
1. Добавьте в форму компонент <xref:System.Windows.Forms.NotifyIcon> и задайте важные свойства, такие как свойства <xref:System.Windows.Forms.NotifyIcon.Icon%2A> и <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.  
  
     Дополнительные сведения см. в разделе [как добавить значки приложений на панель задач с помощью компонента Windows Forms NotifyIcon](app-icons-to-the-taskbar-with-wf-notifyicon.md).  
  
2. Добавьте <xref:System.Windows.Forms.ContextMenu> компонент в форму Windows Forms.  
  
     Добавьте пункты меню в контекстное меню, представляющее команды, которые необходимо сделать доступными во время выполнения. Кроме того, это очень удобно для добавления улучшений меню к этим пунктам меню, таким как ключи доступа.  
  
3. Задайте для свойства <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> компонента <xref:System.Windows.Forms.NotifyIcon> контекстное меню, которое вы добавили.  
  
     Если это свойство установлено, контекстное меню будет отображаться при нажатии значка на панели задач.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a>Связывание контекстного меню с компонентом NotifyIcon программным способом  
  
1. Создайте экземпляр класса <xref:System.Windows.Forms.NotifyIcon> и класс <xref:System.Windows.Forms.ContextMenu> с любыми настройками свойств для приложения (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> и <xref:System.Windows.Forms.NotifyIcon.Visible%2A> свойства для компонента <xref:System.Windows.Forms.NotifyIcon>, элементы меню для компонента <xref:System.Windows.Forms.ContextMenu>).  
  
2. Задайте для свойства <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> компонента <xref:System.Windows.Forms.NotifyIcon> контекстное меню, которое вы добавили.  
  
     Если это свойство установлено, контекстное меню будет отображаться при нажатии значка на панели задач.  
  
    > [!NOTE]
    > В следующем примере кода создается базовая структура меню. Вам потребуется настроить параметры меню для тех, которые соответствуют разрабатываемому приложению. Кроме того, необходимо написать код для управления событиями <xref:System.Windows.Forms.MenuItem.Click> для этих пунктов меню.  
  
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
> Необходимо инициализировать `notifyIcon1` и `contextMenu1,`, которые можно сделать, включив в конструктор формы следующие операторы:  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [Практическое руководство. Добавление значков приложения на панель задач с помощью компонента NotifyIcon в Windows Forms](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [Компонент NotifyIcon](notifyicon-component-windows-forms.md)
- [Общие сведения о компоненте управления NotifyIcon](notifyicon-component-overview-windows-forms.md)
