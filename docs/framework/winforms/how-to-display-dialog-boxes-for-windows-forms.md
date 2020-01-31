---
title: Как отобразить диалоговые окна
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
ms.openlocfilehash: dd04a06eaa0dd7583ef2f72edb4cffa99aaaa60c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739463"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a>Практическое руководство. Отображение диалоговых окон для Windows Forms
Диалоговое окно отображается таким же образом, как и любая другая форма в приложении. Начальная форма загружается автоматически при запуске приложения. Чтобы в приложении отображалась Вторая форма или диалоговое окно, напишите код для загрузки и отображения. Аналогично, чтобы сделать форму или диалоговое окно видимым, напишите код для выгрузки или скрытия.  
  
### <a name="to-display-a-dialog-box"></a>Отображение диалогового окна  
  
1. Перейдите к обработчику событий, с помощью которого необходимо открыть диалоговое окно. Это может произойти при выборе команды меню, при нажатии кнопки или при возникновении любого другого события.  
  
2. В обработчике событий добавьте код, чтобы открыть диалоговое окно. В этом примере для отображения диалогового окна используется событие нажатия кнопки.  
  
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
