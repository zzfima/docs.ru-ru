---
title: Как выполнить Определить, при форматировании изменение атрибутов элемента управления RichTextBox в Windows Forms
ms.date: 03/30/2017
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
ms.openlocfilehash: e746cd1d0f9f7d9850d0263ee6ed0a82472fcb5e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504162"
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="d2b7c-102">Как выполнить Определить, при форматировании изменение атрибутов элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d2b7c-102">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="d2b7c-103">Обычно используются в Windows Forms <xref:System.Windows.Forms.RichTextBox> управления используется для форматирования текста с помощью атрибутов, таких как параметры шрифт или стиль абзаца.</span><span class="sxs-lookup"><span data-stu-id="d2b7c-103">A common use of the Windows Forms <xref:System.Windows.Forms.RichTextBox> control is formatting text with attributes such as font options or paragraph styles.</span></span> <span data-ttu-id="d2b7c-104">Приложение может потребоваться для отслеживания изменений в целях отображения панели инструментов, как и множество текстовых приложений форматирования текста.</span><span class="sxs-lookup"><span data-stu-id="d2b7c-104">Your application may need to keep track of any changes in text formatting for the purpose of displaying a toolbar, as in many word-processing applications.</span></span>  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a><span data-ttu-id="d2b7c-105">Реагировать на изменения атрибутов форматирования</span><span class="sxs-lookup"><span data-stu-id="d2b7c-105">To respond to changes in formatting attributes</span></span>  
  
1.  <span data-ttu-id="d2b7c-106">Написание кода в <xref:System.Windows.Forms.RichTextBox.SelectionChanged> обработчик событий может выполнять соответствующие действия в зависимости от значения атрибута.</span><span class="sxs-lookup"><span data-stu-id="d2b7c-106">Write code in the <xref:System.Windows.Forms.RichTextBox.SelectionChanged> event handler to perform an appropriate action depending on the value of the attribute.</span></span> <span data-ttu-id="d2b7c-107">В следующем примере изменяется внешний вид кнопки на панели инструментов в зависимости от значения <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="d2b7c-107">The following example changes the appearance of a toolbar button depending on the value of the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="d2b7c-108">Кнопки панели инструментов будут обновлены только в том случае, когда курсор перемещается в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="d2b7c-108">The toolbar button will only be updated when the insertion point is moved in the control.</span></span>  
  
     <span data-ttu-id="d2b7c-109">В приведенном ниже примере предполагается, что форма <xref:System.Windows.Forms.RichTextBox> управления и <xref:System.Windows.Forms.ToolBar> элемент управления, содержащий кнопку панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="d2b7c-109">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control and a <xref:System.Windows.Forms.ToolBar> control that contains a toolbar button.</span></span> <span data-ttu-id="d2b7c-110">Дополнительные сведения о панели инструментов и кнопки панели инструментов, см. в разделе [как: Добавление кнопок в элемент управления ToolBar](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md).</span><span class="sxs-lookup"><span data-stu-id="d2b7c-110">For more information about toolbars and toolbar buttons, see [How to: Add Buttons to a ToolBar Control](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d2b7c-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d2b7c-111">See also</span></span>
- <xref:System.Windows.Forms.RichTextBox.SelectionChanged>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="d2b7c-112">Элемент управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="d2b7c-112">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)
- [<span data-ttu-id="d2b7c-113">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d2b7c-113">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
