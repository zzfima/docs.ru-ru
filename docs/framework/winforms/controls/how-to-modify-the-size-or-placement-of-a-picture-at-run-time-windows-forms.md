---
title: Как выполнить Изменение размера или размещения изображения во время выполнения (Windows Forms)
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
ms.openlocfilehash: fa8bdf17f7dc7f6d09059e54b208acaec6207e48
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604786"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>Как выполнить Изменение размера или размещения изображения во время выполнения (Windows Forms)
При использовании Windows Forms <xref:System.Windows.Forms.PictureBox> элемента управления в форме, можно задать <xref:System.Windows.Forms.PictureBox.SizeMode%2A> свойства:  
  
-   Выравнивание верхнего левого угла рисунка с верхнего левого угла элемента управления  
  
-   Центрировать изображение в элементе управления  
  
-   Размер элемента управления в соответствии с рисунка  
  
-   Изменять размеры рисунка в соответствии с размерами элемента управления  
  
 Растяжение рисунка (особенно в формат точечного рисунка) может привести к ухудшению качества изображения. Метафайлы, в которых перечислены инструкции для создания изображений во время выполнения, лучше подходят для растягивания чем растровые изображения.  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>Чтобы задать свойство размеров во время выполнения  
  
1.  Задайте <xref:System.Windows.Forms.PictureBox.SizeMode%2A> для <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (по умолчанию), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, или <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>. <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> означает, что изображение размещается в левом верхнем углу элемента управления; Если изображение больше, чем элемент управления, его нижняя и правая границы обрезаются. <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> означает, что изображение по центру элемента управления; Если изображение больше, чем элемент управления, его внешние края обрезаются. <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> означает, что размер элемента управления имеет размер изображения. <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> является обратным и означает, что размер изображения размер элемента управления.  
  
     В следующем примере в расположение образа выбрана папка «Мои документы». Это делается, поскольку предполагается, что большинство компьютеров под управлением операционной системы Windows, содержат эту папку. Это также позволяет пользователям с минимальным уровнем доступа к системе безопасно запускать приложение. В приведенном ниже примере предполагается, что форма <xref:System.Windows.Forms.PictureBox> управления уже добавлен.  
  
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
- <xref:System.Windows.Forms.PictureBox>
- [Практическое руководство. Загрузка изображения с помощью конструктора](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Общие сведения об элементе управления PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)
- [Практическое руководство. Установка изображений во время выполнения](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)
- [Элемент управления PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
