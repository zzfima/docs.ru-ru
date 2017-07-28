---
title: "How to: Display Dialog Boxes for Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Windows Forms, displaying"
  - "Windows Forms dialog boxes, displaying"
  - "Windows Forms, calling one form from another"
  - "dialog boxes, displaying for Windows Forms"
ms.assetid: aaac1b38-c651-495a-8d3d-5a9bfb32fee3
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Display Dialog Boxes for Windows Forms
Отображение диалогового окна осуществляется таким же образом, как и отображение любой другой формы в приложении.  Начальная форма загружается автоматически при запуске приложения.  Чтобы в приложении появилась вторая форма или диалоговое окно, напишите код для ее загрузки и отображения.  Чтобы скрыть форму или диалоговое окно, напишите код для выгрузки формы или ее сокрытия.  
  
### Чтобы отобразить диалоговое окно, выполните следующие действия.  
  
1.  Перейдите к обработчику событий, с помощью которого требуется открыть диалоговое окно.  Событие может произойти при выборе команды меню, при нажатии кнопки или при возникновении любого другого события.  
  
2.  В обработчике событий добавьте код для открытия диалогового окна.  В этом примере для отображения диалогового окна используется событие, которое происходит при нажатии кнопки.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim dlg1 as new Form()  
       dlg1.ShowDialog()  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       Form dlg1 = new Form();  
       dlg1.ShowDialog();  
    }  
  
    ```  
  
    ```cpp  
    private:   
      void button1_Click(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        Form ^ dlg1 = gcnew Form();  
        dlg1->ShowDialog();  
      }  
    ```