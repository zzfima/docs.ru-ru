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
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a><span data-ttu-id="0f924-102">Практическое руководство. Задание изображения, отображаемого элементом управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0f924-102">How to: Set the image displayed by a Windows Forms control</span></span>

<span data-ttu-id="0f924-103">Несколько элементов управления Windows Forms могут отображать изображения.</span><span class="sxs-lookup"><span data-stu-id="0f924-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="0f924-104">Эти изображения могут быть значками, поясняющими назначение элемента управления, например значок дискеты на кнопке, обозначающей команду " **сохранить** ".</span><span class="sxs-lookup"><span data-stu-id="0f924-104">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="0f924-105">Кроме того, значки могут быть фоновыми изображениями, чтобы обеспечить необходимый внешний вид и поведение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0f924-105">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>

## <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="0f924-106">Задание изображения, отображаемого элементом управления</span><span class="sxs-lookup"><span data-stu-id="0f924-106">To set the image displayed by a control</span></span>

1. <span data-ttu-id="0f924-107">Задайте для свойства `Image` или `BackgroundImage` элемента управления объект типа <xref:System.Drawing.Image>.</span><span class="sxs-lookup"><span data-stu-id="0f924-107">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="0f924-108">Как правило, изображение будет загружаться из файла с помощью <xref:System.Drawing.Image.FromFile%2A> метода.</span><span class="sxs-lookup"><span data-stu-id="0f924-108">Generally, you will be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>

     <span data-ttu-id="0f924-109">В следующем примере кода путь, заданный для расположения изображения, является папкой " **Мои рисунки** ".</span><span class="sxs-lookup"><span data-stu-id="0f924-109">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="0f924-110">Большинство компьютеров, работающих под управлением операционной системы Windows, включают этот каталог.</span><span class="sxs-lookup"><span data-stu-id="0f924-110">Most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="0f924-111">Это также позволяет пользователям с минимальными уровнями доступа к системе безопасно запускать приложение.</span><span class="sxs-lookup"><span data-stu-id="0f924-111">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="0f924-112">В следующем примере кода предполагается, что у вас уже есть форма <xref:System.Windows.Forms.PictureBox> с добавленным элементом управления.</span><span class="sxs-lookup"><span data-stu-id="0f924-112">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="0f924-113">См. также</span><span class="sxs-lookup"><span data-stu-id="0f924-113">See also</span></span>

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
