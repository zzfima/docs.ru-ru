---
title: "Практическое руководство. Создание текстового поля, доступного только для чтения (Windows Forms) | Microsoft Docs"
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
  - "текстовые поля только для чтения"
  - "текстовые поля, только для чтения"
  - "TextBox - элемент управления [Windows Forms], только для чтения"
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Создание текстового поля, доступного только для чтения (Windows Forms)
Редактируемое текстовое поле Windows Forms можно сделать доступным только для чтения.  Например, в текстовом поле могут отображаться данные, которые обычно допускают редактирование, но при определенном состоянии приложения оказываются недоступными для изменения.  
  
### Создание текстового поля только для чтения  
  
1.  Присвойте свойству <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> элемента управления <xref:System.Windows.Forms.TextBox> значение `true`.  Если это свойство имеет значение `true`, то пользователи могут прокручивать и выделять текст, но не изменять его.  Команда **Копировать** в текстовом поле действует, а команды **Вырезать** и **Вставить** — нет.  
  
    > [!NOTE]
    >  Свойство <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> влияет только на взаимодействие с пользователем во время выполнения.  Содержимое текстового поля может быть изменено программными средствами во время выполнения; для этого достаточно изменить значение свойства <xref:System.Windows.Forms.TextBox.Text%2A> текстового поля.  
  
## См. также  
 <xref:System.Windows.Forms.TextBox>   
 [Общие сведения об элементе управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [Практическое руководство. Добавление кавычек в строку](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [Практическое руководство. Многострочные элементы управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [Элемент управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)