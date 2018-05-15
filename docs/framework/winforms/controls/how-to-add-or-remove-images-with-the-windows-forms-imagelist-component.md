---
title: Практическое руководство. Добавление и удаление изображений, выводимых с помощью компонента ImageList, в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], removing from ImageList component
- images [Windows Forms], storing for controls
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
- images [Windows Forms], displaying with controls
ms.assetid: c5eacc56-f769-4e2e-bfb7-f756620913db
ms.openlocfilehash: e5c563c4f46924a95936bc5a51862230f2cbdb99
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a><span data-ttu-id="034c8-102">Практическое руководство. Добавление и удаление изображений, выводимых с помощью компонента ImageList, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="034c8-102">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>
<span data-ttu-id="034c8-103">Windows Forms <xref:System.Windows.Forms.ImageList> компонента обычно заполняется с изображениями, прежде чем он будет связан с элементом управления.</span><span class="sxs-lookup"><span data-stu-id="034c8-103">The Windows Forms <xref:System.Windows.Forms.ImageList> component is typically populated with images before it is associated with a control.</span></span> <span data-ttu-id="034c8-104">Тем не менее можно добавить и удалить изображения после связывания списка изображений с элементом управления.</span><span class="sxs-lookup"><span data-stu-id="034c8-104">However, you can add and remove images after associating the image list with a control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="034c8-105">При удалении изображений, убедитесь, что <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> свойство любых связанных элементов управления по-прежнему допустимо.</span><span class="sxs-lookup"><span data-stu-id="034c8-105">When you remove images, verify that the <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> property of any associated controls is still valid.</span></span>  
  
### <a name="to-add-images-programmatically"></a><span data-ttu-id="034c8-106">Добавление изображений программными средствами</span><span class="sxs-lookup"><span data-stu-id="034c8-106">To add images programmatically</span></span>  
  
-   <span data-ttu-id="034c8-107">Используйте <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> метод списка изображений <xref:System.Windows.Forms.ImageList.Images%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="034c8-107">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> method of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
     <span data-ttu-id="034c8-108">В следующем примере кода путь задан при размещении изображения является **Мои документы** папки.</span><span class="sxs-lookup"><span data-stu-id="034c8-108">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="034c8-109">Это расположение используется, так как предполагается, что большинство компьютеров под управлением операционной системы Windows включает эту папку.</span><span class="sxs-lookup"><span data-stu-id="034c8-109">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="034c8-110">Эта папка также дает возможность пользователям минимальный уровень доступа к системе более безопасно запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="034c8-110">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="034c8-111">В следующем примере кода требуется наличие формы с <xref:System.Windows.Forms.ImageList> управления уже добавлен.</span><span class="sxs-lookup"><span data-stu-id="034c8-111">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
    ```vb  
    Public Sub LoadImage()  
       Dim myImage As System.Drawing.Image = _  
         Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
       ImageList1.Images.Add(myImage)  
    End Sub  
    ```  
  
    ```csharp  
    public void addImage()  
    {  
    // Be sure that you use an appropriate escape sequence (such as the   
    // @) when specifying the location of the file.  
       System.Drawing.Image myImage =   
         Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
       imageList1.Images.Add(myImage);  
    }  
    ```  
  
    ```cpp  
    public:  
       void addImage()  
       {  
       // Replace the bold image in the following sample   
       // with your own icon.  
       // Be sure that you use an appropriate escape sequence (such as   
       // \\) when specifying the location of the file.  
          System::Drawing::Image ^ myImage =   
             Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
          imageList1->Images->Add(myImage);  
       }  
    ```  
  
### <a name="to-add-images-with-a-key-value"></a><span data-ttu-id="034c8-112">Добавление изображений со значением ключа.</span><span class="sxs-lookup"><span data-stu-id="034c8-112">To add images with a key value.</span></span>  
  
