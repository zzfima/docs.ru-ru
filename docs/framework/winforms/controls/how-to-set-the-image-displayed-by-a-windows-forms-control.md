---
title: Как выполнить Задайте изображения, отображаемого элементом управления форм Windows
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
ms.openlocfilehash: 93bc7970ce7c287273f8bd7ff50b07c6658e2a08
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644928"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>Как выполнить Задайте изображения, отображаемого элементом управления форм Windows
Несколько элементов управления Windows Forms можно отображать изображения. Эти образы могут использоваться значки, объяснение назначения элемента управления, такие как значок дискеты на кнопку, обозначающая **Сохранить** команды. Кроме того значок может быть фоновые изображения, чтобы предоставить элемент управления, внешний вид и поведение.  
  
### <a name="to-set-the-image-displayed-by-a-control"></a>Чтобы задать изображение, отображаемое элементом управления  
  
1.  Задайте в качестве `Image` или `BackgroundImage` свойство для объекта типа <xref:System.Drawing.Image>. Как правило, будет загружаться изображения из файла с помощью <xref:System.Drawing.Image.FromFile%2A> метод.  
  
     В следующем примере кода, задайте путь — расположение изображения **Мои рисунки** папки. Большинство компьютеров под управлением операционной системы Windows, содержат эту папку. Это также позволяет пользователям со систему с минимальным уровнем доступа безопасно работать приложение. В следующем примере кода требуется наличие формы с помощью <xref:System.Windows.Forms.PictureBox> добавлен элемент управления.  
  
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
- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
