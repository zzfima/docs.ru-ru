---
title: "Практическое руководство. Отслеживание изменения атрибутов форматирования текста в элементе управления RichTextBox в Windows Forms"
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
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], determining font changes
- text boxes [Windows Forms], determining font changes
- SelChange event
ms.assetid: bdfed015-f77a-41e5-b38f-f8629b2fa166
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0dc272e26124acf5c6bd5cf3030941c26c021c49
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="fed50-102">Практическое руководство. Отслеживание изменения атрибутов форматирования текста в элементе управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fed50-102">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="fed50-103">Часто используются в Windows Forms <xref:System.Windows.Forms.RichTextBox> управления используется для форматирования текста с помощью атрибутов, таких как параметры шрифта или стиль абзаца.</span><span class="sxs-lookup"><span data-stu-id="fed50-103">A common use of the Windows Forms <xref:System.Windows.Forms.RichTextBox> control is formatting text with attributes such as font options or paragraph styles.</span></span> <span data-ttu-id="fed50-104">В приложении могут понадобиться для отслеживания изменений в целях отображения панели инструментов, как и множество текстовых приложений форматирования текста.</span><span class="sxs-lookup"><span data-stu-id="fed50-104">Your application may need to keep track of any changes in text formatting for the purpose of displaying a toolbar, as in many word-processing applications.</span></span>  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a><span data-ttu-id="fed50-105">Для реагирования на изменения атрибутов форматирования</span><span class="sxs-lookup"><span data-stu-id="fed50-105">To respond to changes in formatting attributes</span></span>  
  
1.  <span data-ttu-id="fed50-106">Напишите код в <xref:System.Windows.Forms.RichTextBox.SelectionChanged> обработчик событий может выполнять необходимые действия в зависимости от значения атрибута.</span><span class="sxs-lookup"><span data-stu-id="fed50-106">Write code in the <xref:System.Windows.Forms.RichTextBox.SelectionChanged> event handler to perform an appropriate action depending on the value of the attribute.</span></span> <span data-ttu-id="fed50-107">В следующем примере изменяется внешний вид кнопки на панели инструментов в зависимости от значения <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="fed50-107">The following example changes the appearance of a toolbar button depending on the value of the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="fed50-108">Кнопки панели инструментов будут обновлены только в том случае, когда курсор перемещается в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="fed50-108">The toolbar button will only be updated when the insertion point is moved in the control.</span></span>  
  
     <span data-ttu-id="fed50-109">В приведенном ниже примере предполагается наличие формы с <xref:System.Windows.Forms.RichTextBox> управления и <xref:System.Windows.Forms.ToolBar> управления, который содержит кнопки панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="fed50-109">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control and a <xref:System.Windows.Forms.ToolBar> control that contains a toolbar button.</span></span> <span data-ttu-id="fed50-110">Дополнительные сведения о панели инструментов и кнопки панели инструментов см. в разделе [как: Добавление кнопок в элемент управления ToolBar](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md).</span><span class="sxs-lookup"><span data-stu-id="fed50-110">For more information about toolbars and toolbar buttons, see [How to: Add Buttons to a ToolBar Control](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md).</span></span>  
  
    ```vb  
    ' The following code assumes the existence of a toolbar control  
    ' with at least one toolbar button.  
    Private Sub RichTextBox1_SelectionChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles RichTextBox1.SelectionChanged  
       If RichTextBox1.SelectionBullet = True Then  
          ' Bullet button on toolbar should appear pressed  
          ToolBarButton1.Pushed = True  
       Else  
           ' Bullet button on toolbar should appear unpressed  
           ToolBarButton1.Pushed = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private void richTextBox1_SelectionChanged(object sender,  
    System.EventArgs e)  
    {  
       if (richTextBox1.SelectionBullet == true)   
       {  
          // Bullet button on toolbar should appear pressed  
          toolBarButton1.Pushed = true;  
       }  
       else   
       {  
          // Bullet button on toolbar should appear unpressed  
          toolBarButton1.Pushed = false;  
       }  
    }  
    ```  
  
    ```cpp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private:  
       System::Void richTextBox1_SelectionChanged(  
          System::Object ^  sender, System::EventArgs ^  e)  
       {  
          if (richTextBox1->SelectionBullet == true)  
          {  
             // Bullet button on toolbar should appear pressed  
             toolBarButton1->Pushed = true;  
          }  
          else  
          {  
             // Bullet button on toolbar should appear unpressed  
             toolBarButton1->Pushed = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fed50-111">См. также</span><span class="sxs-lookup"><span data-stu-id="fed50-111">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBox.SelectionChanged>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="fed50-112">Элемент управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="fed50-112">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="fed50-113">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fed50-113">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
