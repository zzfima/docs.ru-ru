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
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a><span data-ttu-id="87a87-102">Как выполнить Задайте изображения, отображаемого элементом управления форм Windows</span><span class="sxs-lookup"><span data-stu-id="87a87-102">How to: Set the Image Displayed by a Windows Forms Control</span></span>
<span data-ttu-id="87a87-103">Несколько элементов управления Windows Forms можно отображать изображения.</span><span class="sxs-lookup"><span data-stu-id="87a87-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="87a87-104">Эти образы могут использоваться значки, объяснение назначения элемента управления, такие как значок дискеты на кнопку, обозначающая **Сохранить** команды.</span><span class="sxs-lookup"><span data-stu-id="87a87-104">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="87a87-105">Кроме того значок может быть фоновые изображения, чтобы предоставить элемент управления, внешний вид и поведение.</span><span class="sxs-lookup"><span data-stu-id="87a87-105">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>  
  
### <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="87a87-106">Чтобы задать изображение, отображаемое элементом управления</span><span class="sxs-lookup"><span data-stu-id="87a87-106">To set the image displayed by a control</span></span>  
  
1.  <span data-ttu-id="87a87-107">Задайте в качестве `Image` или `BackgroundImage` свойство для объекта типа <xref:System.Drawing.Image>.</span><span class="sxs-lookup"><span data-stu-id="87a87-107">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="87a87-108">Как правило, будет загружаться изображения из файла с помощью <xref:System.Drawing.Image.FromFile%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="87a87-108">Generally, you will be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>  
  
     <span data-ttu-id="87a87-109">В следующем примере кода, задайте путь — расположение изображения **Мои рисунки** папки.</span><span class="sxs-lookup"><span data-stu-id="87a87-109">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="87a87-110">Большинство компьютеров под управлением операционной системы Windows, содержат эту папку.</span><span class="sxs-lookup"><span data-stu-id="87a87-110">Most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="87a87-111">Это также позволяет пользователям со систему с минимальным уровнем доступа безопасно работать приложение.</span><span class="sxs-lookup"><span data-stu-id="87a87-111">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="87a87-112">В следующем примере кода требуется наличие формы с помощью <xref:System.Windows.Forms.PictureBox> добавлен элемент управления.</span><span class="sxs-lookup"><span data-stu-id="87a87-112">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="87a87-113">См. также</span><span class="sxs-lookup"><span data-stu-id="87a87-113">See also</span></span>
- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
