---
title: Практическое руководство. Вывод изображений с использованием GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], creating
- GDI+, rendering existing images
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
ms.openlocfilehash: 6f5b139c6831a065c85e9d9889c259c859a649cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-render-images-with-gdi"></a>Практическое руководство. Вывод изображений с использованием GDI+
Для вывода изображений, которые существуют в виде файлов в приложениях, можно использовать [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. Для этого создается новый объект <xref:System.Drawing.Image> класса (таких как <xref:System.Drawing.Bitmap>), создавая <xref:System.Drawing.Graphics> объекта, который ссылается на поверхность рисования, который вы хотите использовать и вызвать <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> объекта. Изображение будет выведено на поверхность для рисования, представленную классом Graphics. Можно создавать и редактировать файлы изображений во время разработки с помощью редактора изображений и отображать их во время выполнения, используя [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. Дополнительные сведения см. в разделе [Редактор изображений для значков](/cpp/windows/image-editor-for-icons).  
  
### <a name="to-render-an-image-with-gdi"></a>Вывод изображения с помощью GDI+  
  
1.  Создайте объект, представляющий изображение, которое необходимо отобразить. Этот объект должен быть членом класса, который наследует от <xref:System.Drawing.Image>, такие как <xref:System.Drawing.Bitmap> или <xref:System.Drawing.Imaging.Metafile>. Пример:  
  
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
  
2.  Создание <xref:System.Drawing.Graphics> , представляющий поверхность рисования, который вы хотите использовать. Дополнительные сведения см. в разделе [Практическое руководство. Создание графических объектов для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).  
  
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
  
3.  Вызовите <xref:System.Drawing.Graphics.DrawImage%2A> графического объекта, чтобы отобразить изображение. Необходимо указать как само выводимое изображение, так и координаты вывода.  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a>См. также  
 [Приступая к программированию графики](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [Практическое руководство. Создание графических объектов для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Перья, линии и прямоугольники в GDI+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)  
 [Практическое руководство. Рисование текста в Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)  
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Рисование линий и замкнутых фигур](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)  
 [Редактор изображений для значков](/cpp/windows/image-editor-for-icons)
