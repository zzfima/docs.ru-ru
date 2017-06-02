---
title: "Практическое руководство. Отображение цветовой палитры с помощью компонента ColorDialog | Microsoft Docs"
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
  - "Цвет - диалоговое окно, отображение палитр цветов"
  - "палитры цветов, диалоговое окно"
  - "палитры цветов, отображение в компоненте ColorDialog"
  - "Color - свойство"
  - "ColorDialog - компонент, отображение палитр цветов"
  - "цвета, предоставление пользователям разрешения на выделение"
  - "цвета, отображение палитр"
  - "палитры, отображение цвета"
ms.assetid: ee050f61-dbc8-4436-ba22-51360981ab48
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Отображение цветовой палитры с помощью компонента ColorDialog
Компонент [ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)ColorDialogcporiColorDialogProgramming\<\] служит для отображения цветовой палитры и возвращает свойство, содержащее значение цвета, которое выбрал пользователь.  
  
### Выбор цвета с помощью компонента ColorDialog  
  
1.  Отобразите диалоговое окно с помощью метода <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.  
  
2.  С помощью свойства <xref:System.Windows.Forms.DialogResult> определите, как было закрыто диалоговое окно.  
  
3.  С помощью свойства <xref:System.Windows.Forms.ColorDialog.Color%2A> компонента <xref:System.Windows.Forms.ColorDialog> задайте выбранный цвет.  
  
     В приведенном ниже примере обработчик событий <xref:System.Windows.Forms.Control.Click> элемента управления <xref:System.Windows.Forms.Button> открывает компонент <xref:System.Windows.Forms.ColorDialog>.  Когда цвет выбран и пользователь нажимает кнопку **ОК**, фоновый цвет элемента управления <xref:System.Windows.Forms.Button> меняется на выбранный цвет.  В примере предполагается, что на форме есть элемент управления <xref:System.Windows.Forms.Button> и компонент <xref:System.Windows.Forms.ColorDialog>.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       If ColorDialog1.ShowDialog() = DialogResult.OK Then  
          Button1.BackColor = ColorDialog1.Color  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(colorDialog1.ShowDialog() == DialogResult.OK)  
       {  
          button1.BackColor = colorDialog1.Color;  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,   
          System::EventArgs ^ e)  
       {  
          if(colorDialog1->ShowDialog() == DialogResult::OK)  
          {  
             button1->BackColor = colorDialog1->Color;  
          }  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Добавьте в конструктор формы следующий код, чтобы зарегистрировать обработчик событий.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    this->button1->Click +=   
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.ColorDialog>   
 [Компонент ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)