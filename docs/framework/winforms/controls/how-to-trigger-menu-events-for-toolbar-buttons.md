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
ms.openlocfilehash: 99db077b41a59fe9263f7283b58b8c31959c7c79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182076"
---
# <a name="how-to-trigger-menu-events-for-toolbar-buttons"></a>Практическое руководство. Генерирование событий меню для кнопок элемента управления Toolbar
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.  
  
 Если ваша форма <xref:System.Windows.Forms.ToolBar> Windows оснащена элементом управления кнопками панели инструментов, вы хотите знать, какую кнопку нажимает пользователь.  
  
 На <xref:System.Windows.Forms.ToolBar.ButtonClick> случае элемента <xref:System.Windows.Forms.ToolBar> управления можно <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> оценить <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> свойство класса. В следующем примере отображается окно сообщения, указывающее, какая кнопка была нажата. Дополнительные сведения см. в разделе <xref:System.Windows.Forms.MessageBox>.  
  
 Приведенный ниже пример <xref:System.Windows.Forms.ToolBar> предполагает, что элемент управления был добавлен в форму Windows.  
  
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
  
2. Добавьте обработчик <xref:System.Windows.Forms.ToolBar> событий <xref:System.Windows.Forms.ToolBar.ButtonClick> для события элемента управления. Используйте оператора переключения <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> и класс для определения кнопки панели инструментов, которая была нажата. В зависимости от результатов отображается соответствующее окно сообщения.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ToolBar>
- [Практическое руководство. Добавление кнопок в элемент управления ToolBar](how-to-add-buttons-to-a-toolbar-control.md)
- [Практическое руководство. Определение значка для кнопки элемента управления ToolBar](how-to-define-an-icon-for-a-toolbar-button.md)
- [Элемент управления ToolBar](toolbar-control-windows-forms.md)
