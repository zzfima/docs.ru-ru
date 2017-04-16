---
title: "Практическое руководство. Создание объектов Graphics для рисования | Microsoft Docs"
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
  - "GDI+, создание изображений"
  - "графика [Windows Forms], создание"
  - "Graphics - класс"
  - "изображения [Windows Forms], создание"
ms.assetid: 162861f9-f050-445e-8abb-b2c43a918b8b
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Практическое руководство. Создание объектов Graphics для рисования
Перед тем как рисовать линии и фигуры, отображать текст, выводить изображения и управлять ими в [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] необходимо создать объект <xref:System.Drawing.Graphics>.  Объект <xref:System.Drawing.Graphics> представляет поверхность рисования [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] и используется для создания графических изображений.  
  
 Ниже представлены два этапа работы с графикой.  
  
1.  Создание объекта <xref:System.Drawing.Graphics>.  
  
2.  Использование объекта <xref:System.Drawing.Graphics> для рисования линий и фигур, отображения текста или изображения и управления ими.  
  
## Создание объекта Graphics  
 Существуют различные способы создания графических объектов.  
  
#### Создание объекта Graphics  
  
-   Получите ссылку на объект Graphics через объект <xref:System.Windows.Forms.PaintEventArgs> при обработке события <xref:System.Windows.Forms.Control.Paint> формы или элемента управления.  Это обычный способ получения ссылки на графический объект при создании кода рисования элементов управления.  Подобным образом можно получить графический объект как свойство объекта <xref:System.Drawing.Printing.PrintPageEventArgs> при обработке события <xref:System.Drawing.Printing.PrintDocument.PrintPage> для <xref:System.Drawing.Printing.PrintDocument>.  
  
     \-или\-  
  
-   Вызовите метод <xref:System.Windows.Forms.Control.CreateGraphics%2A> элемента управления или формы, чтобы получить ссылку на объект <xref:System.Drawing.Graphics>, соответствующий поверхности рисования этой формы или элемента управления.  Используйте этот подход, если необходимо рисовать на поверхности уже существующей формы или элемента управления.  
  
     \-или\-  
  
-   Создайте объект <xref:System.Drawing.Graphics> из любого объекта, унаследованного от класса <xref:System.Drawing.Image>.  Этот способ используется, когда требуется изменить существующее изображение.  
  
     Ниже все эти процедуры описаны более подробно.  
  
## PaintEventArgs в обработчике события Paint  
 При создании обработчика события <xref:System.Windows.Forms.PaintEventHandler> для элементов управления или объекта <xref:System.Drawing.Printing.PrintDocument.PrintPage> для <xref:System.Drawing.Printing.PrintDocument>, графический объект предоставляется как одно из свойств объекта <xref:System.Windows.Forms.PaintEventArgs> или <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
#### Получение ссылки на объект Graphics из объекта PaintEventArgs в событии Paint  
  
1.  Объявите объект <xref:System.Drawing.Graphics>.  
  
2.  Присвойте переменной ссылку на объект <xref:System.Drawing.Graphics>, передаваемый как часть <xref:System.Windows.Forms.PaintEventArgs>.  
  
3.  Вставьте код для рисования формы или элемента управления.  
  
     В следующем примере показано, как создавать ссылку на объект <xref:System.Drawing.Graphics> из объекта <xref:System.Windows.Forms.PaintEventArgs> события <xref:System.Windows.Forms.Control.Paint>.  
  
    ```vb  
    Private Sub Form1_Paint(sender As Object, pe As PaintEventArgs) Handles _  
       MyBase.Paint  
       ' Declares the Graphics object and sets it to the Graphics object  
       ' supplied in the PaintEventArgs.  
       Dim g As Graphics = pe.Graphics  
       ' Insert code to paint the form here.  
    End Sub  
  
    ```  
  
    ```csharp  
    private void Form1_Paint(object sender,   
       System.Windows.Forms.PaintEventArgs pe)   
    {  
       // Declares the Graphics object and sets it to the Graphics object  
       // supplied in the PaintEventArgs.  
       Graphics g = pe.Graphics;  
       // Insert code to paint the form here.  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void Form1_Paint(System::Object ^ sender,  
          System::Windows::Forms::PaintEventArgs ^ pe)  
       {  
          // Declares the Graphics object and sets it to the Graphics object  
          // supplied in the PaintEventArgs.  
          Graphics ^ g = pe->Graphics;  
          // Insert code to paint the form here.  
       }  
    ```  
  
