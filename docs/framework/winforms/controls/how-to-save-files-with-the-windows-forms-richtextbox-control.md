---
title: Сохранение файлов с помощью элемента управления RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- saving files
- RTF files [Windows Forms], saving in RichTextBox control
- examples [Windows Forms], text boxes
- saving files [Windows Forms], RichTextBox control
- files [Windows Forms], saving with RichTextBox control
- RichTextBox control [Windows Forms], saving files
- .rtf files [Windows Forms], saving in RichTextBox control
- text files [Windows Forms], saving from RichTextBox control
ms.assetid: 4a58ec19-84d1-4383-9110-298c06adcfca
ms.openlocfilehash: a87b93a53347aeba54f944b0f4c455aa272ea243
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744819"
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a>Практическое руководство. Сохранение файлов с помощью элемента управления RichTextBox в Windows Forms

Элемент управления Windows Forms <xref:System.Windows.Forms.RichTextBox> может записывать отображаемые сведения в одном из следующих форматов:

- Обычный текст

- Обычный текст в Юникоде

- Формат RTF

- RTF с пробелами вместо объектов OLE

- Обычный текст с текстовым представлением объектов OLE

Чтобы сохранить файл, вызовите метод <xref:System.Windows.Forms.RichTextBox.SaveFile%2A>. Можно также использовать метод **SaveFile** для сохранения данных в поток. Для получения дополнительной информации см. <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.

### <a name="to-save-the-contents-of-the-control-to-a-file"></a>Сохранение содержимого элемента управления в файле

1. Определите путь к файлу, который необходимо сохранить.

    Для этого в реальном приложении обычно используется компонент <xref:System.Windows.Forms.SaveFileDialog>. Общие сведения см. в разделе [Общие сведения о компоненте SaveFileDialog](savefiledialog-component-overview-windows-forms.md).

2. Вызовите метод <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> элемента управления <xref:System.Windows.Forms.RichTextBox>, указав файл для сохранения и, при необходимости, тип файла. При вызове метода с именем файла в качестве единственного аргумента файл будет сохранен как RTF. Чтобы указать другой тип файла, вызовите метод со значением перечисления <xref:System.Windows.Forms.RichTextBoxStreamType> в качестве второго аргумента.

    В приведенном ниже примере путь, заданный для расположения RTF-файла, является папкой " **Мои документы** ". Это расположение используется, поскольку можно предположить, что большинство компьютеров, работающих под управлением операционной системы Windows, будут содержать эту папку. Выбор этого расположения также позволяет пользователям с минимальными уровнями доступа к системе безопасно запускать приложение. В приведенном ниже примере предполагается, что форма с уже добавленным элементом управления <xref:System.Windows.Forms.RichTextBox>.

    ```vb
    Public Sub SaveFile()
       ' You should replace the bold file name in the
       ' sample below with a file name of your own choosing.
       RichTextBox1.SaveFile(System.Environment.GetFolderPath _
       (System.Environment.SpecialFolder.Personal) _
       & "\Testdoc.rtf", _
          RichTextBoxStreamType.RichNoOleObjs)
    End Sub
    ```

    ```csharp
    public void SaveFile()
    {
       // You should replace the bold file name in the
       // sample below with a file name of your own choosing.
       // Note the escape character used (@) when specifying the path.
       richTextBox1.SaveFile(System.Environment.GetFolderPath
       (System.Environment.SpecialFolder.Personal)
       + @"\Testdoc.rtf",
          RichTextBoxStreamType.RichNoOleObjs);
    }
    ```

    ```cpp
    public:
       void SaveFile()
       {
          // You should replace the bold file name in the
          // sample below with a file name of your own choosing.
          richTextBox1->SaveFile(String::Concat
             (System::Environment::GetFolderPath
             (System::Environment::SpecialFolder::Personal),
             "\\Testdoc.rtf"), RichTextBoxStreamType::RichNoOleObjs);
       }
    ```

    > [!IMPORTANT]
    > В этом примере создается файл (если файл отсутствует). Если приложению требуется создать файл, этому приложению требуется доступ для создания папки. Для задания разрешений используются списки управления доступом. Если файл уже существует, приложению требуется только доступ на запись, чем меньше привилегия. Там, где это возможно, более безопасно создавать файл во время развертывания и предоставлять доступ только для чтения к одному файлу, а не к папке. По тем же соображениям рекомендуется записывать данные в пользовательские папки, а не в коревую папку или папку Program Files.

## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [Элемент управления RichTextBox](richtextbox-control-windows-forms.md)
- [Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)
