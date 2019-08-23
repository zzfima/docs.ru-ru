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
ms.openlocfilehash: 430b7f573b115c21b9e2fa87f0ace74205717285
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925120"
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a><span data-ttu-id="a4da2-102">Практическое руководство. Добавление и удаление изображений, выводимых с помощью компонента ImageList, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a4da2-102">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>
<span data-ttu-id="a4da2-103">Windows Forms <xref:System.Windows.Forms.ImageList> компонент обычно заполняется образами, прежде чем он будет связан с элементом управления.</span><span class="sxs-lookup"><span data-stu-id="a4da2-103">The Windows Forms <xref:System.Windows.Forms.ImageList> component is typically populated with images before it is associated with a control.</span></span> <span data-ttu-id="a4da2-104">Однако можно добавлять и удалять изображения после связывания списка изображений с элементом управления.</span><span class="sxs-lookup"><span data-stu-id="a4da2-104">However, you can add and remove images after associating the image list with a control.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a4da2-105">При удалении образов убедитесь, что <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> свойство всех связанных элементов управления по-прежнему допустимо.</span><span class="sxs-lookup"><span data-stu-id="a4da2-105">When you remove images, verify that the <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> property of any associated controls is still valid.</span></span>  
  
### <a name="to-add-images-programmatically"></a><span data-ttu-id="a4da2-106">Добавление образов программным способом</span><span class="sxs-lookup"><span data-stu-id="a4da2-106">To add images programmatically</span></span>  
  
- <span data-ttu-id="a4da2-107"><xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> Используйте метод <xref:System.Windows.Forms.ImageList.Images%2A> свойства списка изображений.</span><span class="sxs-lookup"><span data-stu-id="a4da2-107">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> method of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
     <span data-ttu-id="a4da2-108">В следующем примере кода путь, заданный для расположения изображения, является папкой " **Мои документы** ".</span><span class="sxs-lookup"><span data-stu-id="a4da2-108">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="a4da2-109">Это расположение используется, поскольку можно предположить, что большинство компьютеров, работающих под управлением операционной системы Windows, будут содержать эту папку.</span><span class="sxs-lookup"><span data-stu-id="a4da2-109">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="a4da2-110">Выбор этого расположения также позволяет пользователям с минимальными уровнями доступа к системе более безопасно запускать приложение.</span><span class="sxs-lookup"><span data-stu-id="a4da2-110">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="a4da2-111">В следующем примере кода требуется форма с <xref:System.Windows.Forms.ImageList> уже добавленным элементом управления.</span><span class="sxs-lookup"><span data-stu-id="a4da2-111">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
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
  
### <a name="to-add-images-with-a-key-value"></a><span data-ttu-id="a4da2-112">Для добавления изображений со значением ключа.</span><span class="sxs-lookup"><span data-stu-id="a4da2-112">To add images with a key value.</span></span>  
  
- <span data-ttu-id="a4da2-113">Используйте один из <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> методов <xref:System.Windows.Forms.ImageList.Images%2A> свойства списка изображений, который принимает значение ключа.</span><span class="sxs-lookup"><span data-stu-id="a4da2-113">Use one of the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> methods of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property that takes a key value.</span></span>  
  
     <span data-ttu-id="a4da2-114">В следующем примере кода путь, заданный для расположения изображения, является папкой " **Мои документы** ".</span><span class="sxs-lookup"><span data-stu-id="a4da2-114">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="a4da2-115">Это расположение используется, поскольку можно предположить, что большинство компьютеров, работающих под управлением операционной системы Windows, будут содержать эту папку.</span><span class="sxs-lookup"><span data-stu-id="a4da2-115">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="a4da2-116">Выбор этого расположения также позволяет пользователям с минимальными уровнями доступа к системе более безопасно запускать приложение.</span><span class="sxs-lookup"><span data-stu-id="a4da2-116">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="a4da2-117">В следующем примере кода требуется форма с <xref:System.Windows.Forms.ImageList> уже добавленным элементом управления.</span><span class="sxs-lookup"><span data-stu-id="a4da2-117">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
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
  
### <a name="to-remove-all-images-programmatically"></a><span data-ttu-id="a4da2-118">Программное удаление всех образов</span><span class="sxs-lookup"><span data-stu-id="a4da2-118">To remove all images programmatically</span></span>  
  
- <span data-ttu-id="a4da2-119"><xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> Использование метода для удаления одного образа</span><span class="sxs-lookup"><span data-stu-id="a4da2-119">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> method to remove a single image</span></span>  
  
     <span data-ttu-id="a4da2-120">,-или-</span><span class="sxs-lookup"><span data-stu-id="a4da2-120">,-or-</span></span>  
  
     <span data-ttu-id="a4da2-121"><xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> Используйте метод, чтобы очистить все изображения в списке изображений.</span><span class="sxs-lookup"><span data-stu-id="a4da2-121">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> method to clear all images in the image list.</span></span>  
  
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
  
### <a name="to-remove-images-by-key"></a><span data-ttu-id="a4da2-122">Удаление образов по ключу</span><span class="sxs-lookup"><span data-stu-id="a4da2-122">To remove images by key</span></span>  
  
- <span data-ttu-id="a4da2-123"><xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> Используйте метод, чтобы удалить одно изображение по ключу.</span><span class="sxs-lookup"><span data-stu-id="a4da2-123">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> method to remove a single image by its key.</span></span>  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4da2-124">См. также</span><span class="sxs-lookup"><span data-stu-id="a4da2-124">See also</span></span>

- [<span data-ttu-id="a4da2-125">Компонент ImageList</span><span class="sxs-lookup"><span data-stu-id="a4da2-125">ImageList Component</span></span>](imagelist-component-windows-forms.md)
- [<span data-ttu-id="a4da2-126">Общие сведения о компоненте ImageList</span><span class="sxs-lookup"><span data-stu-id="a4da2-126">ImageList Component Overview</span></span>](imagelist-component-overview-windows-forms.md)
- [<span data-ttu-id="a4da2-127">Изображения, точечные рисунки и метафайлы</span><span class="sxs-lookup"><span data-stu-id="a4da2-127">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
