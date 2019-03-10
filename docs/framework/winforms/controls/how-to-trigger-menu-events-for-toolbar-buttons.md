---
title: Практическое руководство. Триггер событий меню для кнопок панели инструментов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], click event handlers
- ToolBar control [Windows Forms], coding button click events
- toolbars [Windows Forms], click event handlers
ms.assetid: 98374f70-993d-4ca4-89fb-48fea6ce5b45
ms.openlocfilehash: b6d0404f22c7db72b096ef130d9a9f4815db4059
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707551"
---
# <a name="how-to-trigger-menu-events-for-toolbar-buttons"></a><span data-ttu-id="8192f-102">Практическое руководство. Триггер событий меню для кнопок панели инструментов</span><span class="sxs-lookup"><span data-stu-id="8192f-102">How to: Trigger Menu Events for Toolbar Buttons</span></span>
> [!NOTE]
>  <span data-ttu-id="8192f-103">Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="8192f-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="8192f-104">Если ваши функции формы Windows <xref:System.Windows.Forms.ToolBar> элемента управления с кнопками панели инструментов, необходимо знать, какую кнопку пользователь нажимает кнопку.</span><span class="sxs-lookup"><span data-stu-id="8192f-104">If your Windows Form features a <xref:System.Windows.Forms.ToolBar> control with toolbar buttons, you will want to know which button the user clicks.</span></span>  
  
 <span data-ttu-id="8192f-105">На <xref:System.Windows.Forms.ToolBar.ButtonClick> событие <xref:System.Windows.Forms.ToolBar> элемента управления, вы можете оценить <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> свойство <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> класса.</span><span class="sxs-lookup"><span data-stu-id="8192f-105">On the <xref:System.Windows.Forms.ToolBar.ButtonClick> event of the <xref:System.Windows.Forms.ToolBar> control, you can evaluate the <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> property of the <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> class.</span></span> <span data-ttu-id="8192f-106">В следующем примере отображается окно сообщения, указывающее, какая кнопка была нажата.</span><span class="sxs-lookup"><span data-stu-id="8192f-106">In the example below, a message box is shown, indicating which button was clicked.</span></span> <span data-ttu-id="8192f-107">Дополнительные сведения см. в разделе <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="8192f-107">For details, see <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="8192f-108">В приведенном ниже примере предполагается, что <xref:System.Windows.Forms.ToolBar> элемент управления добавлен в форму Windows.</span><span class="sxs-lookup"><span data-stu-id="8192f-108">The example below assumes a <xref:System.Windows.Forms.ToolBar> control has been added to a Windows Form.</span></span>  
  
### <a name="to-handle-the-click-event-on-a-toolbar"></a><span data-ttu-id="8192f-109">Обработка события Click на панели инструментов</span><span class="sxs-lookup"><span data-stu-id="8192f-109">To handle the Click event on a toolbar</span></span>  
  
1.  <span data-ttu-id="8192f-110">В процедуре, добавив кнопки панели инструментов для <xref:System.Windows.Forms.ToolBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8192f-110">In a procedure, add toolbar buttons to the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
    ```vb  
    Public Sub ToolBarConfig()  
    ' Instantiate the toolbar buttons, set their Text properties  
    ' and add them to the ToolBar control.  
       ToolBar1.Buttons.Add(New ToolBarButton("One"))  
       ToolBar1.Buttons.Add(New ToolBarButton("Two"))  
       ToolBar1.Buttons.Add(New ToolBarButton("Three"))  
    ' Add the event handler delegate.  
       AddHandler ToolBar1.ButtonClick, AddressOf Me.ToolBar1_ButtonClick  
    End Sub  
    ```  
  
    ```csharp  
    public void ToolBarConfig()   
    {  
       toolBar1.Buttons.Add(new ToolBarButton("One"));  
       toolBar1.Buttons.Add(new ToolBarButton("Two"));  
       toolBar1.Buttons.Add(new ToolBarButton("Three"));  
  
       toolBar1.ButtonClick +=   
          new ToolBarButtonClickEventHandler(this.toolBar1_ButtonClick);  
    }  
    ```  
  
    ```cpp  
    public:  
       void ToolBarConfig()  
       {  
          toolBar1->Buttons->Add(gcnew ToolBarButton("One"));  
          toolBar1->Buttons->Add(gcnew ToolBarButton("Two"));  
          toolBar1->Buttons->Add(gcnew ToolBarButton("Three"));  
  
          toolBar1->ButtonClick +=   
             gcnew ToolBarButtonClickEventHandler(this,  
             &Form1::toolBar1_ButtonClick);  
       }  
    ```  
  
