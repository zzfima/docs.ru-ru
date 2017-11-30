---
title: "Практическое руководство. Добавление значков приложения на панель задач с помощью компонента NotifyIcon в Windows Forms"
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
f1_keywords: TrayIcon
helpviewer_keywords:
- status area icons
- icons [Windows Forms], adding to taskbar
- NotifyIcon component
- taskbar [Windows Forms], adding icons
ms.assetid: d28c0fe6-aaf2-4df7-ad74-928d861a8510
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 97c31998885926e9a7372bcf3182d1c95f0b79d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a>Практическое руководство. Добавление значков приложения на панель задач с помощью компонента NotifyIcon в Windows Forms
Windows Forms <xref:System.Windows.Forms.NotifyIcon> компонент выводит один значок в области уведомлений панели задач. Чтобы отобразить несколько значков в области состояния, необходимо иметь несколько <xref:System.Windows.Forms.NotifyIcon> компонентов в форме. Чтобы задать значок, отображаемый для элемента управления, используйте <xref:System.Windows.Forms.NotifyIcon.Icon%2A> свойство. Также можно написать код <xref:System.Windows.Forms.NotifyIcon.DoubleClick> обработчика событий, так что-то происходит, когда пользователь дважды щелкает значок. Например может сделать диалоговое окно отображается для пользователя настроить фоновый процесс, представленный этим значком.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.NotifyIcon> Компонент используется только, чтобы оповестить пользователей о возникших на действие или событие, или произошли изменения в состояние какая-либо. Следует использовать меню, панелей инструментов и других элементов пользовательского интерфейса для обычных операций взаимодействия с приложениями.  
  
### <a name="to-set-the-icon"></a>Для задания значка  
  
1.  Присвоить значение <xref:System.Windows.Forms.NotifyIcon.Icon%2A> свойства. Значение должно быть типа `System.Drawing.Icon` и может быть загружена из ICO-файл. Файл значка можно указать в коде или нажав кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с <xref:System.Windows.Forms.NotifyIcon.Icon%2A> свойство в  **Свойства** окна, а затем выбрав нужный файл в **откройте** появившемся.  
  
2.  Задайте для свойства <xref:System.Windows.Forms.NotifyIcon.Visible%2A> значение `true`.  
  
3.  Задать <xref:System.Windows.Forms.NotifyIcon.Text%2A> свойства соответствующую строку всплывающей подсказки.  
  
     В следующем примере кода путь задан для находится значок **Мои документы** папки. Это расположение используется, так как предполагается, что большинство компьютеров под управлением операционной системы Windows будет содержать эта папка. Эта папка также пользователи с уровнями доступа минимальные системные безопасно выполнить приложение. В следующем примере требуется форма с <xref:System.Windows.Forms.NotifyIcon> управления уже добавлен. Также требуется файл значка с именем `Icon.ico`.  
  
    ```vb  
    ' You should replace the bold icon in the sample below  
    ' with an icon of your own choosing.  
    NotifyIcon1.Icon = New _   
       System.Drawing.Icon(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Icon.ico")  
    NotifyIcon1.Visible = True  
    NotifyIcon1.Text = "Antivirus program"  
    ```  
  
    ```csharp  
    // You should replace the bold icon in the sample below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    notifyIcon1.Icon =   
       new System.Drawing.Icon (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Icon.ico");  
    notifyIcon1.Visible = true;  
    notifyIcon1.Text = "Antivirus program";  
    ```  
  
    ```cpp  
    // You should replace the bold icon in the sample below  
    // with an icon of your own choosing.  
    notifyIcon1->Icon = gcnew   
       System::Drawing::Icon(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Icon.ico"));  
    notifyIcon1->Visible = true;  
    notifyIcon1->Text = "Antivirus program";  
    ```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.NotifyIcon>  
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>  
 [Практическое руководство. Связывание контекстного меню с компонентом NotifyIcon в Windows Forms](../../../../docs/framework/winforms/controls/how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)  
 [Компонент NotifyIcon](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)  
 [Общие сведения о компоненте управления NotifyIcon](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)
