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
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a><span data-ttu-id="a41a0-102">Практическое руководство. Отображение диалоговых окон для Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a41a0-102">How to: Display Dialog Boxes for Windows Forms</span></span>
<span data-ttu-id="a41a0-103">Вы отображаете диалоговую коробку так же, как отображаете любую другую форму в приложении.</span><span class="sxs-lookup"><span data-stu-id="a41a0-103">You display a dialog box in the same way you display any other form in an application.</span></span> <span data-ttu-id="a41a0-104">Форма запуска загружается автоматически при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="a41a0-104">The startup form loads automatically when the application is run.</span></span> <span data-ttu-id="a41a0-105">Чтобы в приложении появилась вторая форма или диалоговое окно, напишите код для его загрузки и отображения.</span><span class="sxs-lookup"><span data-stu-id="a41a0-105">To make a second form or dialog box appear in the application, write code to load and display it.</span></span> <span data-ttu-id="a41a0-106">Аналогичным образом, чтобы форма или диалоговое окно исчезло, напишите код, чтобы выгрузить или скрыть его.</span><span class="sxs-lookup"><span data-stu-id="a41a0-106">Similarly, to make the form or dialog box disappear, write code to unload or hide it.</span></span>  
  
### <a name="to-display-a-dialog-box"></a><span data-ttu-id="a41a0-107">Отображение диалогового окна</span><span class="sxs-lookup"><span data-stu-id="a41a0-107">To display a dialog box</span></span>  
  
1. <span data-ttu-id="a41a0-108">Перейдите к обработчику событий, с помощью которого вы хотите открыть поле диалога.</span><span class="sxs-lookup"><span data-stu-id="a41a0-108">Navigate to the event handler with which you want to open the dialog box.</span></span> <span data-ttu-id="a41a0-109">Это может произойти при выборе команды меню, при нажатии кнопки или при любом другом событии.</span><span class="sxs-lookup"><span data-stu-id="a41a0-109">This can happen when a menu command is selected, when a button is clicked, or when any other event occurs.</span></span>  
  
2. <span data-ttu-id="a41a0-110">В обработчике событий добавьте код, чтобы открыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="a41a0-110">In the event handler, add code to open the dialog box.</span></span> <span data-ttu-id="a41a0-111">В этом примере для отображаемого диалогового окна используется событие нажатия кнопки:</span><span class="sxs-lookup"><span data-stu-id="a41a0-111">In this example, a button-click event is used to show the dialog box:</span></span>  
  
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
