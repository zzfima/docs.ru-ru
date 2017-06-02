---
title: "Практическое руководство. Создание кнопки &quot;Отмена&quot; в Windows Forms | Microsoft Docs"
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
  - "Button - элемент управления [Windows Forms], назначение в качестве кнопки отмены"
  - "кнопки, кнопки отмены"
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Создание кнопки &quot;Отмена&quot; в Windows Forms
В любой форме Windows Forms элемент управления <xref:System.Windows.Forms.Button> можно назначить кнопкой "Отмена".  Кнопка "Отмена" активируется при любом нажатии клавиши ESC, независимо от того, на каком элементе управления формы находится в этот момент фокус.  Такая кнопка обычно создается, чтобы позволить пользователю быстро прервать операцию, не выполняя никакого действия.  
  
### Чтобы назначить кнопку "Отмена"  
  
1.  Для свойства <xref:System.Windows.Forms.Form.CancelButton%2A> формы задайте соответствующий элемент управления <xref:System.Windows.Forms.Button>.  
  
    ```vb  
    Private Sub SetCancelButton(ByVal myCancelBtn As Button)  
       Me.CancelButton = myCancelBtn  
    End Sub  
    ```  
  
    ```csharp  
    private void SetCancelButton(Button myCancelBtn)  
    {  
       this.CancelButton = myCancelBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetCancelButton(Button ^ myCancelBtn)  
       {  
          this->CancelButton = myCancelBtn;  
       }  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.Form.CancelButton%2A>   
 [Общие сведения об элементе управления Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)   
 [Способы активации элемента управления Button в Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)   
 [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Практическое руководство. Назначение кнопок принятия в Windows Forms](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-accept-button.md)   
 [Элемент управления Button](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)