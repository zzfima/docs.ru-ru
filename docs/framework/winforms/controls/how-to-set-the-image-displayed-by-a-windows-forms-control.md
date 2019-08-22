---
title: Практическое руководство. Задание изображения, отображаемого элементом управления Windows Forms
ms.date: 08/20/2019
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
ms.openlocfilehash: b1b1dbbb50c3b19cf8d8a7d7030d0bc168afb6a7
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666190"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>Практическое руководство. Задание изображения, отображаемого элементом управления Windows Forms

Несколько элементов управления Windows Forms могут отображать изображения. Эти изображения могут быть значками, поясняющими назначение элемента управления, например значок дискеты на кнопке, обозначающей команду "Сохранить". Кроме того, значки могут быть фоновыми изображениями, чтобы обеспечить необходимый внешний вид и поведение элемента управления.

## <a name="programmatic"></a>Программный

Задайте для свойства `Image` или `BackgroundImage` элемента управления объект типа <xref:System.Drawing.Image>. Как правило, вы загружаете образ из файла с помощью <xref:System.Drawing.Image.FromFile%2A> метода.

В следующем примере кода путь, заданный для расположения изображения, является папкой " **Мои рисунки** ". Большинство компьютеров, работающих под управлением операционной системы Windows, включают этот каталог. Это также позволяет пользователям с минимальными уровнями доступа к системе безопасно запускать приложение. В следующем примере кода предполагается, что у вас уже есть форма <xref:System.Windows.Forms.PictureBox> с добавленным элементом управления.

```vb
' Replace the image named below with your own icon.
PictureBox1.Image = Image.FromFile _
   (System.Environment.GetFolderPath _
   (System.Environment.SpecialFolder.MyPictures) _
   & "\Image.gif")
```

```csharp
// Replace the image named below with your own icon.
// Note the escape character used (@) when specifying the path.
pictureBox1.Image = Image.FromFile
   (System.Environment.GetFolderPath
   (System.Environment.SpecialFolder.MyPictures)
   + @"\Image.gif");
```

```cpp
// Replace the image named below with your own icon.
pictureBox1->Image = Image::FromFile(String::Concat
   (System::Environment::GetFolderPath
   (System::Environment::SpecialFolder::MyPictures),
   "\\Image.gif"));
```

## <a name="designer"></a>Designer

1. В окне **Свойства** в Visual Studio выберите свойство **Image** или **BackgroundImage** элемента управления, а затем нажмите кнопку с многоточием (![многоточие в Visual Studio](./media/visual-studio-ellipsis-button.png)), чтобы отобразить окно **Выбор** Диалоговое окно "ресурс".

2. Выберите изображение, которое требуется отобразить.

## <a name="see-also"></a>См. также

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
