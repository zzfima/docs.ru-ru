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
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a><span data-ttu-id="f2ab6-102">Практическое руководство. Задание изображения, отображаемого элементом управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f2ab6-102">How to: Set the image displayed by a Windows Forms control</span></span>

<span data-ttu-id="f2ab6-103">Несколько элементов управления Windows Forms могут отображать изображения.</span><span class="sxs-lookup"><span data-stu-id="f2ab6-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="f2ab6-104">Эти изображения могут быть значками, поясняющими назначение элемента управления, например значок дискеты на кнопке, обозначающей команду "Сохранить".</span><span class="sxs-lookup"><span data-stu-id="f2ab6-104">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the Save command.</span></span> <span data-ttu-id="f2ab6-105">Кроме того, значки могут быть фоновыми изображениями, чтобы обеспечить необходимый внешний вид и поведение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f2ab6-105">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>

## <a name="programmatic"></a><span data-ttu-id="f2ab6-106">Программный</span><span class="sxs-lookup"><span data-stu-id="f2ab6-106">Programmatic</span></span>

<span data-ttu-id="f2ab6-107">Задайте для свойства `Image` или `BackgroundImage` элемента управления объект типа <xref:System.Drawing.Image>.</span><span class="sxs-lookup"><span data-stu-id="f2ab6-107">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="f2ab6-108">Как правило, вы загружаете образ из файла с помощью <xref:System.Drawing.Image.FromFile%2A> метода.</span><span class="sxs-lookup"><span data-stu-id="f2ab6-108">Generally, you'll be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>

<span data-ttu-id="f2ab6-109">В следующем примере кода путь, заданный для расположения изображения, является папкой " **Мои рисунки** ".</span><span class="sxs-lookup"><span data-stu-id="f2ab6-109">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="f2ab6-110">Большинство компьютеров, работающих под управлением операционной системы Windows, включают этот каталог.</span><span class="sxs-lookup"><span data-stu-id="f2ab6-110">Most computers running the Windows operating system include this directory.</span></span> <span data-ttu-id="f2ab6-111">Это также позволяет пользователям с минимальными уровнями доступа к системе безопасно запускать приложение.</span><span class="sxs-lookup"><span data-stu-id="f2ab6-111">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="f2ab6-112">В следующем примере кода предполагается, что у вас уже есть форма <xref:System.Windows.Forms.PictureBox> с добавленным элементом управления.</span><span class="sxs-lookup"><span data-stu-id="f2ab6-112">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>

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

## <a name="designer"></a><span data-ttu-id="f2ab6-113">Designer</span><span class="sxs-lookup"><span data-stu-id="f2ab6-113">Designer</span></span>

1. <span data-ttu-id="f2ab6-114">В окне **Свойства** в Visual Studio выберите свойство **Image** или **BackgroundImage** элемента управления, а затем нажмите кнопку с многоточием (![многоточие в Visual Studio](./media/visual-studio-ellipsis-button.png)), чтобы отобразить окно **Выбор** Диалоговое окно "ресурс".</span><span class="sxs-lookup"><span data-stu-id="f2ab6-114">In the **Properties** window of Visual Studio, select the **Image** or **BackgroundImage** property of the control, and then select the ellipsis (![Ellipsis button in Visual Studio](./media/visual-studio-ellipsis-button.png)) to display the **Select Resource** dialog box.</span></span>

2. <span data-ttu-id="f2ab6-115">Выберите изображение, которое требуется отобразить.</span><span class="sxs-lookup"><span data-stu-id="f2ab6-115">Select the image you want to display.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2ab6-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f2ab6-116">See also</span></span>

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
