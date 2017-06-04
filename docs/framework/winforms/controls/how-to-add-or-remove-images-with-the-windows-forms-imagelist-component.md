---
title: "Практическое руководство. Добавление и удаление изображений, выводимых с помощью компонента ImageList, в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ImageList - компонент [Windows Forms], добавление изображений"
  - "ImageList - компонент [Windows Forms], удаление изображений"
  - "изображения [Windows Forms], добавление в компонент ImageList"
  - "изображения [Windows Forms], отображение с помощью элементов управления"
  - "изображения [Windows Forms], удаление из компонента ImageList"
  - "изображения [Windows Forms], хранение для элементов управления"
ms.assetid: c5eacc56-f769-4e2e-bfb7-f756620913db
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Добавление и удаление изображений, выводимых с помощью компонента ImageList, в Windows Forms
Компонент Windows Forms <xref:System.Windows.Forms.ImageList> обычно заполняется рисунками перед связыванием с каким\-либо элементом управления.  Однако добавление и удаление рисунков возможно и после связывания этого компонента с элементом управления.  
  
> [!NOTE]
>  При удалении рисунков обеспечьте, чтобы оставалось действительным свойство <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> любых связанных элементов управления.  
  
### Чтобы добавить рисунки с помощью программных средств  
  
-   Используйте метод <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> свойства <xref:System.Windows.Forms.ImageList.Images%2A> набора изображений.  
  
     В следующем примере кода в качестве местоположения изображения выбрана папка **Мои документы**.  Такой выбор объясняется тем, что эта папка имеется на большинстве компьютеров, работающих под управлением операционной системы Windows.  Кроме того, если используется эта папка, то для запуска приложения достаточен минимальный уровень доступа к системе.  Для следующего примера кода требуется форма с заранее добавленным элементом управления <xref:System.Windows.Forms.ImageList>.  
  
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
  
### Добавление изображений со значением ключа.  
  
-   Используйте один из методов <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> свойства <xref:System.Windows.Forms.ImageList.Images%2A> набора изображений, которое принимает значение ключа.  
  
     В следующем примере кода в качестве местоположения изображения выбрана папка **Мои документы**.  Такой выбор объясняется тем, что эта папка имеется на большинстве компьютеров, работающих под управлением операционной системы Windows.  Кроме того, если используется эта папка, то для запуска приложения достаточен минимальный уровень доступа к системе.  Для следующего примера кода требуется форма с заранее добавленным элементом управления <xref:System.Windows.Forms.ImageList>.  
  
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
  
### Чтобы удалить все изображения с помощью программных средств  
  
-   Используйте метод <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> для удаления одного изображения  
  
     \-либо\-  
  
     Используйте метод <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> для удаления всех изображений в наборе.  
  
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
  
### Чтобы удалить рисунки по ключу  
  
-   Используйте метод <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> для удаления отдельного изображения по ключу.  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
  
```  
  
## См. также  
 [Компонент ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)   
 [Общие сведения о компоненте ImageList](../../../../docs/framework/winforms/controls/imagelist-component-overview-windows-forms.md)   
 [Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)