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
ms.openlocfilehash: 9bb094ce0b7945f23a2e9b8614e56c9492d5f832
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736034"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>Практическое руководство. Изменение размера или размещения изображения во время выполнения (Windows Forms)
Если в форме используется элемент управления <xref:System.Windows.Forms.PictureBox> Windows Forms, можно задать для него свойство <xref:System.Windows.Forms.PictureBox.SizeMode%2A>:  
  
- Выровняйте верхний левый угол изображения по левому верхнему углу элемента управления  
  
- Центрирование рисунка внутри элемента управления  
  
- Настройка размера элемента управления в соответствии с отображаемым изображением  
  
- Растяжение всех рисунков, которые отображаются в соответствии с элементом управления  
  
 Растяжение изображения (особенно в формате точечного рисунка) может привести к ухудшению качества изображения. Метафайлы, представляющие собой списки графических инструкций для рисования изображений во время выполнения, лучше подходят для растяжения по сравнению с точечными рисунками.  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>Задание свойства Сиземоде во время выполнения  
  
1. Задайте для <xref:System.Windows.Forms.PictureBox.SizeMode%2A> значение <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (по умолчанию), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>или <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>. <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> означает, что изображение помещается в левый верхний угол элемента управления; Если изображение больше элемента управления, его нижний и правый края обрезаются. <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> означает, что изображение центрируется в элементе управления; Если изображение больше элемента управления, внешние края рисунка обрезаются. <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> означает, что размер элемента управления изменяется в соответствии с размером изображения. <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> является обратным и означает, что размер изображения корректируется до размера элемента управления.  
  
     В приведенном ниже примере путь, заданный для расположения изображения, является папкой "Мои документы". Это делается, поскольку можно предположить, что большинство компьютеров, работающих под управлением операционной системы Windows, будут включать этот каталог. Это также позволяет пользователям с минимальным уровнем доступа к системе безопасно запускать приложение. В приведенном ниже примере предполагается, что форма с уже добавленным элементом управления <xref:System.Windows.Forms.PictureBox>.  
  
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
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.PictureBox>
- [Практическое руководство. Загрузка изображения с помощью конструктора](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Общие сведения об элементе управления PictureBox](picturebox-control-overview-windows-forms.md)
- [Практическое руководство. Установка изображений во время выполнения](how-to-set-pictures-at-run-time-windows-forms.md)
- [Элемент управления PictureBox](picturebox-control-windows-forms.md)
