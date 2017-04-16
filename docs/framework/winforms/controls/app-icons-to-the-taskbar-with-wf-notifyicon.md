---
title: "Практическое руководство. Добавление значков приложения на панель задач с помощью компонента NotifyIcon в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TrayIcon"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "значки, добавление на панель задач"
  - "NotifyIcon - компонент"
  - "значки в области состояния"
  - "панель задач, добавление значков"
ms.assetid: d28c0fe6-aaf2-4df7-ad74-928d861a8510
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Добавление значков приложения на панель задач с помощью компонента NotifyIcon в Windows Forms
Компонент Windows Forms <xref:System.Windows.Forms.NotifyIcon> позволяет отобразить один значок в области уведомления о состоянии в панели задач.  Чтобы отобразить несколько значков в области состояния, необходимо использовать в форме несколько компонентов <xref:System.Windows.Forms.NotifyIcon>.  Для выбора значка, отображаемого для элемента управления, используется свойство <xref:System.Windows.Forms.NotifyIcon.Icon%2A>.  Можно также написать в обработчике событий <xref:System.Windows.Forms.NotifyIcon.DoubleClick> код, выполняющий определенные действия в случае, когда пользователь дважды щелкнет значок.  Например, с помощью кода можно открывать диалоговое окно, в котором пользователю будет предложено настроить фоновый процесс, представленный этим значком.  
  
> [!NOTE]
>  Компонент <xref:System.Windows.Forms.NotifyIcon> используется только для предупреждения пользователей о том, что произошло какое\-либо действие или событие, или об изменении состояния.  Для обычных операций взаимодействия с приложениями следует использовать меню, панели инструментов и другие элементы интерфейса пользователя.  
  
### Чтобы установить значок  
  
1.  Присвойте значение свойству <xref:System.Windows.Forms.NotifyIcon.Icon%2A>.  Значение должно быть типа `System.Drawing.Icon` и может быть загружено из файла с расширением .ico.  Файл значка можно указать в коде или в режиме конструктора, нажав кнопку с многоточием \(![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) рядом со свойством <xref:System.Windows.Forms.NotifyIcon.Icon%2A> в окне **Свойства** и затем выбрав нужный файл в открывшемся диалоговом окне **Открыть**.  
  
2.  Установите для свойства <xref:System.Windows.Forms.NotifyIcon.Visible%2A> значение `true`.  
  
3.  Задайте в качестве значения свойства <xref:System.Windows.Forms.NotifyIcon.Text%2A> соответствующую строку всплывающей подсказки.  
  
     В следующем примере кода в качестве местоположения значка выбрана папка **Мои документы**.  Такой выбор объясняется тем, что эта папка имеется на большинстве компьютеров, работающих под управлением операционной системы Windows.  Кроме того, если используется эта папка, то для запуска приложения достаточен минимальный уровень доступа к системе.  Для следующего примера требуется форма с заранее добавленным элементом управления <xref:System.Windows.Forms.NotifyIcon>.  Также требуется файл значка с именем `Icon.ico`.  
  
     \[Visual Basic\]  
  
    ```  
    ' You should replace the bold icon in the sample below  
    ' with an icon of your own choosing.  
    NotifyIcon1.Icon = New _   
       System.Drawing.Icon(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Icon.ico")  
    NotifyIcon1.Visible = True  
    NotifyIcon1.Text = "Antivirus program"  
  
    ```  
  
     \[C\#\]  
  
    ```  
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
  
     \[cpp\]  
  
    ```  
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
  
## См. также  
 <xref:System.Windows.Forms.NotifyIcon>   
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>   
 [Практическое руководство. Связывание контекстного меню с компонентом NotifyIcon в Windows Forms](../../../../docs/framework/winforms/controls/how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)   
 [Компонент NotifyIcon](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)   
 [Общие сведения о компоненте управления NotifyIcon](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)