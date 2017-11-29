---
title: "Практическое руководство. Сохранение файлов с помощью элемента управления RichTextBox в Windows Forms"
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
- RTF files [Windows Forms], saving in RichTextBox control
- examples [Windows Forms], text boxes
- saving files [Windows Forms], RichTextBox control
- files [Windows Forms], saving with RichTextBox control
- RichTextBox control [Windows Forms], saving files
- .rtf files [Windows Forms], saving in RichTextBox control
- text files [Windows Forms], saving from RichTextBox control
ms.assetid: 4a58ec19-84d1-4383-9110-298c06adcfca
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d28aeaefca6f8aa13607f1c1e6f72557ef536754
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a>Практическое руководство. Сохранение файлов с помощью элемента управления RichTextBox в Windows Forms
Windows Forms <xref:System.Windows.Forms.RichTextBox> управления может записывать информацию, он отображается в одном из следующих форматов:  
  
-   Обычный текст  
  
-   Текст в Юникоде  
  
-   Текст в формате (RTF)  
  
-   Формат RTF с пропусками OLE-объекты  
  
-   Обычный текст с текстовым представлением объектов OLE  
  
 Чтобы сохранить файл, вызовите <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> метод. Можно также использовать **SaveFile** метод для сохранения данных в поток. Для получения дополнительной информации см. <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.  
  
### <a name="to-save-the-contents-of-the-control-to-a-file"></a>Чтобы сохранить содержимое элемента управления в файл  
  
1.  Определите путь к файлу для сохранения.  
  
     Чтобы сделать это в реальном приложении, обычно используется <xref:System.Windows.Forms.SaveFileDialog> компонента. Общие сведения см. в разделе [Общие сведения о компоненте SaveFileDialog](../../../../docs/framework/winforms/controls/savefiledialog-component-overview-windows-forms.md).  
  
2.  Вызовите <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> метод <xref:System.Windows.Forms.RichTextBox> управления, указав имя файла для сохранения и, при необходимости, тип файла. Если вызвать метод с именем файла только аргументом, файл будет сохранен как RTF. Чтобы указать другой тип файла, вызовите метод со значением перечисления <xref:System.Windows.Forms.RichTextBoxStreamType> в качестве второго аргумента.  
  
     В приведенном ниже примере путь задан при размещении RTF-файл является **Мои документы** папки. Это расположение используется, так как предполагается, что большинство компьютеров под управлением операционной системы Windows будет содержать эта папка. Эта папка также позволяет уровень доступа к системе минимальной безопасно запустить приложение. В приведенном ниже примере предполагается наличие формы с <xref:System.Windows.Forms.RichTextBox> управления уже добавлен.  
  
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
    >  В этом примере создается файл (если файл отсутствует). Если приложению требуется создать файл, что ему необходимо иметь доступ к папке. Для задания разрешений используются списки управления доступом. Если файл уже существует, приложению требуется только доступ на запись, меньшими привилегиями. Если это возможно, безопаснее создать файл во время развертывания и только предоставляет доступ на чтение в одном файле, а не создавать доступа для папки. По тем же соображениям рекомендуется записывать данные в пользовательские папки, а не в коревую папку или папку Program Files.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.RichTextBox>  
 [Элемент управления RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Элементы управления для использования в Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
