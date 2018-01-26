---
title: "Практическое руководство. Добавление и удаление изображений, выводимых с помощью компонента ImageList, в Windows Forms"
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
- images [Windows Forms], removing from ImageList component
- images [Windows Forms], storing for controls
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
- images [Windows Forms], displaying with controls
ms.assetid: c5eacc56-f769-4e2e-bfb7-f756620913db
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4e09448cb834453a4c8fce4494ab9fbb53eb0dc3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a>Практическое руководство. Добавление и удаление изображений, выводимых с помощью компонента ImageList, в Windows Forms
Windows Forms <xref:System.Windows.Forms.ImageList> компонента обычно заполняется с изображениями, прежде чем он будет связан с элементом управления. Тем не менее можно добавить и удалить изображения после связывания списка изображений с элементом управления.  
  
> [!NOTE]
>  При удалении изображений, убедитесь, что <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> свойство любых связанных элементов управления по-прежнему допустимо.  
  
### <a name="to-add-images-programmatically"></a>Добавление изображений программными средствами  
  
-   Используйте <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> метод списка изображений <xref:System.Windows.Forms.ImageList.Images%2A> свойство.  
  
     В следующем примере кода путь задан при размещении изображения является **Мои документы** папки. Это расположение используется, так как предполагается, что большинство компьютеров под управлением операционной системы Windows включает эту папку. Эта папка также дает возможность пользователям минимальный уровень доступа к системе более безопасно запустить приложение. В следующем примере кода требуется наличие формы с <xref:System.Windows.Forms.ImageList> управления уже добавлен.  
  
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
  
### <a name="to-add-images-with-a-key-value"></a>Добавление изображений со значением ключа.  
  
-   Используйте один из <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> методы списка изображений <xref:System.Windows.Forms.ImageList.Images%2A> свойства, которое принимает значение ключа.  
  
     В следующем примере кода путь задан при размещении изображения является **Мои документы** папки. Это расположение используется, так как предполагается, что большинство компьютеров под управлением операционной системы Windows включает эту папку. Эта папка также дает возможность пользователям минимальный уровень доступа к системе более безопасно запустить приложение. В следующем примере кода требуется наличие формы с <xref:System.Windows.Forms.ImageList> управления уже добавлен.  
  
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
  
### <a name="to-remove-all-images-programmatically"></a>Чтобы удалить все образы программными средствами  
  
-   Используйте <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> метод для удаления одного образа  
  
     , - или -  
  
     Используйте <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> метод, чтобы удалить все образы в списке изображений.  
  
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
  
### <a name="to-remove-images-by-key"></a>Чтобы удалить рисунки по ключу  
  
-   Используйте <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> метод для удаления одного образа по его ключу.  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a>См. также  
 [Компонент ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)  
 [Общие сведения о компоненте ImageList](../../../../docs/framework/winforms/controls/imagelist-component-overview-windows-forms.md)  
 [Изображения, точечные рисунки и метафайлы](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
