---
title: Практическое руководство. Создание объектов Graphics для рисования
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating
- images [Windows Forms], creating
- GDI+, creating images
ms.assetid: 162861f9-f050-445e-8abb-b2c43a918b8b
ms.openlocfilehash: d591d65904484e33285e5db7aa99760f3e1909d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142437"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a>Практическое руководство. Создание объектов Graphics для рисования
Прежде чем нарисовать линии и формы, визуализировать текст или отобразить и манипулировать изображениями с помощью GDI, необходимо создать <xref:System.Drawing.Graphics> объект. Объект <xref:System.Drawing.Graphics> представляет поверхность рисунка GDI и является объектом, который используется для создания графических изображений.  
  
 В работе с графикой есть два шага:  
  
1. Создание <xref:System.Drawing.Graphics> объекта.  
  
2. Использование <xref:System.Drawing.Graphics> объекта для рисования линий и форм, визуализации текста или отображения и манипулирования изображениями.  
  
## <a name="creating-a-graphics-object"></a>Создание графического объекта  
 Графический объект может быть создан различными способами.  
  
#### <a name="to-create-a-graphics-object"></a>Создание графического объекта  
  
- Получить ссылку на графический объект <xref:System.Windows.Forms.PaintEventArgs> как <xref:System.Windows.Forms.Control.Paint> часть формы или управления. Обычно таким образом вы получаете ссылку на графический объект при создании кода живописи для элемента управления. Аналогичным образом, вы также можете получить графический объект <xref:System.Drawing.Printing.PrintDocument.PrintPage> в <xref:System.Drawing.Printing.PrintDocument>качестве свойства <xref:System.Drawing.Printing.PrintPageEventArgs> при обработке события для .  
  
     -или-  
  
- Вызовите <xref:System.Windows.Forms.Control.CreateGraphics%2A> метод управления или формы, чтобы <xref:System.Drawing.Graphics> получить ссылку на объект, представляющий поверхность чертежа этого элемента или формы. Используйте этот метод, если вы хотите использовать уже существующий вид или элемент управления.  
  
     -или-  
  
- Создайте <xref:System.Drawing.Graphics> объект из любого <xref:System.Drawing.Image>объекта, который наследует. Этот подход полезен, если требуется изменить уже существующее изображение.  
  
     В следующих разделах приводится подробная информация о каждом из этих процессов.  
  
## <a name="painteventargs-in-the-paint-event-handler"></a>PaintEventArgs в обработчике событий краски  
 При <xref:System.Windows.Forms.PaintEventHandler> программировании для <xref:System.Drawing.Printing.PrintDocument.PrintPage> элементов <xref:System.Drawing.Printing.PrintDocument>управления или для, графический объект <xref:System.Windows.Forms.PaintEventArgs> <xref:System.Drawing.Printing.PrintPageEventArgs>предоставляется в качестве одного из свойств или .  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a>Получение ссылки на графический объект от PaintEventArgs в событии Paint  
  
1. Объявить <xref:System.Drawing.Graphics> объект.  
  
2. Назначить переменную для <xref:System.Drawing.Graphics> обозначения объекта, <xref:System.Windows.Forms.PaintEventArgs>передаваемого как часть .  
  
3. Вставьте код, чтобы нарисовать форму или управление.  
  
     В следующем примере показано, как ссылаться на <xref:System.Drawing.Graphics> объект <xref:System.Windows.Forms.PaintEventArgs> из <xref:System.Windows.Forms.Control.Paint> события:  
  
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
  
## <a name="creategraphics-method"></a>Метод СозданияГрафика  
 Вы также можете <xref:System.Windows.Forms.Control.CreateGraphics%2A> использовать метод управления или формы для <xref:System.Drawing.Graphics> получения ссылки на объект, представляющий поверхность чертежа этого элемента или формы.  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a>Создание объекта Graphics с помощью метода CreateGraphics  
  
- Вызовите <xref:System.Windows.Forms.Control.CreateGraphics%2A> метод формы или управления, на котором вы хотите визуализировать графику.  
  
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
  
## <a name="create-from-an-image-object"></a>Создание из объекта изображения  
 Кроме того, можно создать графический объект из любого <xref:System.Drawing.Image> объекта, который вытекает из класса.  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a>Создание объекта Graphics из изображения  
  
- Вызовите <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> метод, поставляя имя переменной изображения, из <xref:System.Drawing.Graphics> которой требуется создать объект.  
  
     В следующем примере показано, как использовать <xref:System.Drawing.Bitmap> объект:  
  
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
> Вы можете <xref:System.Drawing.Graphics> создавать только объекты из неиндексированных файлов .bmp, таких как 16-разрядные, 24-разрядные и 32-разрядные файлы .bmp. Каждый пиксель неиндексированных файлов .bmp имеет цвет, в отличие от пикселей индексированных файлов .bmp, которые держат индекс к цветовой таблице.  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a>Рисование и манипулирование формами и изображениями  
 После его создания <xref:System.Drawing.Graphics> объект может использоваться для рисования линий и форм, визуализации текста или отображения и манипулирования изображениями. Основными объектами, используемыми <xref:System.Drawing.Graphics> с объектом, являются:  
  
- Класс, используемый <xref:System.Drawing.Pen> для рисования линий, изложения фигур или визуализации других геометрических представлений.  
  
- Класс <xref:System.Drawing.Brush> используется для заполнения областей графики, таких как заполненные формы, изображения или текст.  
  
- Класс <xref:System.Drawing.Font> предоставляет описание того, какие формы использовать при визуализации текста.  
  
- Структура <xref:System.Drawing.Color> представляет различные цвета для отображения.  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a>Использование созданного объекта Graphics  
  
- Работа йте с соответствующим объектом, перечисленным выше, чтобы нарисовать то, что вам нужно.  
  
     Дополнительные сведения см. в следующих разделах:  
  
    |Для визуализации|См.|  
    |---------------|---------|  
    |Линии|[Практическое руководство. Рисование линии в Windows Forms](how-to-draw-a-line-on-a-windows-form.md)|  
    |Фигуры|[Практическое руководство. Рисование линии или контурной фигуры](how-to-draw-an-outlined-shape.md)|  
    |текст|[Практическое руководство. Отрисовка текста в Windows Forms](how-to-draw-text-on-a-windows-form.md)|  
    |Изображения|[Практическое руководство. Вывод изображений с использованием GDI+](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a>См. также раздел

- [Приступая к программированию графики](getting-started-with-graphics-programming.md)
- [Объекты Graphics и Drawing в Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Прямые и кривые линии и фигуры](lines-curves-and-shapes.md)
- [Практическое руководство. Вывод изображений с использованием GDI+](how-to-render-images-with-gdi.md)
