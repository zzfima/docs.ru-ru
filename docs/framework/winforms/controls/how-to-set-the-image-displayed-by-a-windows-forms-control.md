---
title: "Практическое руководство. Определение изображения, отображаемого элементом управления Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6d9f4d806b39e6e1272ddbb60befdaf8c76e46b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a><span data-ttu-id="da1c7-102">Практическое руководство. Определение изображения, отображаемого элементом управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da1c7-102">How to: Set the Image Displayed by a Windows Forms Control</span></span>
<span data-ttu-id="da1c7-103">Несколько элементов управления Windows Forms можно отображать изображения.</span><span class="sxs-lookup"><span data-stu-id="da1c7-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="da1c7-104">Эти образы могут использоваться значки, поясняющие назначение элемента управления, например, значок дискеты на кнопке, отвечающий за **Сохранить** команды.</span><span class="sxs-lookup"><span data-stu-id="da1c7-104">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="da1c7-105">Кроме того значок может быть фоновые изображения, чтобы предоставить элемент управления, внешний вид и поведение.</span><span class="sxs-lookup"><span data-stu-id="da1c7-105">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>  
  
### <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="da1c7-106">Чтобы задать изображение, отображаемое на элементе управления</span><span class="sxs-lookup"><span data-stu-id="da1c7-106">To set the image displayed by a control</span></span>  
  
1.  <span data-ttu-id="da1c7-107">Задайте в качестве `Image` или `BackgroundImage` свойство для объекта типа <xref:System.Drawing.Image>.</span><span class="sxs-lookup"><span data-stu-id="da1c7-107">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="da1c7-108">Как правило, будет загружаться изображение из файла с помощью <xref:System.Drawing.Image.FromFile%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="da1c7-108">Generally, you will be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>  
  
     <span data-ttu-id="da1c7-109">В следующем примере кода путь задан при размещении изображения является **Мои рисунки** папки.</span><span class="sxs-lookup"><span data-stu-id="da1c7-109">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="da1c7-110">Большинство компьютеров под управлением операционной системы Windows, содержат эту папку.</span><span class="sxs-lookup"><span data-stu-id="da1c7-110">Most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="da1c7-111">Это также позволяет пользователям с уровнями доступа минимальные системные для безопасной работы приложения.</span><span class="sxs-lookup"><span data-stu-id="da1c7-111">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="da1c7-112">В следующем примере кода требуется наличие формы с <xref:System.Windows.Forms.PictureBox> управления добавлен.</span><span class="sxs-lookup"><span data-stu-id="da1c7-112">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="da1c7-113">См. также</span><span class="sxs-lookup"><span data-stu-id="da1c7-113">See Also</span></span>  
 <xref:System.Drawing.Image.FromFile%2A>  
 <xref:System.Drawing.Image>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>
