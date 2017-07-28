---
title: "Практическое руководство. Определение всплывающих подсказок для элементов управления в Windows Forms во время разработки | Microsoft Docs"
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
  - "примеры [Windows Forms], всплывающие подсказки"
  - "всплывающие подсказки [Windows Forms], для элементов управления"
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Практическое руководство. Определение всплывающих подсказок для элементов управления в Windows Forms во время разработки
Строку всплывающей подсказки можно задать в коде <xref:System.Windows.Forms.ToolTip> или в окне конструктора Windows Forms Designer.  Дополнительные сведения о компоненте <xref:System.Windows.Forms.ToolTip> см. в разделе [Общие сведения об элементе управления ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы задать всплывающую подсказку ToolTip программным способом  
  
1.  Добавьте элемент управления, для которого будет отображаться всплывающая подсказка.  
  
2.  Используйте метод <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> компонента <xref:System.Windows.Forms.ToolTip>.  
  
    ```vb  
    ' In this example, Button1 is the control to display the ToolTip.  
    ToolTip1.SetToolTip(Button1, "Save changes")  
  
    ```  
  
    ```csharp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1.SetToolTip(button1, "Save changes");  
  
    ```  
  
    ```cpp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1->SetToolTip(button1, "Save changes");  
    ```  
  
### Чтобы задать всплывающую подсказку ToolTip в конструкторе  
  
1.  Добавьте компонент <xref:System.Windows.Forms.ToolTip> на форму.  
  
2.  Выберите элемент управления, для которого будет отображаться всплывающая подсказка, или добавьте его в форму.  
  
3.  В окне **Свойства** задайте в качестве значения свойства **ToolTip on ToolTip1** соответствующую строку текста.  
  
## См. также  
 [Общие сведения об элементе управления ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)   
 [Практическое руководство. Изменение значения задержки для компонента ToolTip в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)   
 [Компонент ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)