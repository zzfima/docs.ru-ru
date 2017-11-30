---
title: "Практическое руководство. Отображение списка шрифтов с помощью компонента FontDialog"
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
- fonts [Windows Forms], showing list
- FontDialog component [Windows Forms]
- fonts [Windows Forms], attributes
- Font property [Windows Forms], setting with FontDialog component
- Font dialog box [Windows Forms], displaying
- fonts [Windows Forms], selecting
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 781daeb43a952ef25e73edd577fa17c61b02b426
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-show-a-font-list-with-the-fontdialog-component"></a>Практическое руководство. Отображение списка шрифтов с помощью компонента FontDialog
[FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md) компонент позволяет пользователям выбрать шрифт, а также менять параметры его отображения, такие как вес и размер.  
  
 Шрифт, выбранный в диалоговом окне, возвращается в <xref:System.Windows.Forms.FontDialog.Font%2A> свойство. Таким образом используя преимущества шрифта, выбранного пользователем так же легко, как и чтение свойство.  
  
### <a name="to-select-font-properties-using-the-fontdialog-component"></a>Чтобы выбрать свойства шрифта с помощью компонента FontDialog  
  
1.  Отобразить диалоговое окно с помощью <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод.  
  
2.  Используйте <xref:System.Windows.Forms.DialogResult> свойство, чтобы определить, как окно было закрыто.  
  
3.  Используйте <xref:System.Windows.Forms.FontDialog.Font%2A> свойство, чтобы задать нужный шрифт.  
  
     В следующем примере <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Click> обработчик событий открывает <xref:System.Windows.Forms.FontDialog> компонента. Если шрифт является выбран и пользователь нажимает **ОК**, <xref:System.Windows.Forms.FontDialog.Font%2A> свойство <xref:System.Windows.Forms.TextBox> элемент управления на форме имеет значение выбранного шрифта. В этом примере предполагается, имеет форму <xref:System.Windows.Forms.Button> управления <xref:System.Windows.Forms.TextBox> управления и <xref:System.Windows.Forms.FontDialog> компонента.  
  
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
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.FontDialog>  
 [Компонент FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)
