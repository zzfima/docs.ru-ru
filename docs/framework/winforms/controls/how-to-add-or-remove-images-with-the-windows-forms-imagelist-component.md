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
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a>Практическое руководство. Добавление и удаление изображений, выводимых с помощью компонента ImageList, в Windows Forms
Компонент Форм <xref:System.Windows.Forms.ImageList> Windows обычно заполняется изображениями до того, как он связан с элементом управления. Тем не менее, вы можете добавлять и удалять изображения после связи списка изображений с элементом управления.  
  
> [!NOTE]
> При удалении изображений <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> убедитесь, что свойство любых связанных элементов управления остается действительным.  
  
### <a name="to-add-images-programmatically"></a>Добавление изображений программно  
  
- Используйте <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> метод свойства списка <xref:System.Windows.Forms.ImageList.Images%2A> изображений.  
  
     В следующем примере кода путь, установленный для расположения изображения, является папкой **«Мои документы».** Это место используется, потому что можно предположить, что большинство компьютеров, работающих под управлением операционной системы Windows, будут включать эту папку. Выбор этого местоположения также позволяет пользователям, которые имеют минимальные уровни доступа к системе более безопасно запустить приложение. Следующий пример кода требует, чтобы <xref:System.Windows.Forms.ImageList> у вас была форма с уже добавленным элементом управления.  
  
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
  
### <a name="to-add-images-with-a-key-value"></a>Добавление изображений с ключевым значением.  
  
- Используйте один <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> из методов свойства <xref:System.Windows.Forms.ImageList.Images%2A> списка изображений, который имеет ключевое значение.  
  
     В следующем примере кода путь, установленный для расположения изображения, является папкой **«Мои документы».** Это место используется, потому что можно предположить, что большинство компьютеров, работающих под управлением операционной системы Windows, будут включать эту папку. Выбор этого местоположения также позволяет пользователям, которые имеют минимальные уровни доступа к системе более безопасно запустить приложение. Следующий пример кода требует, чтобы <xref:System.Windows.Forms.ImageList> у вас была форма с уже добавленным элементом управления.  
  
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
  
### <a name="to-remove-all-images-programmatically"></a>Удаление всех изображений программно  
  
- Используйте <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> метод для удаления одного изображения  
  
     ,или-  
  
     Используйте <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> метод для очистки всех изображений в списке изображений.  
  
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
  
### <a name="to-remove-images-by-key"></a>Удаление изображений по клавише  
  
- Используйте <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> метод для удаления одного изображения по его ключу.  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a>См. также раздел

- [Компонент ImageList](imagelist-component-windows-forms.md)
- [Общие сведения о компоненте ImageList](imagelist-component-overview-windows-forms.md)
- [Изображения, Bitmaps и Метафайлы](../advanced/images-bitmaps-and-metafiles.md)
