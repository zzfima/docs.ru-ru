---
title: "Практическое руководство. Связывание контекстного меню с компонентом NotifyIcon в Windows Forms | Microsoft Docs"
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
  - "контекстные меню, для фоновых процессов"
  - "NotifyIcon - компонент, сопоставление контекстных меню"
  - "контекстные меню, для фоновых процессов"
ms.assetid: d68f3926-08d3-4f7d-949f-1981b29cf188
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Практическое руководство. Связывание контекстного меню с компонентом NotifyIcon в Windows Forms
> [!NOTE]
>  Хотя элементы управления <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenuStrip> заменяют элементы управления <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> предыдущих версий и расширяют их функциональные возможности, при необходимости элементы управления <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> можно сохранить для обратной совместимости и использования в будущем.  
  
 Компонент Windows Forms <xref:System.Windows.Forms.NotifyIcon> позволяет отобразить один значок в области уведомления в панели задач.  Как правило, щелкнув этот значок правой кнопкой мыши, можно передать необходимые команды в представляемое им приложение.  Для сопоставления с этой функцией в приложении необходимо связать компонент <xref:System.Windows.Forms.ContextMenu> с компонентом <xref:System.Windows.Forms.NotifyIcon>.  
  
> [!NOTE]
>  Если требуется, чтобы приложение запускалось в свернутом виде и при этом в панели задач появлялся экземпляр компонента <xref:System.Windows.Forms.NotifyIcon>, необходимо присвоить значение <xref:System.Windows.Forms.FormWindowState> свойству <xref:System.Windows.Forms.Form.WindowState%2A> основной формы и убедиться, что свойство <xref:System.Windows.Forms.NotifyIcon.Visible%2A> компонента <xref:System.Windows.Forms.NotifyIcon> имеет значение `true`.  
  
### Чтобы связать контекстное меню с компонентом NotifyIcon в режиме разработки  
  
1.  Добавьте в форму компонент <xref:System.Windows.Forms.NotifyIcon.Icon%2A> и задайте значения для основных свойств, таких как <xref:System.Windows.Forms.NotifyIcon> и <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.  
  
     Дополнительные сведения см. в разделе [Практическое руководство. Добавление значков приложения на панель задач с помощью компонента NotifyIcon в Windows Forms](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).  
  
2.  Добавьте компонент <xref:System.Windows.Forms.ContextMenu> в форму Windows Forms.  
  
     Добавьте в контекстное меню пункты, предоставляющие команды, которые должны быть доступны во время выполнения.  Одновременно с этими пунктами меню можно также связать дополнительные возможности, такие как клавиши доступа.  
  
3.  Установите свойство <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> компонента <xref:System.Windows.Forms.NotifyIcon> контекстного меню.  
  
     Если после этого щелкнуть значок в панели задач, откроется соответствующее контекстное меню.  
  
### Чтобы связать контекстное меню с компонентом NotifyIcon программным способом  
  
1.  Создайте экземпляры компонентов <xref:System.Windows.Forms.NotifyIcon> и <xref:System.Windows.Forms.ContextMenu> с необходимыми для приложения параметрами свойств \(свойств <xref:System.Windows.Forms.NotifyIcon.Icon%2A> и <xref:System.Windows.Forms.NotifyIcon.Visible%2A> для компонента <xref:System.Windows.Forms.NotifyIcon> и свойств, определяющих пункты меню для компонента <xref:System.Windows.Forms.ContextMenu>\).  
  
2.  Установите свойство <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> компонента <xref:System.Windows.Forms.NotifyIcon> контекстного меню.  
  
     Если после этого щелкнуть значок в панели задач, откроется соответствующее контекстное меню.  
  
    > [!NOTE]
    >  В следующем примере кода создается базовая структура меню.  В нее необходимо будет подставить те пункты меню, которые требуются для разрабатываемого приложения.  Кроме того, необходимо написать код для обработки событий <xref:System.Windows.Forms.MenuItem.Click> для этих пунктов меню.  
  
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
>  Необходимо инициализировать `notifyIcon1` и `contextMenu1,`, для чего достаточно включить в конструктор формы следующие инструкции:  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## См. также  
 <xref:System.Windows.Forms.NotifyIcon>   
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>   
 [Практическое руководство. Добавление значков приложения на панель задач с помощью компонента NotifyIcon в Windows Forms](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md)   
 [Компонент NotifyIcon](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)   
 [Общие сведения о компоненте управления NotifyIcon](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)