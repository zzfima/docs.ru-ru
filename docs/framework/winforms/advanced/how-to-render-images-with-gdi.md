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
ms.openlocfilehash: fffe1f1052d7323d234985b7e752866f2e89657d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182505"
---
# <a name="how-to-render-images-with-gdi"></a>Практическое руководство. Вывод изображений с использованием GDI+
Для визуализации изображений, существующих в приложениях, можно использовать GDI-образы. Это делается путем создания <xref:System.Drawing.Image> нового объекта <xref:System.Drawing.Bitmap>класса (например), создания <xref:System.Drawing.Graphics> объекта, отсылающего <xref:System.Drawing.Graphics.DrawImage%2A> к поверхности рисунка, которую вы хотите использовать, и вызова метода <xref:System.Drawing.Graphics> объекта. Изображение будет выведено на поверхность для рисования, представленную классом Graphics. Редактор изображений можно использовать для создания и ред., файлы изображений во время проектирования, а также для визуализации их с помощью GDI во время выполнения. Дополнительные сведения см. в разделе [Редактор изображений для значков](/cpp/windows/image-editor-for-icons).  
  
### <a name="to-render-an-image-with-gdi"></a>Вывод изображения с помощью GDI+  
  
1. Создайте объект, представляющий изображение, которое необходимо отобразить. Этот объект должен быть членом класса, <xref:System.Drawing.Image>который <xref:System.Drawing.Bitmap> наследует от, таких как или <xref:System.Drawing.Imaging.Metafile>. Пример:  
  
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
  
2. Создайте <xref:System.Drawing.Graphics> объект, представляющий поверхность рисунка, которую вы хотите использовать. Дополнительные сведения см. в разделе [Практическое руководство. Создание графических объектов для рисования](how-to-create-graphics-objects-for-drawing.md).  
  
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
  
3. Вызовите <xref:System.Drawing.Graphics.DrawImage%2A> графический объект для визуализации изображения. Необходимо указать как само выводимое изображение, так и координаты вывода.  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a>См. также раздел

- [Приступая к программированию графики](getting-started-with-graphics-programming.md)
- [Практическое руководство. Создание объектов Graphics для рисования](how-to-create-graphics-objects-for-drawing.md)
- [Перья, линии и прямоугольники в GDI+](pens-lines-and-rectangles-in-gdi.md)
- [Практическое руководство. Отрисовка текста в Windows Forms](how-to-draw-text-on-a-windows-form.md)
- [Объекты Graphics и Drawing в Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Рисование линий и замкнутых фигур](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)
- [Редактор изображений для значков](/cpp/windows/image-editor-for-icons)
