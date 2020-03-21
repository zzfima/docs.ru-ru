---
title: 'Как: Отображение Dialog коробки'
ms.date: 03/30/2017
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
ms.openlocfilehash: 3625080c7c322e297a9de92e4f95a40c0caf3e72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181974"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a>Практическое руководство. Отображение диалоговых окон для Windows Forms
Вы отображаете диалоговую коробку так же, как отображаете любую другую форму в приложении. Форма запуска загружается автоматически при запуске приложения. Чтобы в приложении появилась вторая форма или диалоговое окно, напишите код для его загрузки и отображения. Аналогичным образом, чтобы форма или диалоговое окно исчезло, напишите код, чтобы выгрузить или скрыть его.  
  
### <a name="to-display-a-dialog-box"></a>Отображение диалогового окна  
  
1. Перейдите к обработчику событий, с помощью которого вы хотите открыть поле диалога. Это может произойти при выборе команды меню, при нажатии кнопки или при любом другом событии.  
  
2. В обработчике событий добавьте код, чтобы открыть диалоговое окно. В этом примере для отображаемого диалогового окна используется событие нажатия кнопки:  
  
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
