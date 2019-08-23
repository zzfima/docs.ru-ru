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
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a>Практическое руководство. Добавление и удаление изображений, выводимых с помощью компонента ImageList, в Windows Forms
Windows Forms <xref:System.Windows.Forms.ImageList> компонент обычно заполняется образами, прежде чем он будет связан с элементом управления. Однако можно добавлять и удалять изображения после связывания списка изображений с элементом управления.  
  
> [!NOTE]
> При удалении образов убедитесь, что <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> свойство всех связанных элементов управления по-прежнему допустимо.  
  
### <a name="to-add-images-programmatically"></a>Добавление образов программным способом  
  
- <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> Используйте метод <xref:System.Windows.Forms.ImageList.Images%2A> свойства списка изображений.  
  
     В следующем примере кода путь, заданный для расположения изображения, является папкой " **Мои документы** ". Это расположение используется, поскольку можно предположить, что большинство компьютеров, работающих под управлением операционной системы Windows, будут содержать эту папку. Выбор этого расположения также позволяет пользователям с минимальными уровнями доступа к системе более безопасно запускать приложение. В следующем примере кода требуется форма с <xref:System.Windows.Forms.ImageList> уже добавленным элементом управления.  
  
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
  
- Используйте один из <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> методов <xref:System.Windows.Forms.ImageList.Images%2A> свойства списка изображений, который принимает значение ключа.  
  
     В следующем примере кода путь, заданный для расположения изображения, является папкой " **Мои документы** ". Это расположение используется, поскольку можно предположить, что большинство компьютеров, работающих под управлением операционной системы Windows, будут содержать эту папку. Выбор этого расположения также позволяет пользователям с минимальными уровнями доступа к системе более безопасно запускать приложение. В следующем примере кода требуется форма с <xref:System.Windows.Forms.ImageList> уже добавленным элементом управления.  
  
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
  
- <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> Использование метода для удаления одного образа  
  
     ,-или-  
  
     <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> Используйте метод, чтобы очистить все изображения в списке изображений.  
  
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
  
- <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> Используйте метод, чтобы удалить одно изображение по ключу.  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a>См. также

- [Компонент ImageList](imagelist-component-windows-forms.md)
- [Общие сведения о компоненте ImageList](imagelist-component-overview-windows-forms.md)
- [Изображения, точечные рисунки и метафайлы](../advanced/images-bitmaps-and-metafiles.md)
