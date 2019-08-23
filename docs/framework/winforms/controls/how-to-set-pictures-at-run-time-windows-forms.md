---
title: Практическое руководство. Задание изображений во время выполнения (Windows Forms)
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
ms.openlocfilehash: 99d78a275c8ad8f55d9b0832a794545b65da7e20
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917529"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a>Практическое руководство. Задание изображений во время выполнения (Windows Forms)
Можно программно задать изображение, отображаемое Windows Formsным <xref:System.Windows.Forms.PictureBox> элементом управления.  
  
### <a name="to-set-a-picture-programmatically"></a>Установка рисунка программным способом  
  
- Задайте свойство с помощью <xref:System.Drawing.Image>методакласса. <xref:System.Drawing.Image.FromFile%2A> <xref:System.Windows.Forms.PictureBox.Image%2A>  
  
     В приведенном ниже примере путь, заданный для расположения изображения, является папкой "Мои документы". Это делается, поскольку можно предположить, что большинство компьютеров, работающих под управлением операционной системы Windows, будут включать этот каталог. Это также позволяет пользователям с минимальным уровнем доступа к системе безопасно запускать приложение. В приведенном ниже примере предполагается, <xref:System.Windows.Forms.PictureBox> что форма с уже добавленным элементом управления.  
  
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
    > Дополнительные сведения о том, почему следует использовать <xref:System.Drawing.Image.Dispose%2A> метод таким образом, см. в разделе Очистка неуправляемых [ресурсов](../../../standard/garbage-collection/unmanaged.md).  
  
     Этот код очистит изображение, даже если изображение было загружено в элемент управления во время разработки.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [Общие сведения об элементе управления PictureBox](picturebox-control-overview-windows-forms.md)
- [Практическое руководство. Загрузка изображения с помощью конструктора](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Практическое руководство. Изменение размера или расположения изображения во время выполнения](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [Элемент управления PictureBox](picturebox-control-windows-forms.md)
