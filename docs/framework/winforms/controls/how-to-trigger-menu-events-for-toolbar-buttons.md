---
title: "Практическое руководство. Генерирование событий меню для кнопок элемента управления Toolbar | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "примеры [Windows Forms], панели инструментов"
  - "ToolBar - элемент управления [Windows Forms], обработчики событий Click"
  - "ToolBar - элемент управления [Windows Forms], кодирование событий нажатия кнопки"
  - "панели инструментов [Windows Forms], обработчики событий Click"
ms.assetid: 98374f70-993d-4ca4-89fb-48fea6ce5b45
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Генерирование событий меню для кнопок элемента управления Toolbar
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.  
  
 Если в форме Windows Forms существует элемент управления <xref:System.Windows.Forms.ToolBar> с кнопками панели инструментов, необходимо знать, какую кнопку нажимает пользователь.  
  
 В событии <xref:System.Windows.Forms.ToolBar.ButtonClick> элемента управления <xref:System.Windows.Forms.ToolBar> можно оценить свойство <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> класса.  В приведенном ниже примере представлено окно сообщения, показывающее, какая кнопка была нажата.  Дополнительные сведения см. в разделе [Класс MessageBox](frlrfSystemWindowsFormsMessageBoxClassTopic).  
  
 В примере, представленном ниже, подразумевается, что элемент управления <xref:System.Windows.Forms.ToolBar> добавлен в форму Windows Forms.  
  
### Чтобы обработать событие Click в панели инструментов  
  
1.  В процедуре добавьте кнопки в элемент управления <xref:System.Windows.Forms.ToolBar>.  
  
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
  
2.  Добавьте обработчик для события <xref:System.Windows.Forms.ToolBar.ButtonClick> элемента управления <xref:System.Windows.Forms.ToolBar>.  Используйте оператор переключения регистра и класс <xref:System.Windows.Forms.ToolBarButtonClickEventArgs>, чтобы определить, какая кнопка панели инструментов была нажата.  В соответствии с результатом отобразите окно сообщения.  
  
    > [!NOTE]
    >  Окно сообщения в этом примере использовалось исключительно в качестве шаблона.  Конечно, можно добавить любой другой код, который должен выполняться при нажатии кнопки панели инструментов.  
  
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
  
## См. также  
 <xref:System.Windows.Forms.ToolBar>   
 [Практическое руководство. Добавление кнопок в элемент управления ToolBar](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md)   
 [Практическое руководство. Определение значка для кнопки элемента управления ToolBar](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)   
 [Элемент управления ToolBar](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)