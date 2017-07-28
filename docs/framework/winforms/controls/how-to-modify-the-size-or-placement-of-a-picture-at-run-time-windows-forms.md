---
title: "Практическое руководство. Изменение размера или размещения изображения во время выполнения (Windows Forms) | Microsoft Docs"
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
  - "примеры [Windows Forms], PictureBox - элемент управления"
  - "изображения [Windows Forms], управление размещением в элементе управления PictureBox [Windows Forms]"
  - "PictureBox - элемент управления [Windows Forms], размер и выравнивание рисунка"
  - "рисунки, управление размещением в элементе управления PictureBox [Windows Forms]"
ms.assetid: d0b332a3-fae2-4891-957c-dc3e17743326
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Изменение размера или размещения изображения во время выполнения (Windows Forms)
Если элемент управления Windows Forms <xref:System.Windows.Forms.PictureBox> используется в форме, имеется возможность с помощью свойства <xref:System.Windows.Forms.PictureBox.SizeMode%2A>:  
  
-   Выровнять левый верхний угол рисунка по левому верхнему углу элемента управления  
  
-   Поместить рисунок в центре элемента управления  
  
-   Изменять размеры элемента управления в соответствии с размерами отображаемого рисунка  
  
-   Изменять размеры рисунка в соответствии с размерами элемента управления  
  
 Растяжение границ рисунка \(особенно в растровом формате\) может привести к ухудшению качества изображения.  Метафайлы, в которых перечислены инструкции для создания изображений во время выполнения, лучше подходят для растяжения границ, чем растровые изображения.  
  
### Чтобы задать значение свойству SizeMode во время выполнения  
  
1.  Задайте для свойства <xref:System.Windows.Forms.PictureBox.SizeMode%2A> значение <xref:System.Windows.Forms.PictureBoxSizeMode> \(по умолчанию\), <xref:System.Windows.Forms.PictureBoxSizeMode>, <xref:System.Windows.Forms.PictureBoxSizeMode> или <xref:System.Windows.Forms.PictureBoxSizeMode>.  <xref:System.Windows.Forms.PictureBoxSizeMode> означает, что изображение размещается в левом верхнему углу элемента управления; если изображение больше элемента управления, его правый и нижний края обрезаются.  <xref:System.Windows.Forms.PictureBoxSizeMode> означает, что изображение выравнивается по центру элемента управления; если изображение больше элемента управления, его края обрезаются.  <xref:System.Windows.Forms.PictureBoxSizeMode> означает, что размер элемента управления определяется размером изображения.  <xref:System.Windows.Forms.PictureBoxSizeMode> наоборот означает, что размер элемента изображения определяется размером элемента управления.  
  
     В приведенном ниже примере в пути для расположения отображаемых рисунков указана папка "Мои документы".  Такой выбор объясняется тем, что эта папка имеется на большинстве компьютеров, работающих под управлением операционной системы Windows.  Кроме того, если используется эта папка, то для запуска приложения достаточен минимальный уровень доступа к системе.  В примере, представленном ниже, подразумевается, что элемент управления <xref:System.Windows.Forms.PictureBox> уже добавлен в форму.  
  
    ```vb  
    Private Sub StretchPic()  
       ' Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage  
       ' Load the picture into the control.  
       ' You should replace the bold image   
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
  
    ```  
  
    ```csharp  
    private void StretchPic(){  
       // Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage;  
       // Load the picture into the control.  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Image.gif")  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void StretchPic()  
       {  
          // Stretch the picture to fit the control.  
          pictureBox1->SizeMode = PictureBoxSizeMode::StretchImage;  
          // Load the picture into the control.  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.PictureBox>   
 [Практическое руководство. Загрузка изображения с помощью конструктора](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)   
 [Общие сведения об элементе управления PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)   
 [Практическое руководство. Установка изображений во время выполнения](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)   
 [Элемент управления PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)