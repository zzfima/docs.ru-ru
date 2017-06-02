---
title: "Практическое руководство. Отображение списка шрифтов с помощью компонента FontDialog | Microsoft Docs"
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
  - "диалоговое окно шрифтов, отображение"
  - "Font - свойство, установка с помощью компонента FontDialog"
  - "FontDialog - компонент [Windows Forms]"
  - "шрифты, атрибуты"
  - "шрифты, выбор"
  - "шрифты, отображение списка"
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Отображение списка шрифтов с помощью компонента FontDialog
Компонент [FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md) позволяет пользователям выбирать шрифт и менять параметры его отображения, такие как вес и размер.  
  
 Шрифт, выбранный в диалоговом окне, возвращается в свойстве <xref:System.Windows.Forms.FontDialog.Font%2A>.  Таким образом, при выборе шрифта пользователем весь процесс сводится к чтению свойства.  
  
### Чтобы выбрать свойства шрифта с помощью компонента FontDialog  
  
1.  Отобразите диалоговое окно с помощью метода <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.  
  
2.  С помощью свойства <xref:System.Windows.Forms.DialogResult> определите, как было закрыто диалоговое окно.  
  
3.  Для задания требуемого шрифта воспользуйтесь свойством <xref:System.Windows.Forms.FontDialog.Font%2A>.  
  
     В приведенном ниже примере обработчик события <xref:System.Windows.Forms.Control.Click> элемента управления <xref:System.Windows.Forms.Button> открывает компонент <xref:System.Windows.Forms.FontDialog>.  Когда шрифт выбран и пользователь нажимает кнопку **ОК**, свойство <xref:System.Windows.Forms.FontDialog.Font%2A> элемента управления <xref:System.Windows.Forms.TextBox> приобретает значение выбранного шрифта.  Пример предполагает, что в форме есть элемент управления <xref:System.Windows.Forms.Button>, элемент управления <xref:System.Windows.Forms.TextBox> и компонент <xref:System.Windows.Forms.FontDialog>.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If FontDialog1.ShowDialog() = DialogResult.OK Then  
          TextBox1.Font = FontDialog1.Font  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(fontDialog1.ShowDialog() == DialogResult.OK)  
       {  
          textBox1.Font = fontDialog1.Font;  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(fontDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Font = fontDialog1->Font;  
          }  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Поместите в конструктор формы следующий код, чтобы зарегистрировать обработчик событий.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.FontDialog>   
 [Компонент FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)