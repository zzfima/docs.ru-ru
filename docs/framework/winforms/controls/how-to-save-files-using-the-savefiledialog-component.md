---
title: Практическое руководство. Сохранение файлов с помощью компонента SaveFileDialog
ms.date: 03/30/2017
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
ms.openlocfilehash: 32de7f7e38195271e179d4fae3884b7a39f37c45
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868087"
---
# <a name="how-to-save-files-using-the-savefiledialog-component"></a>Практическое руководство. Сохранение файлов с помощью компонента SaveFileDialog

Компонент <xref:System.Windows.Forms.SaveFileDialog> позволяет пользователям просматривать файловую систему и выбирать файлы для сохранения. Диалоговое окно возвращает путь и имя файла, который пользователь выбрал в диалоговом окне. Тем не менее для фактического сохранения файла на диск необходимо написать специальный код.

### <a name="to-save-a-file-using-the-savefiledialog-component"></a>Сохранение файла с помощью компонента SaveFileDialog

- Выведите на экран диалоговое окно **Сохранить файл** и вызовите метод для сохранения файла, выбранного пользователем.

  Чтобы сохранить файл, используйте метод <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> компонента <xref:System.Windows.Forms.SaveFileDialog>. Этот метод предоставляет объект <xref:System.IO.Stream>, в который можно выполнять запись.

  В приведенном ниже примере используется свойство <xref:System.Windows.Forms.DialogResult> для получения имени файла и метод <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> для сохранения файла. Метод <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> предоставляет поток для записи файла.

  В приведенном ниже примере имеется элемент управления <xref:System.Windows.Forms.Button> с назначенным ему изображением. При нажатии кнопки создается экземпляр компонента <xref:System.Windows.Forms.SaveFileDialog> с фильтром, который разрешает файлы типа. gif,. JPEG и. bmp. При выборе файла такого типа в диалоговом окне "Сохранить файл" изображение кнопки сохраняется.

  > [!IMPORTANT]
  > Чтобы получить или задать свойство <xref:System.Windows.Forms.FileDialog.FileName%2A>, сборке требуется уровень привилегий, предоставляемый классом <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType>. Если процесс выполняется в контексте с частичным доверием, он может сгенерировать исключение из-за недостатка привилегий. Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../misc/code-access-security-basics.md).

  В примере предполагается, что в форме есть элемент управления <xref:System.Windows.Forms.Button> со свойством <xref:System.Windows.Forms.ButtonBase.Image%2A>, для которого задано значение файла типа. gif,. JPEG или. bmp.

  > [!NOTE]
  > Свойство <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> класса <xref:System.Windows.Forms.FileDialog> (которое из-за наследования является частью класса <xref:System.Windows.Forms.SaveFileDialog>) использует индекс, отсчитываемый от единицы. Это важно при написании кода для сохранения данных в определенном формате (например, в формате обычного текста или двоичном формате). Это свойство представлено в следующем примере.

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

  (Визуальный C# элемент C++и визуальный элемент) Поместите следующий код в конструктор формы для регистрации обработчика событий.

  ```csharp
  this.button2.Click += new System.EventHandler(this.button2_Click);
  ```

  ```cpp
  this->button2->Click += gcnew
      System::EventHandler(this, &Form1::button2_Click);
  ```

  Дополнительные сведения о записи файловых потоков см. в разделе <xref:System.IO.FileStream.BeginWrite%2A> и <xref:System.IO.FileStream.Write%2A>.

  > [!NOTE]
  > Некоторые элементы управления, такие как элемент управления <xref:System.Windows.Forms.RichTextBox>, имеют возможность сохранять файлы.

## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.SaveFileDialog>
- [Компонент SaveFileDialog](savefiledialog-component-windows-forms.md)
