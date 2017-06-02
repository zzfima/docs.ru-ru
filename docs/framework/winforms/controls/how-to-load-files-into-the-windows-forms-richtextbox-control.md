---
title: "Практическое руководство. Загрузка файлов в элемент управления RichTextBox в Windows Forms | Microsoft Docs"
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
  - "текстовые поля, отображение файлов"
  - "примеры [Windows Forms], текстовые поля"
  - "RTF-файлы, открытие в элементе управления RichTextBox"
  - "файлы RTF, открытие в элементе управления RichTextBox"
  - "текстовые файлы, отображение в элементе управления RichTextBox"
  - "RTF-файлы, отображение в элементе управления RichTextBox"
  - "элемент управления RichTextBox [Windows Forms], открытие файлов"
  - "файлы RTF, отображение в элементе управления RichTextBox"
ms.assetid: c03451be-f285-4428-a71a-c41e002cc919
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Загрузка файлов в элемент управления RichTextBox в Windows Forms
Элемент управления Windows Forms <xref:System.Windows.Forms.RichTextBox> может отображать обычный текст, обычный текст в Юникоде или файл в формате RTF. Для этого вызовите метод <xref:System.Windows.Forms.RichTextBox.LoadFile%2A>. Метод <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> можно также использовать для загрузки данных из потока. Для получения дополнительной информации см. <xref:System.Windows.Forms.RichTextBox.LoadFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.  
  
### Загрузка файла в элемент управления RichTextBox  
  
1.  Определить путь к открываемому файлу с помощью компонента <xref:System.Windows.Forms.OpenFileDialog>. Для получения общих сведений см. [Общие сведения о компоненте OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-overview-windows-forms.md).  
  
2.  Вызовите метод <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> элемента управления <xref:System.Windows.Forms.RichTextBox>, указав загружаемый файл и при необходимости тип файла. В следующем примере загружаемый файл берется из свойства <xref:System.Windows.Forms.FileDialog.FileName%2A> компонента <xref:System.Windows.Forms.OpenFileDialog>. Если вы вызываете метод с именем файла в качестве единственного аргумента, предполагается, что тип файла должен быть RTF. Чтобы указать другой тип файла, вызовите метод со значением перечисления <xref:System.Windows.Forms.RichTextBoxStreamType> в качестве второго аргумента.  
  
     В следующем примере компонент <xref:System.Windows.Forms.OpenFileDialog> отображается при нажатии кнопки. Выбранный файл открывается и отображается в элементе управления <xref:System.Windows.Forms.RichTextBox>. В этом примере предполагается, что форма содержит кнопку `btnOpenFile`.  
  
    ```vb  
    Private Sub btnOpenFile_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles btnOpenFile.Click  
         If OpenFileDialog1.ShowDialog() = DialogResult.OK Then  
           RichTextBox1.LoadFile(OpenFileDialog1.FileName, _  
              RichTextBoxStreamType.RichText)  
          End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void btnOpenFile_Click(object sender, System.EventArgs e)  
    {  
       if(openFileDialog1.ShowDialog() == DialogResult.OK)  
       {  
         richTextBox1.LoadFile(openFileDialog1.FileName, RichTextBoxStreamType.RichText);  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void btnOpenFile_Click(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          if(openFileDialog1->ShowDialog() == DialogResult::OK)  
          {  
             richTextBox1->LoadFile(openFileDialog1->FileName,  
                RichTextBoxStreamType::RichText);  
          }  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
    ```csharp  
    this.btnOpenFile.Click += new System.EventHandler(this. btnOpenFile_Click);  
  
    ```  
  
    ```cpp  
    this->btnOpenFile->Click += gcnew   
       System::EventHandler(this, &Form1::btnOpenFile_Click);  
    ```  
  
    > [!IMPORTANT]
    >  Для запуска этого процесса сборке может потребоваться уровень привилегий, предоставляемый классом <xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName>. При выполнении в контексте частичного доверия процесс может выдавать исключение из\-за недостаточных привилегий. Дополнительные сведения см. в разделе [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).  
  
## См. также  
 <xref:System.Windows.Forms.RichTextBox.LoadFile%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.RichTextBox>   
 [Элемент управления RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)