---
title: "Практическое руководство. Вывод изображений с использованием GDI+ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "GDI+, отрисовка существующих изображений"
  - "изображения [Windows Forms], создание"
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Вывод изображений с использованием GDI+
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] можно использовать для вывода изображений, которые существуют в приложении в качестве файлов.  Это осуществляется путем создания объекта класса <xref:System.Drawing.Image> \(например объекта <xref:System.Drawing.Bitmap>\), создания объекта <xref:System.Drawing.Graphics>, который ссылается на поверхность рисования, и вызова метода <xref:System.Drawing.Graphics.DrawImage%2A> объекта <xref:System.Drawing.Graphics>.  Изображение будет выведено на поверхность рисования, предоставленную графическим классом.  С помощью редактора изображений можно создавать и редактировать файлы изображений в режиме разработки и отображать их с использованием [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] в режиме выполнения.  Дополнительные сведения см. в разделе [Image Editor for Icons](../Topic/Image%20Editor%20for%20Icons.md).  
  
### Вывод изображения с помощью GDI\+  
  
1.  Создайте объект, представляющий изображение для вывода.  Этот объект должен быть членом класса, наследуемого от <xref:System.Drawing.Image>, например <xref:System.Drawing.Bitmap> или <xref:System.Drawing.Imaging.Metafile>.  Ниже приведен пример.  
  
    ```vb  
    ' Uses the System.Environment.GetFolderPath to get the path to the   
    ' current user's MyPictures folder.  
    Dim myBitmap as New Bitmap _  
       (System.Environment.GetFolderPath _  
          (System.Environment.SpecialFolder.MyPictures))  
  
    ```  
  
    ```csharp  
    // Uses the System.Environment.GetFolderPath to get the path to the   
    // current user's MyPictures folder.  
    Bitmap myBitmap = new Bitmap  
       (System.Environment.GetFolderPath  
          (System.Environment.SpecialFolder.MyPictures));  
  
    ```  
  
    ```cpp  
    // Uses the System.Environment.GetFolderPath to get the path to the   
    // current user's MyPictures folder.  
    Bitmap^ myBitmap = gcnew Bitmap  
       (System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::MyPictures));  
    ```  
  
2.  Создайте объект <xref:System.Drawing.Graphics>, представляющий поверхность рисования для использования.  Дополнительные сведения см. в разделе [Практическое руководство. Создание объектов Graphics для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).  
  
    ```vb  
    ' Creates a Graphics object that represents the drawing surface of   
    ' Button1.  
    Dim g as Graphics = Button1.CreateGraphics  
  
    ```  
  
    ```csharp  
    // Creates a Graphics object that represents the drawing surface of   
    // Button1.  
    Graphics g = Button1.CreateGraphics();  
  
    ```  
  
    ```cpp  
    // Creates a Graphics object that represents the drawing surface of   
    // Button1.  
    Graphics^ g = button1->CreateGraphics();  
    ```  
  
3.  Вызовите метод <xref:System.Drawing.Graphics.DrawImage%2A> графического объекта, чтобы вывести изображение.  Следует указать изображение и координаты для его отображения.  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## См. также  
 [Приступая к программированию графики](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Практическое руководство. Создание объектов Graphics для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Перья, линии и прямоугольники в GDI\+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)   
 [Практическое руководство. Отрисовка текста в Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)   
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Drawing Lines or Closed Figures](../Topic/Drawing%20Lines%20or%20Closed%20Figures%20\(Image%20Editor%20for%20Icons\).md)   
 [Image Editor for Icons](../Topic/Image%20Editor%20for%20Icons.md)