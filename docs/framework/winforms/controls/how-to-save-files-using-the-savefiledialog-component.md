---
title: "Практическое руководство. Сохранение файлов с помощью компонента SaveFileDialog | Microsoft Docs"
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
  - "файлы, сохранение"
  - "OpenFile - метод, сохранение файлов с помощью компонента SaveFileDialog"
  - "SaveFileDialog - компонент, сохранение файлов"
  - "сохранение файлов"
ms.assetid: 02e8f409-b83f-4707-babb-e71f6b223d90
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Практическое руководство. Сохранение файлов с помощью компонента SaveFileDialog
Компонент <xref:System.Windows.Forms.SaveFileDialog> позволяет пользователям просматривать файловую систему и выбирать файлы для сохранения.  Диалоговое окно возвращает путь и имя файла, который был выбран пользователем.  Однако для сохранения файла на диск необходимо написать код.  
  
### Чтобы сохранить файл с помощью компонента SaveFileDialog  
  
-   Отобразите диалоговое окно **"Сохранение файла"** и вызовите метод, чтобы сохранить файл, выбранный пользователем.  
  
     Чтобы сохранить файл, вызовите метод <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> компонента <xref:System.Windows.Forms.SaveFileDialog>.  С помощью этого метода получите объект <xref:System.IO.Stream>, в который можно произвести запись.  
  
     В примере, представленном ниже, свойство <xref:System.Windows.Forms.DialogResult> используется для получения имени файла, а метод <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> — для сохранения файла.  Метод <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> предоставляет поток, в который производится запись файла.  
  
     В примере, представленном ниже, используется элемент управления <xref:System.Windows.Forms.Button> с присоединенным к нему изображением.  Когда пользователь нажимает кнопку, открывается экземпляр компонента <xref:System.Windows.Forms.SaveFileDialog>, с помощью которого можно выбрать следующие типы файлов: GIF, JPEG и BMP.  Если в диалоговом окне "Сохранение файла" выбран файл какого\-либо из этих типов, изображение кнопки сохраняется.  
  
    > [!IMPORTANT]
    >  Чтобы получить или задать свойство <xref:System.Windows.Forms.FileDialog.FileName%2A>, сборка требует уровня привилегий, предоставляемых классом <xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName>.  Если процесс выполняется в контексте с частичным доверием, он может сгенерировать исключение из\-за недостатка привилегий.  Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../../../docs/framework/misc/code-access-security-basics.md).  
  
     В примере предполагается, что в форме существует элемент управления <xref:System.Windows.Forms.Button> со свойством <xref:System.Windows.Forms.ButtonBase.Image%2A>, в качестве значения которого можно использовать определенные типы файлов \(GIF, JPEG и BMP\).  
  
    > [!NOTE]
    >  Свойство <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> класса <xref:System.Windows.Forms.FileDialog> \(которое в результате наследования является частью класса <xref:System.Windows.Forms.SaveFileDialog>\) использует индекс, начинающийся с единицы.  Очень важно при написании кода сохранять данные в определенном формате \(например, сохранять файл в формате простого текста, а не в двоичном\).  Это свойство представлено в следующем примере.  
  
    ```vb  
    Private Sub Button2_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button2.Click  
       ' Displays a SaveFileDialog so the user can save the Image  
       ' assigned to Button2.  
       Dim saveFileDialog1 As New SaveFileDialog()  
       saveFileDialog1.Filter = "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif"  
       saveFileDialog1.Title = "Save an Image File"  
       saveFileDialog1.ShowDialog()  
  
       ' If the file name is not an empty string open it for saving.  
       If saveFileDialog1.FileName <> "" Then  
          ' Saves the Image via a FileStream created by the OpenFile method.  
          Dim fs As System.IO.FileStream = Ctype _  
             (saveFileDialog1.OpenFile(), System.IO.FileStream)  
          ' Saves the Image in the appropriate ImageFormat based upon the  
          ' file type selected in the dialog box.  
          ' NOTE that the FilterIndex property is one-based.  
          Select Case saveFileDialog1.FilterIndex  
             Case 1  
                Me.button2.Image.Save(fs, _  
                   System.Drawing.Imaging.ImageFormat.Jpeg)  
  
             Case 2  
                Me.button2.Image.Save(fs, _  
                   System.Drawing.Imaging.ImageFormat.Bmp)  
  
             Case 3  
                Me.button2.Image.Save(fs, _  
                   System.Drawing.Imaging.ImageFormat.Gif)  
           End Select  
  
           fs.Close()  
        End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button2_Click(object sender, System.EventArgs e)  
    {  
       // Displays a SaveFileDialog so the user can save the Image  
       // assigned to Button2.  
       SaveFileDialog saveFileDialog1 = new SaveFileDialog();  
       saveFileDialog1.Filter = "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif";  
       saveFileDialog1.Title = "Save an Image File";  
       saveFileDialog1.ShowDialog();  
  
       // If the file name is not an empty string open it for saving.  
       if(saveFileDialog1.FileName != "")  
       {  
          // Saves the Image via a FileStream created by the OpenFile method.  
          System.IO.FileStream fs =   
             (System.IO.FileStream)saveFileDialog1.OpenFile();  
          // Saves the Image in the appropriate ImageFormat based upon the  
          // File type selected in the dialog box.  
          // NOTE that the FilterIndex property is one-based.  
          switch(saveFileDialog1.FilterIndex)  
          {  
             case 1 :   
             this.button2.Image.Save(fs,   
                System.Drawing.Imaging.ImageFormat.Jpeg);  
             break;  
  
             case 2 :   
             this.button2.Image.Save(fs,   
                System.Drawing.Imaging.ImageFormat.Bmp);  
             break;  
  
             case 3 :   
             this.button2.Image.Save(fs,   
                System.Drawing.Imaging.ImageFormat.Gif);  
             break;  
          }  
  
       fs.Close();  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       System::Void button2_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Displays a SaveFileDialog so the user can save the Image  
          // assigned to Button2.  
          SaveFileDialog ^ saveFileDialog1 = new SaveFileDialog();  
          saveFileDialog1->Filter =   
             "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif";  
          saveFileDialog1->Title = "Save an Image File";  
          saveFileDialog1->ShowDialog();  
          // If the file name is not an empty string, open it for saving.  
          if(saveFileDialog1->FileName != "")  
          {  
             // Saves the Image through a FileStream created by  
             // the OpenFile method.  
             System::IO::FileStream ^ fs =   
                safe_cast<System::IO::FileStream*>(  
                saveFileDialog1->OpenFile());  
             // Saves the Image in the appropriate ImageFormat based on  
             // the file type selected in the dialog box.  
             // Note that the FilterIndex property is one based.  
             switch(saveFileDialog1->FilterIndex)  
             {  
                case 1 :  
                   this->button2->Image->Save(fs,  
                      System::Drawing::Imaging::ImageFormat::Jpeg);  
                   break;  
                case 2 :  
                   this->button2->Image->Save(fs,   
                      System::Drawing::Imaging::ImageFormat::Bmp);  
                   break;  
                case 3 :  
                   this->button2->Image->Save(fs,   
                      System::Drawing::Imaging::ImageFormat::Gif);  
                   break;  
             }  
          fs->Close();  
          }  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Поместите в конструктор формы следующий код, чтобы зарегистрировать обработчик событий.  
  
    ```csharp  
    this.button2.Click += new System.EventHandler(this.button2_Click);  
  
    ```  
  
    ```cpp  
    this->button2->Click += gcnew  
       System::EventHandler(this, &Form1::button2_Click);  
    ```  
  
     Дополнительные сведения о записи файловых потоков можно найти в разделах [Метод FileStream.BeginWrite](frlrfSystemIOFileStreamClassBeginWriteTopic) и [Метод FileStream.Write](https://msdn.microsoft.com/en-us/library/system.io.filestream.write.aspx).  
  
    > [!NOTE]
    >  Определенные элементы управления, например элемент управления <xref:System.Windows.Forms.RichTextBox>, могут сохранять файлы.  Дополнительные сведения можно найти в разделе "Компонент SaveFileDialog" технической статьи [Основной код для диалоговых окон Windows Forms](http://go.microsoft.com/fwlink/?LinkID=102575) библиотеки MSDN Online.  
  
## См. также  
 <xref:System.Windows.Forms.SaveFileDialog>   
 [Компонент SaveFileDialog](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)