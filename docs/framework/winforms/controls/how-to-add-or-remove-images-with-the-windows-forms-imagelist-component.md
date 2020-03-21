---
title: Добавление или удаление изображений с помощью компонента ImageList
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
ms.openlocfilehash: e045be7ea9407bc379b0c22282fcd2184ff5db51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182303"
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a><span data-ttu-id="4ddaf-102">Практическое руководство. Добавление и удаление изображений, выводимых с помощью компонента ImageList, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4ddaf-102">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>
<span data-ttu-id="4ddaf-103">Компонент Форм <xref:System.Windows.Forms.ImageList> Windows обычно заполняется изображениями до того, как он связан с элементом управления.</span><span class="sxs-lookup"><span data-stu-id="4ddaf-103">The Windows Forms <xref:System.Windows.Forms.ImageList> component is typically populated with images before it is associated with a control.</span></span> <span data-ttu-id="4ddaf-104">Тем не менее, вы можете добавлять и удалять изображения после связи списка изображений с элементом управления.</span><span class="sxs-lookup"><span data-stu-id="4ddaf-104">However, you can add and remove images after associating the image list with a control.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4ddaf-105">При удалении изображений <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> убедитесь, что свойство любых связанных элементов управления остается действительным.</span><span class="sxs-lookup"><span data-stu-id="4ddaf-105">When you remove images, verify that the <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> property of any associated controls is still valid.</span></span>  
  
### <a name="to-add-images-programmatically"></a><span data-ttu-id="4ddaf-106">Добавление изображений программно</span><span class="sxs-lookup"><span data-stu-id="4ddaf-106">To add images programmatically</span></span>  
  
- <span data-ttu-id="4ddaf-107">Используйте <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> метод свойства списка <xref:System.Windows.Forms.ImageList.Images%2A> изображений.</span><span class="sxs-lookup"><span data-stu-id="4ddaf-107">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> method of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
     <span data-ttu-id="4ddaf-108">В следующем примере кода путь, установленный для расположения изображения, является папкой **«Мои документы».**</span><span class="sxs-lookup"><span data-stu-id="4ddaf-108">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="4ddaf-109">Это место используется, потому что можно предположить, что большинство компьютеров, работающих под управлением операционной системы Windows, будут включать эту папку.</span><span class="sxs-lookup"><span data-stu-id="4ddaf-109">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="4ddaf-110">Выбор этого местоположения также позволяет пользователям, которые имеют минимальные уровни доступа к системе более безопасно запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="4ddaf-110">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="4ddaf-111">Следующий пример кода требует, чтобы <xref:System.Windows.Forms.ImageList> у вас была форма с уже добавленным элементом управления.</span><span class="sxs-lookup"><span data-stu-id="4ddaf-111">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
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
  
### <a name="to-add-images-with-a-key-value"></a><span data-ttu-id="4ddaf-112">Добавление изображений с ключевым значением.</span><span class="sxs-lookup"><span data-stu-id="4ddaf-112">To add images with a key value.</span></span>  
  
- <span data-ttu-id="4ddaf-113">Используйте один <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> из методов свойства <xref:System.Windows.Forms.ImageList.Images%2A> списка изображений, который имеет ключевое значение.</span><span class="sxs-lookup"><span data-stu-id="4ddaf-113">Use one of the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> methods of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property that takes a key value.</span></span>  
  
     <span data-ttu-id="4ddaf-114">В следующем примере кода путь, установленный для расположения изображения, является папкой **«Мои документы».**</span><span class="sxs-lookup"><span data-stu-id="4ddaf-114">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="4ddaf-115">Это место используется, потому что можно предположить, что большинство компьютеров, работающих под управлением операционной системы Windows, будут включать эту папку.</span><span class="sxs-lookup"><span data-stu-id="4ddaf-115">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="4ddaf-116">Выбор этого местоположения также позволяет пользователям, которые имеют минимальные уровни доступа к системе более безопасно запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="4ddaf-116">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="4ddaf-117">Следующий пример кода требует, чтобы <xref:System.Windows.Forms.ImageList> у вас была форма с уже добавленным элементом управления.</span><span class="sxs-lookup"><span data-stu-id="4ddaf-117">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
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
  
### <a name="to-remove-all-images-programmatically"></a><span data-ttu-id="4ddaf-118">Удаление всех изображений программно</span><span class="sxs-lookup"><span data-stu-id="4ddaf-118">To remove all images programmatically</span></span>  
  
- <span data-ttu-id="4ddaf-119">Используйте <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> метод для удаления одного изображения</span><span class="sxs-lookup"><span data-stu-id="4ddaf-119">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> method to remove a single image</span></span>  
  
     <span data-ttu-id="4ddaf-120">,или-</span><span class="sxs-lookup"><span data-stu-id="4ddaf-120">,-or-</span></span>  
  
     <span data-ttu-id="4ddaf-121">Используйте <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> метод для очистки всех изображений в списке изображений.</span><span class="sxs-lookup"><span data-stu-id="4ddaf-121">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> method to clear all images in the image list.</span></span>  
  
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
  
### <a name="to-remove-images-by-key"></a><span data-ttu-id="4ddaf-122">Удаление изображений по клавише</span><span class="sxs-lookup"><span data-stu-id="4ddaf-122">To remove images by key</span></span>  
  
- <span data-ttu-id="4ddaf-123">Используйте <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> метод для удаления одного изображения по его ключу.</span><span class="sxs-lookup"><span data-stu-id="4ddaf-123">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> method to remove a single image by its key.</span></span>  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ddaf-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4ddaf-124">See also</span></span>

- [<span data-ttu-id="4ddaf-125">Компонент ImageList</span><span class="sxs-lookup"><span data-stu-id="4ddaf-125">ImageList Component</span></span>](imagelist-component-windows-forms.md)
- [<span data-ttu-id="4ddaf-126">Общие сведения о компоненте ImageList</span><span class="sxs-lookup"><span data-stu-id="4ddaf-126">ImageList Component Overview</span></span>](imagelist-component-overview-windows-forms.md)
- [<span data-ttu-id="4ddaf-127">Изображения, Bitmaps и Метафайлы</span><span class="sxs-lookup"><span data-stu-id="4ddaf-127">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
