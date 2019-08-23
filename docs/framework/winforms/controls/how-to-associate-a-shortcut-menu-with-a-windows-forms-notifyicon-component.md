---
title: Практическое руководство. Связывание контекстного меню с компонентом NotifyIcon в Windows Forms
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
ms.openlocfilehash: bf5602d0526fdd97f0cc14382339095a793f13c3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922769"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a>Практическое руководство. Связывание контекстного меню с компонентом NotifyIcon в Windows Forms
> [!NOTE]
> Хотя <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> заменяют и добавляют функции к элементам управления и предыдущих версий и сохраняются для обратной совместимости и использования в будущем при выборе. <xref:System.Windows.Forms.ContextMenuStrip>  
  
 <xref:System.Windows.Forms.NotifyIcon> Компонент отображает значок в области уведомлений о состоянии панели задач. Обычно приложения позволяют щелкнуть этот значок правой кнопкой мыши, чтобы отправить команды в приложение, которое оно представляет. Связав <xref:System.Windows.Forms.ContextMenu> компонент<xref:System.Windows.Forms.NotifyIcon> с компонентом, можно добавить эту функцию в приложения.  
  
> [!NOTE]
> Если необходимо, чтобы приложение было свернуто при запуске при <xref:System.Windows.Forms.NotifyIcon> отображении экземпляра компонента на панели задач, установите <xref:System.Windows.Forms.Form.WindowState%2A> свойство основной формы в <xref:System.Windows.Forms.FormWindowState.Minimized> значение и убедитесь, <xref:System.Windows.Forms.NotifyIcon> что <xref:System.Windows.Forms.NotifyIcon.Visible%2A> свойство компонента имеет значение `true`.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a>Связывание контекстного меню с компонентом NotifyIcon во время разработки  
  
1. Добавьте в форму <xref:System.Windows.Forms.NotifyIcon.Icon%2A> <xref:System.Windows.Forms.NotifyIcon.Visible%2A> компонент и задайте важные свойства, такие как свойства и. <xref:System.Windows.Forms.NotifyIcon>  
  
     Дополнительные сведения см. в разделе [Практическое руководство. Добавьте значки приложений на панель задач с компонентом](app-icons-to-the-taskbar-with-wf-notifyicon.md)Windows Forms NotifyIcon.  
  
2. <xref:System.Windows.Forms.ContextMenu> Добавьте компонент в форму Windows Forms.  
  
     Добавьте пункты меню в контекстное меню, представляющее команды, которые необходимо сделать доступными во время выполнения. Кроме того, это очень удобно для добавления улучшений меню к этим пунктам меню, таким как ключи доступа.  
  
3. Присвойте <xref:System.Windows.Forms.NotifyIcon> свойству компонента значение, добавленное в контекстное меню. <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A>  
  
     Если это свойство установлено, контекстное меню будет отображаться при нажатии значка на панели задач.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a>Связывание контекстного меню с компонентом NotifyIcon программным способом  
  
1. Создайте экземпляр <xref:System.Windows.Forms.NotifyIcon> класса <xref:System.Windows.Forms.NotifyIcon> <xref:System.Windows.Forms.NotifyIcon.Icon%2A> <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.NotifyIcon.Visible%2A> и класс с любыми настройками свойств для приложения (и свойствами для компонента, элементы меню для элемента <xref:System.Windows.Forms.ContextMenu> компонент).  
  
2. Присвойте <xref:System.Windows.Forms.NotifyIcon> свойству компонента значение, добавленное в контекстное меню. <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A>  
  
     Если это свойство установлено, контекстное меню будет отображаться при нажатии значка на панели задач.  
  
    > [!NOTE]
    > В следующем примере кода создается базовая структура меню. Вам потребуется настроить параметры меню для тех, которые соответствуют разрабатываемому приложению. Кроме того, необходимо написать код для управления <xref:System.Windows.Forms.MenuItem.Click> событиями этих пунктов меню.  
  
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
> Для этого необходимо `notifyIcon1` выполнить `contextMenu1,` инициализацию, включив в конструктор формы следующие операторы:  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [Практическое руководство. Добавление значков приложений на панель задач с компонентом Windows Forms NotifyIcon](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [Компонент NotifyIcon](notifyicon-component-windows-forms.md)
- [Общие сведения о компоненте управления NotifyIcon](notifyicon-component-overview-windows-forms.md)
