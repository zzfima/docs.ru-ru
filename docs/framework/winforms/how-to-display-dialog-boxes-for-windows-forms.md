---
title: Практическое руководство. Отображение диалоговых окон для Windows Forms
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
ms.openlocfilehash: a25fe86c4dde1fed69e192956d77615bf2a70402
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537428"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a><span data-ttu-id="fa213-102">Практическое руководство. Отображение диалоговых окон для Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fa213-102">How to: Display Dialog Boxes for Windows Forms</span></span>
<span data-ttu-id="fa213-103">Отобразить диалоговое окно в так же, как любой другой форме отображения в приложении.</span><span class="sxs-lookup"><span data-stu-id="fa213-103">You display a dialog box in the same way you display any other form in an application.</span></span> <span data-ttu-id="fa213-104">Начальная форма загружается автоматически при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="fa213-104">The startup form loads automatically when the application is run.</span></span> <span data-ttu-id="fa213-105">Чтобы сделать вторую форму или диалоговое окно отображается в приложении, напишите код для загрузки и отображения.</span><span class="sxs-lookup"><span data-stu-id="fa213-105">To make a second form or dialog box appear in the application, write code to load and display it.</span></span> <span data-ttu-id="fa213-106">Аналогичным образом чтобы форма или диалогового окна поле исчезают, напишите код для выгрузки его или скрывать.</span><span class="sxs-lookup"><span data-stu-id="fa213-106">Similarly, to make the form or dialog box disappear, write code to unload or hide it.</span></span>  
  
### <a name="to-display-a-dialog-box"></a><span data-ttu-id="fa213-107">Чтобы отобразить диалоговое окно</span><span class="sxs-lookup"><span data-stu-id="fa213-107">To display a dialog box</span></span>  
  
1.  <span data-ttu-id="fa213-108">Перейдите к обработчику событий, с которой необходимо открыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="fa213-108">Navigate to the event handler with which you want to open the dialog box.</span></span> <span data-ttu-id="fa213-109">Это может произойти при выборе команды меню, при нажатии кнопки или при возникновении любого другого события.</span><span class="sxs-lookup"><span data-stu-id="fa213-109">This can happen when a menu command is selected, when a button is clicked, or when any other event occurs.</span></span>  
  
2.  <span data-ttu-id="fa213-110">В обработчике событий добавьте код, чтобы открыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="fa213-110">In the event handler, add code to open the dialog box.</span></span> <span data-ttu-id="fa213-111">В этом примере событие нажатия кнопки используется для отображения диалогового окна:</span><span class="sxs-lookup"><span data-stu-id="fa213-111">In this example, a button-click event is used to show the dialog box:</span></span>  
  
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
