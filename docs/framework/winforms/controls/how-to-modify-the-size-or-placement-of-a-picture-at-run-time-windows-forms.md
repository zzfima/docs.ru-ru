---
title: Практическое руководство. Изменение размера или размещения изображения во время выполнения (Windows Forms)
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
ms.openlocfilehash: 9e6e114e0a9d7e5e9c17ba21ef941703cd108784
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534778"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>Практическое руководство. Изменение размера или размещения изображения во время выполнения (Windows Forms)
Если вы используете Windows Forms <xref:System.Windows.Forms.PictureBox> элемента управления в форме, можно задать <xref:System.Windows.Forms.PictureBox.SizeMode%2A> свойства:  
  
-   Выравнивание верхнего левого угла изображения с верхнего левого угла элемента управления  
  
-   Центрировать изображение в элементе управления  
  
-   Изменить размер элемента управления по размеру изображения, которые в нем отображаются  
  
-   Изменять размеры рисунка в соответствии с размерами элемента управления  
  
 Растяжение рисунка (особенно в формат растрового изображения) может привести к ухудшению качества изображения. Метафайлы, в которых перечислены инструкции для создания изображений во время выполнения, лучше подходят для растяжения границ, чем растровые изображения.  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>Чтобы задать свойства SizeMode во время выполнения  
  
1.  Задать <xref:System.Windows.Forms.PictureBox.SizeMode%2A> для <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (по умолчанию), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, или <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>. <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> означает, что изображение размещается в левом верхнем углу элемента управления; Если изображение больше, чем элемент управления, его нижняя и правая границы обрезаются. <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> означает, что изображение по центру элемента управления; Если изображение больше, чем элемент управления, его внешние границы обрезаются. <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> означает, что размер элемента управления размер изображения. <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> является обратным и означает, что размер изображения размер элемента управления.  
  
     В следующем примере в расположение образа выбрана папка «Мои документы». Эта операция необходима, поскольку можно предположить, что большинство компьютеров под управлением операционной системы Windows включает этот каталог. Это также позволяет пользователям с минимальным уровнем доступа к системе безопасно запускать приложение. В приведенном ниже примере предполагается наличие формы с <xref:System.Windows.Forms.PictureBox> управления уже добавлен.  
  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.PictureBox>  
 [Практическое руководство. Загрузка изображения с помощью конструктора](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)  
 [Общие сведения об элементе управления PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [Практическое руководство. Установка изображений во время выполнения](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [Элемент управления PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
