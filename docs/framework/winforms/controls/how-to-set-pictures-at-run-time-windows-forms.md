---
title: Практическое руководство. Установка изображений во время выполнения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pictures [Windows Forms], setting display
- examples [Windows Forms], PictureBox control
- bitmaps [Windows Forms], displaying in PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding images
- images [Windows Forms], adding with PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 18ca41d0-68a5-4660-985e-a6c1fbc01d76
ms.openlocfilehash: bd0509c05fd9c1cfc0c631fcd613c64d20296f6b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746746"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a>Практическое руководство. Установка изображений во время выполнения (Windows Forms)
Можно программно задать изображение, отображаемое Windows Forms элементом управления <xref:System.Windows.Forms.PictureBox>.  
  
### <a name="to-set-a-picture-programmatically"></a>Установка рисунка программным способом  
  
- Задайте свойство <xref:System.Windows.Forms.PictureBox.Image%2A> с помощью метода <xref:System.Drawing.Image.FromFile%2A> класса <xref:System.Drawing.Image>.  
  
     В приведенном ниже примере путь, заданный для расположения изображения, является папкой "Мои документы". Это делается, поскольку можно предположить, что большинство компьютеров, работающих под управлением операционной системы Windows, будут включать этот каталог. Это также позволяет пользователям с минимальным уровнем доступа к системе безопасно запускать приложение. В приведенном ниже примере предполагается, что форма с уже добавленным элементом управления <xref:System.Windows.Forms.PictureBox>.  
  
    ```vb  
    Private Sub LoadNewPict()  
       ' You should replace the bold image   
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadNewPict(){  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    }  
    ```  
  
    ```cpp  
    private:  
       void LoadNewPict()  
       {  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
### <a name="to-clear-a-graphic"></a>Очистка графического изображения  
  
- Сначала освободите память, используемую изображением, а затем очистите изображение. Если управление памятью становится проблемой, сборка мусора освободит память позже.  
  
    ```vb  
    If Not (PictureBox1.Image Is Nothing) Then  
       PictureBox1.Image.Dispose()  
       PictureBox1.Image = Nothing  
    End If  
    ```  
  
    ```csharp  
    if (pictureBox1.Image != null)   
    {  
       pictureBox1.Image.Dispose();  
       pictureBox1.Image = null;  
    }  
    ```  
  
    ```cpp  
    if (pictureBox1->Image != nullptr)  
    {  
       pictureBox1->Image->Dispose();  
       pictureBox1->Image = nullptr;  
    }  
    ```  
  
    > [!NOTE]
    > Дополнительные сведения о том, почему следует использовать метод <xref:System.Drawing.Image.Dispose%2A> таким образом, см. в разделе [Очистка неуправляемых ресурсов](../../../standard/garbage-collection/unmanaged.md).  
  
     Этот код очистит изображение, даже если изображение было загружено в элемент управления во время разработки.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [Общие сведения об элементе управления PictureBox](picturebox-control-overview-windows-forms.md)
- [Практическое руководство. Загрузка изображения с помощью конструктора](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Практическое руководство. Изменение размера или размещения изображения во время выполнения](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [Элемент управления PictureBox](picturebox-control-windows-forms.md)
