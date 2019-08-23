---
title: Практическое руководство. Генерирование событий меню для кнопок элемента управления Toolbar
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
ms.openlocfilehash: 381b8ba08db6ff5bb817c9c89008dacb1085ac1b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956040"
---
# <a name="how-to-trigger-menu-events-for-toolbar-buttons"></a>Практическое руководство. Генерирование событий меню для кнопок элемента управления Toolbar
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.  
  
 Если в форме Windows Forms <xref:System.Windows.Forms.ToolBar> есть элемент управления с кнопками панели инструментов, вам будет необходимо указать, какая кнопка была нажата пользователем.  
  
 В случае события <xref:System.Windows.Forms.ToolBar> элемента управления можно <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> оценить свойство класса. <xref:System.Windows.Forms.ToolBar.ButtonClick> В следующем примере отображается окно сообщения, указывающее, какая кнопка была нажата. Дополнительные сведения см. в разделе <xref:System.Windows.Forms.MessageBox>.  
  
 В приведенном ниже примере <xref:System.Windows.Forms.ToolBar> предполагается, что элемент управления был добавлен в форму Windows Forms.  
  
### <a name="to-handle-the-click-event-on-a-toolbar"></a>Обработка события Click на панели инструментов  
  
1. В процедуре добавьте кнопки <xref:System.Windows.Forms.ToolBar> панели инструментов в элемент управления.  
  
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
  
2. Добавьте обработчик событий для <xref:System.Windows.Forms.ToolBar> <xref:System.Windows.Forms.ToolBar.ButtonClick> события элемента управления. Используйте оператор переключения регистра и <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> класс для определения кнопки на панели инструментов, которая была нажата. В зависимости от результатов отображается соответствующее окно сообщения.  
  
    > [!NOTE]
    > Окно сообщения в этом примере используется исключительно в качестве шаблона. Вы можете добавить другой код, выполняемый при нажатии кнопки панели инструментов.  
  
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
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ToolBar>
- [Практическое руководство. Добавление кнопок в элемент управления ToolBar](how-to-add-buttons-to-a-toolbar-control.md)
- [Практическое руководство. Определение значка для кнопки на панели инструментов](how-to-define-an-icon-for-a-toolbar-button.md)
- [Элемент управления ToolBar](toolbar-control-windows-forms.md)
