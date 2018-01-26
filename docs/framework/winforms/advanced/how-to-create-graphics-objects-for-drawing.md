---
title: "Практическое руководство. Создание объектов Graphics для рисования"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating
- images [Windows Forms], creating
- GDI+, creating images
ms.assetid: 162861f9-f050-445e-8abb-b2c43a918b8b
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d4b626d3d87c6537b74b6d28e086303474ea2c3e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-graphics-objects-for-drawing"></a>Практическое руководство. Создание объектов Graphics для рисования
Перед тем как выводить линий и фигур, отображения текста или отображения и управлять ими с [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], необходимо создать <xref:System.Drawing.Graphics> объекта. <xref:System.Drawing.Graphics> Представляет [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] поверхности для рисования и является объектом, который используется для создания графических изображений.  
  
 При работе с графикой существует два действия:  
  
1.  Создание <xref:System.Drawing.Graphics> объекта.  
  
2.  С помощью <xref:System.Drawing.Graphics> объект для рисования линий и фигур, отображения текста или отображения и управления ими.  
  
## <a name="creating-a-graphics-object"></a>Создание графических объектов  
 Графические объекты могут создаваться различными способами.  
  
#### <a name="to-create-a-graphics-object"></a>Чтобы создать объект графики  
  
-   Получить ссылку на объект graphics как часть <xref:System.Windows.Forms.PaintEventArgs> в <xref:System.Windows.Forms.Control.Paint> событий формы или элемента управления. Это обычный способ получения ссылки на графический объект при создании кода рисования для элемента управления. Аналогичным образом можно получить графический объект как свойство <xref:System.Drawing.Printing.PrintPageEventArgs> при обработке <xref:System.Drawing.Printing.PrintDocument.PrintPage> событий для <xref:System.Drawing.Printing.PrintDocument>.  
  
     - или -  
  
-   Вызовите <xref:System.Windows.Forms.Control.CreateGraphics%2A> метод элемента управления или формы, чтобы получить ссылку на <xref:System.Drawing.Graphics> , представляющий поверхность рисования объекта формы или элемента управления. Используйте этот метод, чтобы рисовать на формы или элемента управления, который уже существует.  
  
     - или -  
  
-   Создание <xref:System.Drawing.Graphics> объект из любого объекта, который наследует от <xref:System.Drawing.Image>. Этот подход полезен, когда требуется изменить существующее изображение.  
  
     В следующих разделах приводятся сведения о каждой из этих процессов.  
  
## <a name="painteventargs-in-the-paint-event-handler"></a>PaintEventArgs в обработчике событий рисования  
 При программировании <xref:System.Windows.Forms.PaintEventHandler> для элементов управления или <xref:System.Drawing.Printing.PrintDocument.PrintPage> для <xref:System.Drawing.Printing.PrintDocument>, графический объект предоставляется как одно из свойств объекта <xref:System.Windows.Forms.PaintEventArgs> или <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a>Для получения ссылки на графические объекты из PaintEventArgs в событие рисования  
  
1.  Объявите <xref:System.Drawing.Graphics> объекта.  
  
2.  Назначьте переменной для ссылки на <xref:System.Drawing.Graphics> объект, передаваемый как часть <xref:System.Windows.Forms.PaintEventArgs>.  
  
3.  Вставьте код для рисования формы или элемента управления.  
  
     В следующем примере показано, как ссылаться на <xref:System.Drawing.Graphics> объекта из <xref:System.Windows.Forms.PaintEventArgs> в <xref:System.Windows.Forms.Control.Paint> событий:  
  
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
  
## <a name="creategraphics-method"></a>Метод CreateGraphics  
 Можно также использовать <xref:System.Windows.Forms.Control.CreateGraphics%2A> метод элемента управления или формы, чтобы получить ссылку на <xref:System.Drawing.Graphics> , представляющий поверхность рисования объекта формы или элемента управления.  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a>Чтобы создать объект графики с метод CreateGraphics  
  
-   Вызовите <xref:System.Windows.Forms.Control.CreateGraphics%2A> метод формы или элемента управления, по которому необходимо для отрисовки графики.  
  
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
  
## <a name="create-from-an-image-object"></a>Создание из объекта Image  
 Кроме того, можно создать объект графики из любого объекта, производного от <xref:System.Drawing.Image> класса.  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a>Чтобы создать объект графики из изображения  
  
-   Вызовите <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> метод, указав имя переменной образа, из которого требуется создать <xref:System.Drawing.Graphics> объекта.  
  
     В следующем примере показано, как использовать <xref:System.Drawing.Bitmap> объекта:  
  
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
>  Можно создать только <xref:System.Drawing.Graphics> объекты из неиндексированных BMP-файлов, например, 16, 24 и 32-разрядных BMP-файлы. Каждая точка неиндексированного BMP-файла содержит сведения о цвете, в отличие от точек индексированного BMP-файлы, которые содержат указатели на таблицу цветов.  
  
-  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a>Рисование и управления ими фигуры и изображения  
 После его создания, <xref:System.Drawing.Graphics> объект может использоваться для рисования линий и фигур, отображения текста или отображения и управления ими. Объекты principal, которые используются с <xref:System.Drawing.Graphics> объекта:  
  
-   <xref:System.Drawing.Pen> Класс, используемый для рисования линий, контуров и отрисовки других геометрических объектов.  
  
-   <xref:System.Drawing.Brush> Класс, используемый для заливки областей, например фигур, изображений или текста.  
  
-   <xref:System.Drawing.Font> Класса — содержит описание фигур, которые должны использоваться при отображении текста.  
  
-   <xref:System.Drawing.Color> Структуры — содержит различные цвета для отображения.  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a>Чтобы использовать графический объект, который вы создали  
  
-   Работа с соответствующего объекта, перечисленные выше для рисования, что нужно.  
  
     Дополнительные сведения см. в следующих разделах:  
  
    |Для подготовки к просмотру|См.|  
    |---------------|---------|  
    |Прямые линии|[Практическое руководство. Рисование линии в Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)|  
    |Фигуры|[Практическое руководство. Рисование контурной фигуры](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)|  
    |Text|[Практическое руководство. Рисование текста в Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)|  
    |Изображения|[Практическое руководство. Прорисовка изображений с использованием GDI+](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a>См. также  
 [Приступая к программированию графики](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Линии, кривые и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Практическое руководство. Прорисовка изображений с использованием GDI+](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)