## Метод CreateGraphics  
 Для получения ссылки на объект <xref:System.Drawing.Graphics>, который соответствует поверхности рисования формы или элемента управления, можно также использовать метод <xref:System.Windows.Forms.Control.CreateGraphics%2A> этой формы или элемента управления.  
  
#### Создание объекта Graphics с помощью метода CreateGraphics  
  
-   Вызовите метод <xref:System.Windows.Forms.Control.CreateGraphics%2A> формы или элемента управления, на котором необходимо отобразить графику.  
  
    ```vb  
    Dim g as Graphics  
    ' Sets g to a Graphics object representing the drawing surface of the  
    ' control or form g is a member of.  
    g = Me.CreateGraphics  
  
    ```  
  
    ```csharp  
    Graphics g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this.CreateGraphics();  
  
    ```  
  
    ```cpp  
    Graphics ^ g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this->CreateGraphics();  
    ```  
  
## Создание из объекта Image  
 Объект Graphics можно создать из любого объекта, производного от класса <xref:System.Drawing.Image>.  
  
#### Создание объекта Graphics из объекта Image  
  
-   Вызовите метод <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=fullName> переменной Image, из которой нужно создать объект <xref:System.Drawing.Graphics>.  
  
     В следующем примере показывается, как использовать объект <xref:System.Drawing.Bitmap>.  
  
    ```vb  
    Dim myBitmap as New Bitmap("C:\Documents and Settings\Joe\Pics\myPic.bmp")  
    Dim g as Graphics = Graphics.FromImage(myBitmap)  
  
    ```  
  
    ```csharp  
    Bitmap myBitmap = new Bitmap(@"C:\Documents and   
       Settings\Joe\Pics\myPic.bmp");  
    Graphics g = Graphics.FromImage(myBitmap);  
  
    ```  
  
    ```cpp  
    Bitmap ^ myBitmap = gcnew  
       Bitmap("D:\\Documents and Settings\\Joe\\Pics\\myPic.bmp");  
    Graphics ^ g = Graphics::FromImage(myBitmap);  
    ```  
  
> [!NOTE]
>  Создание объектов <xref:System.Drawing.Graphics> возможно только из неиндексированных BMP\-файлов, таких как 16\-разрядные, 24\-разрядные и 32\-разрядные BMP\-файлы.  Каждый пиксель неиндексированного BMP\-файла содержит сведения о цвете, в отличие от пикселей индексированного BMP\-файла, которые содержат указатели на таблицу цветов.  
  
## Рисование фигур и изображений и управление ими  
 После создания объекта <xref:System.Drawing.Graphics> его можно использовать для рисования линий и фигур, отображения текста или изображения и управления ими.  Ниже представлены основные объекты, используемые с объектом <xref:System.Drawing.Graphics>.  
  
-   Класс <xref:System.Drawing.Pen> — служит для рисования линий, контуров и отрисовки других геометрических объектов.  
  
-   Класс <xref:System.Drawing.Brush> — служит для заливки областей, например фигур, изображений или текста.  
  
-   Класс <xref:System.Drawing.Font> — содержит описание фигур, которые должны использоваться при отрисовке текста.  
  
-   Структура <xref:System.Drawing.Color> — содержит различные цвета.  
  
#### Использование созданного объекта Graphics  
  
-   Используйте перечисленные выше объекты, чтобы рисовать нужные изображения.  
  
     Дополнительные сведения см. в следующих разделах.  
  
    |Объект|См.|  
    |------------|---------|  
    |Строки|[Практическое руководство. Рисование линии в Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)|  
    |Фигуры|[Практическое руководство. Рисование линии или контурной фигуры](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)|  
    |Текст|[Практическое руководство. Отрисовка текста в Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)|  
    |Изображения|[Практическое руководство. Вывод изображений с использованием GDI\+](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)|  
  
## См. также  
 [Приступая к программированию графики](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Прямые и кривые линии и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Практическое руководство. Вывод изображений с использованием GDI\+](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)