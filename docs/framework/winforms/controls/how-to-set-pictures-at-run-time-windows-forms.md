---
title: "Практическое руководство. Установка изображений во время выполнения (Windows Forms) | Microsoft Docs"
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
  - "растровые изображения [Windows Forms], отображение в элементе управления PictureBox [Windows Forms]"
  - "примеры [Windows Forms], PictureBox - элемент управления"
  - "изображения [Windows Forms], добавление с помощью элемента управления PictureBox [Windows Forms]"
  - "PictureBox - элемент управления [Windows Forms], добавление изображений"
  - "PictureBox - элемент управления [Windows Forms], добавление рисунков"
  - "рисунки, настройка отображения"
ms.assetid: 18ca41d0-68a5-4660-985e-a6c1fbc01d76
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Установка изображений во время выполнения (Windows Forms)
Имеется возможность задания рисунка, отображаемого элементом управления Windows Forms <xref:System.Windows.Forms.PictureBox>, программными средствами.  
  
### Чтобы задать рисунок программными средствами  
  
-   Задайте свойство <xref:System.Windows.Forms.PictureBox.Image%2A> при помощи метода <xref:System.Drawing.Image.FromFile%2A> класса <xref:System.Drawing.Image>.  
  
     В приведенном ниже примере в пути для расположения отображаемых рисунков указана папка "Мои документы".  Такой выбор объясняется тем, что эта папка имеется на большинстве компьютеров, работающих под управлением операционной системы Windows.  Кроме того, если используется эта папка, то для запуска приложения достаточен минимальный уровень доступа к системе.  В примере, представленном ниже, подразумевается, что элемент управления <xref:System.Windows.Forms.PictureBox> уже добавлен в форму.  
  
    ```vb  
    Private Sub LoadNewPict()  
       ' You should replace the bold image   
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
  
    ```  
  
    ```csharp  
    private void LoadNewPict(){  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void LoadNewPict()  
       {  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
### Удаление графического объекта  
  
-   Сначала освободите память, используемую изображением, а затем удалите графический объект.  При наличии проблем с управлением памятью, она будет очищена позднее при сборке мусора.  
  
    ```vb  
    If Not (PictureBox1.Image Is Nothing) Then  
       PictureBox1.Image.Dispose()  
       PictureBox1.Image = Nothing  
    End If  
  
    ```  
  
    ```csharp  
    if (pictureBox1.Image != null)   
    {  
       pictureBox1.Image.Dispose();  
       pictureBox1.Image = null;  
    }  
  
    ```  
  
    ```cpp  
    if (pictureBox1->Image != nullptr)  
    {  
       pictureBox1->Image->Dispose();  
       pictureBox1->Image = nullptr;  
    }  
    ```  
  
    > [!NOTE]
    >  Дополнительные сведения с описанием причины использования метода <xref:System.Drawing.Image.Dispose%2A> таким образом см. в разделе [Cleaning Up Unmanaged Resources](../../../../docs/standard/garbage-collection/unmanaged.md).  
  
     Этот код удалит изображение даже в том случае, если графический объект был загружен в элемент управления в режиме разработки.  
  
## См. также  
 <xref:System.Windows.Forms.PictureBox>   
 <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName>   
 [Общие сведения об элементе управления PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)   
 [Практическое руководство. Загрузка изображения с помощью конструктора](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)   
 [Практическое руководство. Изменение размера или размещения изображения во время выполнения](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)   
 [Элемент управления PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)