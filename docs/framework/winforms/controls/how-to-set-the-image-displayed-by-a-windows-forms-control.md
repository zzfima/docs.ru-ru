---
title: "Практическое руководство. Определение изображения, отображаемого элементом управления Windows Forms | Microsoft Docs"
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
  - "Button - элемент управления [Windows Forms], изображения"
  - "элементы управления [Windows Forms], изображения"
  - "примеры [Windows Forms], элементы управления"
  - "изображения [Windows Forms], элементы управления Windows Forms"
  - "элементы управления Windows Forms, изображения"
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Определение изображения, отображаемого элементом управления Windows Forms
На многих элементах управления Windows Forms могут отображаться рисунки.  В качестве этих рисунков могут использоваться значки, поясняющие назначение элемента управления, например, значок дискеты на кнопке, соответствующей команде **Сохранить**.  В качестве значков можно также использовать фоновые изображения, чтобы придать значку требуемый внешний вид и поведение.  
  
### Чтобы задать рисунок, отображаемый на элементе управления  
  
1.  Присвойте свойству `Image` или `BackgroundImage` элемента управления объект типа <xref:System.Drawing.Image>.  Как правило, изображение будет загружаться из файла при помощи метода <xref:System.Drawing.Image.FromFile%2A>.  
  
     В следующем примере кода в качестве местоположения изображения выбрана папка **Мои рисунки**.  Эта папка имеется на большинстве компьютеров, работающих под управлением операционной системы Windows.  Кроме того, если используется эта папка, то для запуска приложения достаточен минимальный уровень доступа к системе.  Для следующего примера кода требуется форма с заранее добавленным элементом управления <xref:System.Windows.Forms.PictureBox>.  
  
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
  
## См. также  
 <xref:System.Drawing.Image.FromFile%2A>   
 <xref:System.Drawing.Image>   
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>