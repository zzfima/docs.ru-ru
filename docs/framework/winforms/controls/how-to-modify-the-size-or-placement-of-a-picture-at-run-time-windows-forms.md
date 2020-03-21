---
title: Практическое руководство. Изменение размера или размещения изображения во время выполнения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], controlling placement in PictureBox control [Windows Forms]
- examples [Windows Forms], PictureBox control
- PictureBox control [Windows Forms], picture size and alignment
- pictures [Windows Forms], controlling placement in PictureBox control [Windows Forms]
ms.assetid: d0b332a3-fae2-4891-957c-dc3e17743326
ms.openlocfilehash: fea813d7b9fe585e35b729b8b64e3a5f414ef76d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141970"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>Практическое руководство. Изменение размера или размещения изображения во время выполнения (Windows Forms)
Если вы используете <xref:System.Windows.Forms.PictureBox> элемент управления формами Windows <xref:System.Windows.Forms.PictureBox.SizeMode%2A> в форме, вы можете установить свойство на ней:  
  
- Выровняйте верхний левый угол изображения с верхним левым углом управления  
  
- Центр изображения в элементе управления  
  
- Отрегулируйте размер элемента управления, чтобы соответствовать изображению, который он отображает  
  
- Растянуть любую картинку, которую он отображает, чтобы соответствовать элементу управления  
  
 Растяжка изображения (особенно в формате bitmap) может привести к потере качества изображения. Metafiles, которые представляют собой списки графических инструкций для рисования изображений во время выполнения, лучше подходят для растяжения, чем bitmaps.  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>Установить свойство SizeMode во время выполнения  
  
1. <xref:System.Windows.Forms.PictureBox.SizeMode%2A> Установить <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (по <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>умолчанию), <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>, , или . <xref:System.Windows.Forms.PictureBoxSizeMode.Normal>означает, что изображение помещается в верхнем левом углу управления; если изображение больше элемента управления, его нижние и правые края обрезаны. <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>означает, что изображение сосредоточено внутри элемента управления; если изображение больше элемента управления, внешние края изображения обрезаны. <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>означает, что размер элемента управления регулируется с размером изображения. <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>является обратным, и означает, что размер изображения регулируется размером элемента управления.  
  
     В приведенном ниже примере путь, установленный для расположения изображения, представляет собой папку «Мои документы». Это делается, потому что можно предположить, что большинство компьютеров под управлением операционной системы Windows будет включать в себя этот каталог. Это также позволяет пользователям с минимальным уровнем доступа к системе безопасно запускать приложение. Приведенный ниже пример предполагает <xref:System.Windows.Forms.PictureBox> форму с уже добавленным элементом управления.  
  
    ```vb  
    Private Sub StretchPic()  
       ' Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage  
       ' Load the picture into the control.  
       ' You should replace the bold image
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void StretchPic(){  
       // Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage;  
       // Load the picture into the control.  
       // You should replace the bold image
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Image.gif")  
    }  
    ```  
  
    ```cpp  
    private:  
       void StretchPic()  
       {  
          // Stretch the picture to fit the control.  
          pictureBox1->SizeMode = PictureBoxSizeMode::StretchImage;  
          // Load the picture into the control.  
          // You should replace the bold image
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.PictureBox>
- [Практическое руководство. Загрузка изображения с помощью конструктора](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Общие сведения об элементе управления PictureBox](picturebox-control-overview-windows-forms.md)
- [Практическое руководство. Установка изображений во время выполнения](how-to-set-pictures-at-run-time-windows-forms.md)
- [Элемент управления PictureBox](picturebox-control-windows-forms.md)