2.  <span data-ttu-id="8192f-111">Добавьте обработчик событий для <xref:System.Windows.Forms.ToolBar> элемента управления <xref:System.Windows.Forms.ToolBar.ButtonClick> событий.</span><span class="sxs-lookup"><span data-stu-id="8192f-111">Add an event handler for the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.ButtonClick> event.</span></span> <span data-ttu-id="8192f-112">Используйте оператор переключения регистра и <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> класс, чтобы определить кнопку панели инструментов, которая была нажата.</span><span class="sxs-lookup"><span data-stu-id="8192f-112">Use a case switching statement and the <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> class to determine the toolbar button that was clicked.</span></span> <span data-ttu-id="8192f-113">В зависимости от результатов отображается соответствующее окно сообщения.</span><span class="sxs-lookup"><span data-stu-id="8192f-113">Based on this, show an appropriate message box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8192f-114">Окно сообщения в этом примере используется исключительно в качестве шаблона.</span><span class="sxs-lookup"><span data-stu-id="8192f-114">A message box is being used solely as a placeholder in this example.</span></span> <span data-ttu-id="8192f-115">Вы можете добавить другой код, выполняемый при нажатии кнопки панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="8192f-115">Feel free to add other code to execute when the toolbar buttons are clicked.</span></span>  
  
    ```vb  
    Protected Sub ToolBar1_ButtonClick(ByVal sender As Object, _  
    ByVal e As ToolBarButtonClickEventArgs)  
    ' Evaluate the Button property of the ToolBarButtonClickEventArgs  
    ' to determine which button was clicked.  
       Select Case ToolBar1.Buttons.IndexOf(e.Button)  
         Case 0  
           MessageBox.Show("First toolbar button clicked")  
         Case 1  
           MessageBox.Show("Second toolbar button clicked")  
         Case 2  
           MessageBox.Show("Third toolbar button clicked")  
       End Select  
    End Sub  
    ```  
  
    ```csharp  
    protected void toolBar1_ButtonClick(object sender,  
    ToolBarButtonClickEventArgs e)  
    {  
       // Evaluate the Button property of the ToolBarButtonClickEventArgs  
       // to determine which button was clicked.  
       switch (toolBar1.Buttons.IndexOf(e.Button))  
       {  
          case 0 :  
             MessageBox.Show("First toolbar button clicked");  
             break;  
          case 1 :  
             MessageBox.Show("Second toolbar button clicked");  
             break;  
          case 2 :  
             MessageBox.Show("Third toolbar button clicked");  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    protected:  
       void toolBar1_ButtonClick(System::Object ^ sender,  
          ToolBarButtonClickEventArgs ^ e)  
       {  
         // Evaluate the Button property of the ToolBarButtonClickEventArgs  
         // to determine which button was clicked.  
          switch (toolBar1->Buttons->IndexOf(e->Button))  
          {  
             case 0 :  
                MessageBox::Show("First toolbar button clicked");  
                break;  
             case 1 :  
                MessageBox::Show("Second toolbar button clicked");  
                break;  
             case 2 :  
                MessageBox::Show("Third toolbar button clicked");  
                break;  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8192f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8192f-116">See also</span></span>
- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="8192f-117">Практическое руководство. Добавление кнопок в элемент управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="8192f-117">How to: Add Buttons to a ToolBar Control</span></span>](how-to-add-buttons-to-a-toolbar-control.md)
- [<span data-ttu-id="8192f-118">Практическое руководство. Определение значка для кнопки панели инструментов</span><span class="sxs-lookup"><span data-stu-id="8192f-118">How to: Define an Icon for a ToolBar Button</span></span>](how-to-define-an-icon-for-a-toolbar-button.md)
- [<span data-ttu-id="8192f-119">Элемент управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="8192f-119">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
