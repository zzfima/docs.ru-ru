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
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="c8ab9-102">Практическое руководство. Создание объектов Graphics для рисования</span><span class="sxs-lookup"><span data-stu-id="c8ab9-102">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="c8ab9-103">Прежде чем нарисовать линии и формы, визуализировать текст или отобразить и манипулировать изображениями с помощью GDI, необходимо создать <xref:System.Drawing.Graphics> объект.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-103">Before you can draw lines and shapes, render text, or display and manipulate images with GDI+, you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="c8ab9-104">Объект <xref:System.Drawing.Graphics> представляет поверхность рисунка GDI и является объектом, который используется для создания графических изображений.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-104">The <xref:System.Drawing.Graphics> object represents a GDI+ drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="c8ab9-105">В работе с графикой есть два шага:</span><span class="sxs-lookup"><span data-stu-id="c8ab9-105">There are two steps in working with graphics:</span></span>  
  
1. <span data-ttu-id="c8ab9-106">Создание <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-106">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="c8ab9-107">Использование <xref:System.Drawing.Graphics> объекта для рисования линий и форм, визуализации текста или отображения и манипулирования изображениями.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-107">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="c8ab9-108">Создание графического объекта</span><span class="sxs-lookup"><span data-stu-id="c8ab9-108">Creating a Graphics Object</span></span>  
 <span data-ttu-id="c8ab9-109">Графический объект может быть создан различными способами.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-109">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="c8ab9-110">Создание графического объекта</span><span class="sxs-lookup"><span data-stu-id="c8ab9-110">To create a graphics object</span></span>  
  
- <span data-ttu-id="c8ab9-111">Получить ссылку на графический объект <xref:System.Windows.Forms.PaintEventArgs> как <xref:System.Windows.Forms.Control.Paint> часть формы или управления.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-111">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="c8ab9-112">Обычно таким образом вы получаете ссылку на графический объект при создании кода живописи для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-112">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="c8ab9-113">Аналогичным образом, вы также можете получить графический объект <xref:System.Drawing.Printing.PrintDocument.PrintPage> в <xref:System.Drawing.Printing.PrintDocument>качестве свойства <xref:System.Drawing.Printing.PrintPageEventArgs> при обработке события для .</span><span class="sxs-lookup"><span data-stu-id="c8ab9-113">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="c8ab9-114">-или-</span><span class="sxs-lookup"><span data-stu-id="c8ab9-114">-or-</span></span>  
  
- <span data-ttu-id="c8ab9-115">Вызовите <xref:System.Windows.Forms.Control.CreateGraphics%2A> метод управления или формы, чтобы <xref:System.Drawing.Graphics> получить ссылку на объект, представляющий поверхность чертежа этого элемента или формы.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-115">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="c8ab9-116">Используйте этот метод, если вы хотите использовать уже существующий вид или элемент управления.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-116">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="c8ab9-117">-или-</span><span class="sxs-lookup"><span data-stu-id="c8ab9-117">-or-</span></span>  
  
- <span data-ttu-id="c8ab9-118">Создайте <xref:System.Drawing.Graphics> объект из любого <xref:System.Drawing.Image>объекта, который наследует.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-118">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="c8ab9-119">Этот подход полезен, если требуется изменить уже существующее изображение.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-119">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="c8ab9-120">В следующих разделах приводится подробная информация о каждом из этих процессов.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-120">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="c8ab9-121">PaintEventArgs в обработчике событий краски</span><span class="sxs-lookup"><span data-stu-id="c8ab9-121">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="c8ab9-122">При <xref:System.Windows.Forms.PaintEventHandler> программировании для <xref:System.Drawing.Printing.PrintDocument.PrintPage> элементов <xref:System.Drawing.Printing.PrintDocument>управления или для, графический объект <xref:System.Windows.Forms.PaintEventArgs> <xref:System.Drawing.Printing.PrintPageEventArgs>предоставляется в качестве одного из свойств или .</span><span class="sxs-lookup"><span data-stu-id="c8ab9-122">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="c8ab9-123">Получение ссылки на графический объект от PaintEventArgs в событии Paint</span><span class="sxs-lookup"><span data-stu-id="c8ab9-123">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1. <span data-ttu-id="c8ab9-124">Объявить <xref:System.Drawing.Graphics> объект.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-124">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="c8ab9-125">Назначить переменную для <xref:System.Drawing.Graphics> обозначения объекта, <xref:System.Windows.Forms.PaintEventArgs>передаваемого как часть .</span><span class="sxs-lookup"><span data-stu-id="c8ab9-125">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3. <span data-ttu-id="c8ab9-126">Вставьте код, чтобы нарисовать форму или управление.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-126">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="c8ab9-127">В следующем примере показано, как ссылаться на <xref:System.Drawing.Graphics> объект <xref:System.Windows.Forms.PaintEventArgs> из <xref:System.Windows.Forms.Control.Paint> события:</span><span class="sxs-lookup"><span data-stu-id="c8ab9-127">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
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
  
## <a name="creategraphics-method"></a><span data-ttu-id="c8ab9-128">Метод СозданияГрафика</span><span class="sxs-lookup"><span data-stu-id="c8ab9-128">CreateGraphics Method</span></span>  
 <span data-ttu-id="c8ab9-129">Вы также можете <xref:System.Windows.Forms.Control.CreateGraphics%2A> использовать метод управления или формы для <xref:System.Drawing.Graphics> получения ссылки на объект, представляющий поверхность чертежа этого элемента или формы.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-129">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="c8ab9-130">Создание объекта Graphics с помощью метода CreateGraphics</span><span class="sxs-lookup"><span data-stu-id="c8ab9-130">To create a Graphics object with the CreateGraphics method</span></span>  
  
