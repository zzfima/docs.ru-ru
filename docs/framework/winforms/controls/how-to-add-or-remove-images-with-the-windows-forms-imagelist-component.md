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
ms.openlocfilehash: f531003377395bf219775e5ddb48ceb0822ff0ea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741503"
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a>Практическое руководство. Добавление и удаление изображений с помощью компонента ImageList в Windows Forms
Компонент Windows Forms <xref:System.Windows.Forms.ImageList> обычно заполняется образами, прежде чем он будет связан с элементом управления. Однако можно добавлять и удалять изображения после связывания списка изображений с элементом управления.  
  
> [!NOTE]
> При удалении образов убедитесь, что свойство <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> всех связанных элементов управления по-прежнему допустимо.  
  
### <a name="to-add-images-programmatically"></a>Добавление образов программным способом  
  
- Используйте метод <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> свойства <xref:System.Windows.Forms.ImageList.Images%2A> списка изображений.  
  
     В следующем примере кода путь, заданный для расположения изображения, является папкой " **Мои документы** ". Это расположение используется, поскольку можно предположить, что большинство компьютеров, работающих под управлением операционной системы Windows, будут содержать эту папку. Выбор этого расположения также позволяет пользователям с минимальными уровнями доступа к системе более безопасно запускать приложение. В следующем примере кода требуется, чтобы была уже добавлена форма с <xref:System.Windows.Forms.ImageList> элементом управления.  
  
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
  
### <a name="to-add-images-with-a-key-value"></a>Для добавления изображений со значением ключа.  
  
- Используйте один из <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> методов свойства <xref:System.Windows.Forms.ImageList.Images%2A> списка изображений, которое принимает значение ключа.  
  
     В следующем примере кода путь, заданный для расположения изображения, является папкой " **Мои документы** ". Это расположение используется, поскольку можно предположить, что большинство компьютеров, работающих под управлением операционной системы Windows, будут содержать эту папку. Выбор этого расположения также позволяет пользователям с минимальными уровнями доступа к системе более безопасно запускать приложение. В следующем примере кода требуется, чтобы была уже добавлена форма с <xref:System.Windows.Forms.ImageList> элементом управления.  
  
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
  
### <a name="to-remove-all-images-programmatically"></a>Программное удаление всех образов  
  
- Использование метода <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> для удаления одного образа  
  
     ,-или-  
  
     Используйте метод <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A>, чтобы очистить все изображения в списке изображений.  
  
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
  
### <a name="to-remove-images-by-key"></a>Удаление образов по ключу  
  
- Используйте метод <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> для удаления одного образа по ключу.  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a>См. также:

- [Компонент ImageList](imagelist-component-windows-forms.md)
- [Общие сведения о компоненте ImageList](imagelist-component-overview-windows-forms.md)
- [Изображения, точечные рисунки и метафайлы](../advanced/images-bitmaps-and-metafiles.md)
