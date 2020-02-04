---
title: Загрузка файлов в элемент управления RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying files
- examples [Windows Forms], text boxes
- .rtf files [Windows Forms], opening in RichTextBox control
- RTF files [Windows Forms], opening in RichTextBox control
- text files [Windows Forms], displaying in RichTextBox control
- .rtf files [Windows Forms], displaying in RichTextBox control
- RichTextBox control [Windows Forms], opening files
- RTF files [Windows Forms], displaying in RichTextBox control
ms.assetid: c03451be-f285-4428-a71a-c41e002cc919
ms.openlocfilehash: c31e004ea4cd0821b5f18f0ab0fe2708e6ac4b59
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736295"
---
# <a name="how-to-load-files-into-the-windows-forms-richtextbox-control"></a>Практическое руководство. Загрузка файлов в элемент управления RichTextBox в Windows Forms

Элемент управления Windows Forms <xref:System.Windows.Forms.RichTextBox> может отображать обычный текст, обычный текст в Юникоде или файл в формате RTF. Для этого вызовите метод <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> . Метод <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> можно также использовать для загрузки данных из потока. Дополнительные сведения см. в разделе <xref:System.Windows.Forms.RichTextBox.LoadFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.

### <a name="to-load-a-file-into-the-richtextbox-control"></a>Загрузка файла в элемент управления RichTextBox

1. Определить путь к открываемому файлу с помощью компонента <xref:System.Windows.Forms.OpenFileDialog> . Общие сведения см. в разделе [Общие сведения о компоненте OpenFileDialog](openfiledialog-component-overview-windows-forms.md).

2. Вызовите метод <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> элемента управления <xref:System.Windows.Forms.RichTextBox> , указав загружаемый файл и при необходимости тип файла. В следующем примере загружаемый файл берется из свойства <xref:System.Windows.Forms.OpenFileDialog> компонента <xref:System.Windows.Forms.FileDialog.FileName%2A> . Если вы вызываете метод с именем файла в качестве единственного аргумента, предполагается, что тип файла должен быть RTF. Чтобы указать другой тип файла, вызовите метод со значением перечисления <xref:System.Windows.Forms.RichTextBoxStreamType> в качестве второго аргумента.

    В следующем примере компонент <xref:System.Windows.Forms.OpenFileDialog> отображается при нажатии кнопки. Выбранный файл открывается и отображается в элементе управления <xref:System.Windows.Forms.RichTextBox> . В этом примере предполагается, что форма содержит кнопку`btnOpenFile`.

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

    (Визуальный C#элемент C++, визуальный элемент) Поместите следующий код в конструктор формы для регистрации обработчика событий.

    ```csharp
    this.btnOpenFile.Click += new System.EventHandler(this. btnOpenFile_Click);
    ```

    ```cpp
    this->btnOpenFile->Click += gcnew
       System::EventHandler(this, &Form1::btnOpenFile_Click);
    ```

    > [!IMPORTANT]
    > Для запуска этого процесса сборке может потребоваться уровень привилегий, предоставляемый классом <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> . При выполнении в контексте частичного доверия процесс может выдавать исключение из-за недостаточных привилегий. Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../misc/code-access-security-basics.md).

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.RichTextBox.LoadFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [Элемент управления RichTextBox](richtextbox-control-windows-forms.md)
- [Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)
