---
title: "Практическое руководство. Назначение кнопок принятия в Windows Forms | Microsoft Docs"
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
  - "Accept - кнопка в формах Windows Forms"
  - "Button - элемент управления [Windows Forms], назначение по умолчанию"
  - "кнопки, значения по умолчанию в Windows Forms"
  - "элементы управления Windows Forms, кнопка по умолчанию в форме"
ms.assetid: 22cc9da6-b913-4e04-9554-dee443ac5c3a
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Назначение кнопок принятия в Windows Forms
В любой форме Windows Forms можно назначить элемент управления <xref:System.Windows.Forms.Button> кнопкой "Принять", называемой также кнопкой по умолчанию.  Кнопка по умолчанию нажимается при любом нажатии клавиши ВВОД независимо от того, на каком элементе управления формы в этот момент находится фокус.  
  
> [!NOTE]
>  Исключение составляют случаи, когда элемент управления, на котором находится фокус, является другой кнопкой \(в этом случае нажимается кнопка, на которой находится фокус\), многострочным текстовым полем или настраиваемым элементом управления, перехватывающими клавишу ВВОД.  
  
### Чтобы назначить кнопку "Принять"  
  
1.  Для свойства <xref:System.Windows.Forms.Form.AcceptButton%2A> формы задайте соответствующий элемент управления <xref:System.Windows.Forms.Button>.  
  
    ```vb  
    Private Sub SetDefault(ByVal myDefaultBtn As Button)  
      Me.AcceptButton = myDefaultBtn   
    End Sub  
    ```  
  
    ```csharp  
    private void SetDefault(Button myDefaultBtn)  
    {  
       this.AcceptButton = myDefaultBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetDefault(Button ^ myDefaultBtn)  
       {  
          this->AcceptButton = myDefaultBtn;  
       }  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.Form.AcceptButton%2A>   
 [Общие сведения об элементе управления Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)   
 [Способы активации элемента управления Button в Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)   
 [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Практическое руководство. Создание кнопки "Отмена" в Windows Forms](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-cancel-button.md)   
 [Элемент управления Button](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)