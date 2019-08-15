---
title: Практическое руководство. Задание изображения, отображаемого элементом управления Windows Forms
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
ms.openlocfilehash: 99bde4fac7b3057358c7e6a8550efdb4cc351eb0
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69037879"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>Практическое руководство. Задание изображения, отображаемого элементом управления Windows Forms

Несколько элементов управления Windows Forms могут отображать изображения. Эти изображения могут быть значками, поясняющими назначение элемента управления, например значок дискеты на кнопке, обозначающей команду " **сохранить** ". Кроме того, значки могут быть фоновыми изображениями, чтобы обеспечить необходимый внешний вид и поведение элемента управления.

## <a name="to-set-the-image-displayed-by-a-control"></a>Задание изображения, отображаемого элементом управления

1. Задайте для свойства `Image` или `BackgroundImage` элемента управления объект типа <xref:System.Drawing.Image>. Как правило, изображение будет загружаться из файла с помощью <xref:System.Drawing.Image.FromFile%2A> метода.

     В следующем примере кода путь, заданный для расположения изображения, является папкой " **Мои рисунки** ". Большинство компьютеров, работающих под управлением операционной системы Windows, включают этот каталог. Это также позволяет пользователям с минимальными уровнями доступа к системе безопасно запускать приложение. В следующем примере кода предполагается, что у вас уже есть форма <xref:System.Windows.Forms.PictureBox> с добавленным элементом управления.

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