- <span data-ttu-id="c8ab9-131">Вызовите <xref:System.Windows.Forms.Control.CreateGraphics%2A> метод формы или управления, на котором вы хотите визуализировать графику.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-131">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
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
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="c8ab9-132">Создание из объекта изображения</span><span class="sxs-lookup"><span data-stu-id="c8ab9-132">Create from an Image Object</span></span>  
 <span data-ttu-id="c8ab9-133">Кроме того, можно создать графический объект из любого <xref:System.Drawing.Image> объекта, который вытекает из класса.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-133">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="c8ab9-134">Создание объекта Graphics из изображения</span><span class="sxs-lookup"><span data-stu-id="c8ab9-134">To create a Graphics object from an Image</span></span>  
  
- <span data-ttu-id="c8ab9-135">Вызовите <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> метод, поставляя имя переменной изображения, из <xref:System.Drawing.Graphics> которой требуется создать объект.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-135">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="c8ab9-136">В следующем примере показано, как использовать <xref:System.Drawing.Bitmap> объект:</span><span class="sxs-lookup"><span data-stu-id="c8ab9-136">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
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
> <span data-ttu-id="c8ab9-137">Вы можете <xref:System.Drawing.Graphics> создавать только объекты из неиндексированных файлов .bmp, таких как 16-разрядные, 24-разрядные и 32-разрядные файлы .bmp.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-137">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="c8ab9-138">Каждый пиксель неиндексированных файлов .bmp имеет цвет, в отличие от пикселей индексированных файлов .bmp, которые держат индекс к цветовой таблице.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-138">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="c8ab9-139">Рисование и манипулирование формами и изображениями</span><span class="sxs-lookup"><span data-stu-id="c8ab9-139">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="c8ab9-140">После его создания <xref:System.Drawing.Graphics> объект может использоваться для рисования линий и форм, визуализации текста или отображения и манипулирования изображениями.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-140">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="c8ab9-141">Основными объектами, используемыми <xref:System.Drawing.Graphics> с объектом, являются:</span><span class="sxs-lookup"><span data-stu-id="c8ab9-141">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
- <span data-ttu-id="c8ab9-142">Класс, используемый <xref:System.Drawing.Pen> для рисования линий, изложения фигур или визуализации других геометрических представлений.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-142">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
- <span data-ttu-id="c8ab9-143">Класс <xref:System.Drawing.Brush> используется для заполнения областей графики, таких как заполненные формы, изображения или текст.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-143">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
- <span data-ttu-id="c8ab9-144">Класс <xref:System.Drawing.Font> предоставляет описание того, какие формы использовать при визуализации текста.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-144">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
- <span data-ttu-id="c8ab9-145">Структура <xref:System.Drawing.Color> представляет различные цвета для отображения.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-145">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="c8ab9-146">Использование созданного объекта Graphics</span><span class="sxs-lookup"><span data-stu-id="c8ab9-146">To use the Graphics object you have created</span></span>  
  
- <span data-ttu-id="c8ab9-147">Работа йте с соответствующим объектом, перечисленным выше, чтобы нарисовать то, что вам нужно.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-147">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="c8ab9-148">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="c8ab9-148">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="c8ab9-149">Для визуализации</span><span class="sxs-lookup"><span data-stu-id="c8ab9-149">To render</span></span>|<span data-ttu-id="c8ab9-150">См.</span><span class="sxs-lookup"><span data-stu-id="c8ab9-150">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="c8ab9-151">Линии</span><span class="sxs-lookup"><span data-stu-id="c8ab9-151">Lines</span></span>|[<span data-ttu-id="c8ab9-152">Практическое руководство. Рисование линии в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c8ab9-152">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="c8ab9-153">Фигуры</span><span class="sxs-lookup"><span data-stu-id="c8ab9-153">Shapes</span></span>|[<span data-ttu-id="c8ab9-154">Практическое руководство. Рисование линии или контурной фигуры</span><span class="sxs-lookup"><span data-stu-id="c8ab9-154">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="c8ab9-155">текст</span><span class="sxs-lookup"><span data-stu-id="c8ab9-155">Text</span></span>|[<span data-ttu-id="c8ab9-156">Практическое руководство. Отрисовка текста в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c8ab9-156">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="c8ab9-157">Изображения</span><span class="sxs-lookup"><span data-stu-id="c8ab9-157">Images</span></span>|[<span data-ttu-id="c8ab9-158">Практическое руководство. Вывод изображений с использованием GDI+</span><span class="sxs-lookup"><span data-stu-id="c8ab9-158">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="c8ab9-159">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c8ab9-159">See also</span></span>

- [<span data-ttu-id="c8ab9-160">Приступая к программированию графики</span><span class="sxs-lookup"><span data-stu-id="c8ab9-160">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="c8ab9-161">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c8ab9-161">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="c8ab9-162">Прямые и кривые линии и фигуры</span><span class="sxs-lookup"><span data-stu-id="c8ab9-162">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="c8ab9-163">Практическое руководство. Вывод изображений с использованием GDI+</span><span class="sxs-lookup"><span data-stu-id="c8ab9-163">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
