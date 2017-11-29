---
title: "Практическое руководство. Связывание контекстного меню с компонентом NotifyIcon в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], for background processes
- NotifyIcon component [Windows Forms], associating shortcut menus
- shortcut menus [Windows Forms], for background processes
ms.assetid: d68f3926-08d3-4f7d-949f-1981b29cf188
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 985aa58056f4c4ec8f3042c682291508f1434ee0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a>Практическое руководство. Связывание контекстного меню с компонентом NotifyIcon в Windows Forms
> [!NOTE]
>  Несмотря на то что <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenuStrip> заменить и добавить функциональные возможности в <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> элементы управления предыдущих версий, <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> можно сохранить для обратной совместимости и использования в будущем, если выбрать.  
  
 <xref:System.Windows.Forms.NotifyIcon> Компонент отображает значок в области уведомлений панели задач. Как правило приложения позволяют щелкните правой кнопкой мыши этот значок, чтобы отправлять команды в приложение, которое он представляет. Связав <xref:System.Windows.Forms.ContextMenu> компонент с <xref:System.Windows.Forms.NotifyIcon> компонента, эти функции можно добавить в приложения.  
  
> [!NOTE]
>  Если требуется, чтобы свести к минимуму во время запуска при отображении экземпляра приложения <xref:System.Windows.Forms.NotifyIcon> набор компонентов на панели задач главной формы <xref:System.Windows.Forms.Form.WindowState%2A> свойства <xref:System.Windows.Forms.FormWindowState.Minimized> и убедитесь, что <xref:System.Windows.Forms.NotifyIcon> компонента <xref:System.Windows.Forms.NotifyIcon.Visible%2A> свойство имеет значение `true`.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a>Чтобы связать контекстное меню с компонентом NotifyIcon во время разработки  
  
1.  Добавить <xref:System.Windows.Forms.NotifyIcon> компонента в форму и задайте важные свойства, такие как <xref:System.Windows.Forms.NotifyIcon.Icon%2A> и <xref:System.Windows.Forms.NotifyIcon.Visible%2A> свойства.  
  
     Дополнительные сведения см. в разделе [как: добавление значков приложения на панель задач с помощью компонента NotifyIcon в Windows Forms](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).  
  
2.  Добавить <xref:System.Windows.Forms.ContextMenu> в форме Windows Forms.  
  
     Добавление элементов меню в контекстное меню, представляющие команды, что вы хотите сделать доступными во время выполнения. Это подходящий момент, чтобы добавить дополнительные функции меню этих пунктов меню, таких как ключи доступа.  
  
3.  Задать <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> свойство <xref:System.Windows.Forms.NotifyIcon> в контекстное меню, которое вы добавили компонент.  
  
     При щелчке значка на панели задач, отображается в контекстном меню.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a>Чтобы связать контекстное меню с компонентом NotifyIcon программным способом  
  
1.  Создайте экземпляр класса <xref:System.Windows.Forms.NotifyIcon> класса и <xref:System.Windows.Forms.ContextMenu> класса, независимо от настройки свойства, необходимые для приложения (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> и <xref:System.Windows.Forms.NotifyIcon.Visible%2A> свойства <xref:System.Windows.Forms.NotifyIcon> компонент, пункты меню для <xref:System.Windows.Forms.ContextMenu> компонент).  
  
2.  Задать <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> свойство <xref:System.Windows.Forms.NotifyIcon> в контекстное меню, которое вы добавили компонент.  
  
     При щелчке значка на панели задач, отображается в контекстном меню.  
  
    > [!NOTE]
    >  В следующем примере кода создается базовая структура меню. Необходимо будет подставить те пункты меню, которые соответствуют приложение, которое вы разрабатываете. Кроме того, необходимо написать код для обработки <xref:System.Windows.Forms.MenuItem.Click> событий для этих пунктов меню.  
  
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
>  Необходимо инициализировать `notifyIcon1` и `contextMenu1,` это можно сделать, включив в конструктор формы следующие инструкции:  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.NotifyIcon>  
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>  
 [Практическое руководство. Добавление значков приложения на панель задач с помощью компонента NotifyIcon в Windows Forms](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md)  
 [Компонент NotifyIcon](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)  
 [Общие сведения о компоненте управления NotifyIcon](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)
