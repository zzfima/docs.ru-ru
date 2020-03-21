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
ms.openlocfilehash: cd599ac7e07b5210f8bcff1ffbc76b3d9ee563d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182119"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a>Практическое руководство. Установка изображений во время выполнения (Windows Forms)
Можно программно установить изображение, отображаемые элементом управления формами <xref:System.Windows.Forms.PictureBox> Windows.  
  
### <a name="to-set-a-picture-programmatically"></a>Установить картинку программно  
  
- Установите <xref:System.Windows.Forms.PictureBox.Image%2A> свойство <xref:System.Drawing.Image.FromFile%2A> методом <xref:System.Drawing.Image> класса.  
  
     В приведенном ниже примере путь, установленный для расположения изображения, представляет собой папку «Мои документы». Это делается, потому что можно предположить, что большинство компьютеров под управлением операционной системы Windows будет включать в себя этот каталог. Это также позволяет пользователям с минимальным уровнем доступа к системе безопасно запускать приложение. Приведенный ниже пример предполагает <xref:System.Windows.Forms.PictureBox> форму с уже добавленным элементом управления.  
  
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
  
### <a name="to-clear-a-graphic"></a>Чтобы очистить графический  
  
- Во-первых, отпустите память, используемую изображением, а затем очистите графику. Сбор мусора высвободит память позже, если управление памятью станет проблемой.  
  
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
    > Для получения дополнительной информации <xref:System.Drawing.Image.Dispose%2A> о том, почему вы должны использовать метод таким образом, см. [Очистка неуправляемых ресурсов.](../../../standard/garbage-collection/unmanaged.md)  
  
     Этот код очистит изображение, даже если графический был загружен в управление во время проектирования.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [Общие сведения об элементе управления PictureBox](picturebox-control-overview-windows-forms.md)
- [Практическое руководство. Загрузка изображения с помощью конструктора](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Практическое руководство. Изменение размера или размещения изображения во время выполнения](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [Элемент управления PictureBox](picturebox-control-windows-forms.md)
