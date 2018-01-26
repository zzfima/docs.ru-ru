---
title: "Практическое руководство. Отображение диалоговых окон для Windows Forms"
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
- Windows Forms, displaying
- Windows Forms dialog boxes [Windows Forms], displaying
- Windows Forms, calling one form from another
- dialog boxes [Windows Forms], displaying for Windows Forms
ms.assetid: aaac1b38-c651-495a-8d3d-5a9bfb32fee3
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 46e4d019bbd586c0ed46794f55c65da7bcc657f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a>Практическое руководство. Отображение диалоговых окон для Windows Forms
Отобразить диалоговое окно в так же, как любой другой форме отображения в приложении. Начальная форма загружается автоматически при запуске приложения. Чтобы сделать вторую форму или диалоговое окно отображается в приложении, напишите код для загрузки и отображения. Аналогичным образом чтобы форма или диалогового окна поле исчезают, напишите код для выгрузки его или скрывать.  
  
### <a name="to-display-a-dialog-box"></a>Чтобы отобразить диалоговое окно  
  
1.  Перейдите к обработчику событий, с которой необходимо открыть диалоговое окно. Это может произойти при выборе команды меню, при нажатии кнопки или при возникновении любого другого события.  
  
2.  В обработчике событий добавьте код, чтобы открыть диалоговое окно. В этом примере событие нажатия кнопки используется для отображения диалогового окна:  
  
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
