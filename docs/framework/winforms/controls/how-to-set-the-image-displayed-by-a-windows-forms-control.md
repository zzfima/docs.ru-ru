---
title: Практическое руководство. Определение изображения, отображаемого элементом управления Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
ms.openlocfilehash: 4870f9e2acc48a90e1e2193d514926fedee05f61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>Практическое руководство. Определение изображения, отображаемого элементом управления Windows Forms
Несколько элементов управления Windows Forms можно отображать изображения. Эти образы могут использоваться значки, поясняющие назначение элемента управления, например, значок дискеты на кнопке, отвечающий за **Сохранить** команды. Кроме того значок может быть фоновые изображения, чтобы предоставить элемент управления, внешний вид и поведение.  
  
### <a name="to-set-the-image-displayed-by-a-control"></a>Чтобы задать изображение, отображаемое на элементе управления  
  
1.  Задайте в качестве `Image` или `BackgroundImage` свойство для объекта типа <xref:System.Drawing.Image>. Как правило, будет загружаться изображение из файла с помощью <xref:System.Drawing.Image.FromFile%2A> метод.  
  
     В следующем примере кода путь задан при размещении изображения является **Мои рисунки** папки. Большинство компьютеров под управлением операционной системы Windows, содержат эту папку. Это также позволяет пользователям с уровнями доступа минимальные системные для безопасной работы приложения. В следующем примере кода требуется наличие формы с <xref:System.Windows.Forms.PictureBox> управления добавлен.  
  
    ```vb  
    ' Replace the image named below  
    ' with an icon of your own choosing.  
    PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.MyPictures) _  
       & "\Image.gif")  
    ```  
  
    ```csharp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.MyPictures)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    pictureBox1->Image = Image::FromFile(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::MyPictures),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Image.FromFile%2A>  
 <xref:System.Drawing.Image>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>
