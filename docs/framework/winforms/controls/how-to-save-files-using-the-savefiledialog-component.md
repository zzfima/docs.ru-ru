---
title: "Практическое руководство. Сохранение файлов с помощью компонента SaveFileDialog"
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
- saving files
- SaveFileDialog component [Windows Forms], saving files
- files [Windows Forms], saving
- OpenFile method [Windows Forms], saving files with SaveFileDialog component
ms.assetid: 02e8f409-b83f-4707-babb-e71f6b223d90
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 70301cd3d357ab90ac6e7ed6d76a902107ef5e4a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-save-files-using-the-savefiledialog-component"></a>Практическое руководство. Сохранение файлов с помощью компонента SaveFileDialog
<xref:System.Windows.Forms.SaveFileDialog> Компонент позволяет пользователям просматривать файловую систему и выберите файлы для сохранения. Диалоговое окно возвращает путь и имя файла, который пользователь выбрал в диалоговом окне. Тем не менее для фактического сохранения файла на диск необходимо написать специальный код.  
  
### <a name="to-save-a-file-using-the-savefiledialog-component"></a>Сохранение файла с помощью компонента SaveFileDialog  
  
-   Выведите на экран диалоговое окно **Сохранить файл** и вызовите метод для сохранения файла, выбранного пользователем.  
  
     Используйте <xref:System.Windows.Forms.SaveFileDialog> компонента <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> метод для сохранения файла. Этот метод позволяет <xref:System.IO.Stream> можно записать объект.  
  
     В приведенном ниже используется <xref:System.Windows.Forms.DialogResult> свойства, чтобы получить имя файла и <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> метод для сохранения файла. <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> Метод предоставляет поток для записи файла.  
  
     В приведенном ниже примере имеется <xref:System.Windows.Forms.Button> элемента управления с присоединенным к нему изображением. При нажатии кнопки, <xref:System.Windows.Forms.SaveFileDialog> экземпляр компонента, файлов: тип GIF, JPEG и .bmp фильтром. При выборе файла такого типа в диалоговом окне "Сохранить файл" изображение кнопки сохраняется.  
  
    > [!IMPORTANT]
    >  Чтобы получить или задать <xref:System.Windows.Forms.FileDialog.FileName%2A> свойства, сборка требует уровня прав доступа предоставляемых по <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> класса. Если процесс выполняется в контексте с частичным доверием, он может сгенерировать исключение из-за недостатка привилегий. Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../../../docs/framework/misc/code-access-security-basics.md).  
  
     В этом примере предполагается, имеет форму <xref:System.Windows.Forms.Button> управления с его <xref:System.Windows.Forms.ButtonBase.Image%2A> значение свойства типа GIF, JPEG и .bmp в файл.  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.FileDialog> Класса <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> свойство (, из-за наследования, являющийся частью <xref:System.Windows.Forms.SaveFileDialog> класс) использует однобазовый индекс. Это важно при написании кода для сохранения данных в определенном формате (например, в формате обычного текста или двоичном формате). Это свойство представлено в следующем примере.  
  
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
                safe_cast\<System::IO::FileStream*>(  
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
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
    ```csharp  
    this.button2.Click += new System.EventHandler(this.button2_Click);  
    ```  
  
    ```cpp  
    this->button2->Click += gcnew  
       System::EventHandler(this, &Form1::button2_Click);  
    ```  
  
     Дополнительные сведения о создании файлового потока см. в разделе <xref:System.IO.FileStream.BeginWrite%2A> и <xref:System.IO.FileStream.Write%2A>.  
  
    > [!NOTE]
    >  Некоторые элементы управления, такие как <xref:System.Windows.Forms.RichTextBox> управления, иметь возможность сохранять файлы. Дополнительные сведения см. в разделе, посвященном компоненту SaveFileDialog, технической статьи [Essential Code for Windows Forms Dialog Boxes](http://go.microsoft.com/fwlink/?LinkID=102575) в библиотеке MSDN Online.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.SaveFileDialog>  
 [Компонент SaveFileDialog](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)