-   <span data-ttu-id="034c8-113">Используйте один из <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> методы списка изображений <xref:System.Windows.Forms.ImageList.Images%2A> свойства, которое принимает значение ключа.</span><span class="sxs-lookup"><span data-stu-id="034c8-113">Use one of the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> methods of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property that takes a key value.</span></span>  
  
     <span data-ttu-id="034c8-114">В следующем примере кода путь задан при размещении изображения является **Мои документы** папки.</span><span class="sxs-lookup"><span data-stu-id="034c8-114">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="034c8-115">Это расположение используется, так как предполагается, что большинство компьютеров под управлением операционной системы Windows включает эту папку.</span><span class="sxs-lookup"><span data-stu-id="034c8-115">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="034c8-116">Эта папка также дает возможность пользователям минимальный уровень доступа к системе более безопасно запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="034c8-116">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="034c8-117">В следующем примере кода требуется наличие формы с <xref:System.Windows.Forms.ImageList> управления уже добавлен.</span><span class="sxs-lookup"><span data-stu-id="034c8-117">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
    ```vb  
    Public Sub LoadImage()  
       Dim myImage As System.Drawing.Image = _  
         Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
       ImageList1.Images.Add("myPhoto", myImage)  
    End Sub  
    ```  
  
```csharp  
public void addImage()  
{  
// Be sure that you use an appropriate escape sequence (such as the   
// @) when specifying the location of the file.  
   System.Drawing.Image myImage =   
     Image.FromFile  
   (System.Environment.GetFolderPath  
   (System.Environment.SpecialFolder.Personal)  
   + @"\Image.gif");  
   imageList1.Images.Add("myPhoto", myImage);  
}  
```  
  
1.  
  
### <a name="to-remove-all-images-programmatically"></a><span data-ttu-id="034c8-118">Чтобы удалить все образы программными средствами</span><span class="sxs-lookup"><span data-stu-id="034c8-118">To remove all images programmatically</span></span>  
  
-   <span data-ttu-id="034c8-119">Используйте <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> метод для удаления одного образа</span><span class="sxs-lookup"><span data-stu-id="034c8-119">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> method to remove a single image</span></span>  
  
     <span data-ttu-id="034c8-120">, - или -</span><span class="sxs-lookup"><span data-stu-id="034c8-120">,-or-</span></span>  
  
     <span data-ttu-id="034c8-121">Используйте <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> метод, чтобы удалить все образы в списке изображений.</span><span class="sxs-lookup"><span data-stu-id="034c8-121">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> method to clear all images in the image list.</span></span>  
  
    ```vb  
    ' Removes the first image in the image list  
    ImageList1.Images.Remove(myImage)  
    ' Clears all images in the image list  
    ImageList1.Images.Clear()  
    ```  
  
```csharp  
// Removes the first image in the image list.  
imageList1.Images.Remove(myImage);  
// Clears all images in the image list.  
imageList1.Images.Clear();  
```  
  
### <a name="to-remove-images-by-key"></a><span data-ttu-id="034c8-122">Чтобы удалить рисунки по ключу</span><span class="sxs-lookup"><span data-stu-id="034c8-122">To remove images by key</span></span>  
  
-   <span data-ttu-id="034c8-123">Используйте <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> метод для удаления одного образа по его ключу.</span><span class="sxs-lookup"><span data-stu-id="034c8-123">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> method to remove a single image by its key.</span></span>  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a><span data-ttu-id="034c8-124">См. также</span><span class="sxs-lookup"><span data-stu-id="034c8-124">See Also</span></span>  
 [<span data-ttu-id="034c8-125">Компонент ImageList</span><span class="sxs-lookup"><span data-stu-id="034c8-125">ImageList Component</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)  
 [<span data-ttu-id="034c8-126">Общие сведения о компоненте ImageList</span><span class="sxs-lookup"><span data-stu-id="034c8-126">ImageList Component Overview</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-overview-windows-forms.md)  
 [<span data-ttu-id="034c8-127">Изображения, точечные рисунки и метафайлы</span><span class="sxs-lookup"><span data-stu-id="034c8-127">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
