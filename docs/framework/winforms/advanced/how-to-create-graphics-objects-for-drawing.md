---
title: Как выполнить Создание объектов Graphics для рисования
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
ms.openlocfilehash: a21e049cb91ec29bcd46eb04efd78487da9a6317
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54497036"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="4d52a-102">Как выполнить Создание объектов Graphics для рисования</span><span class="sxs-lookup"><span data-stu-id="4d52a-102">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="4d52a-103">Перед тем как рисовать линии и фигуры, отображать текст или изображения и управлять ими с помощью [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], необходимо создать объект <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="4d52a-103">Before you can draw lines and shapes, render text, or display and manipulate images with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="4d52a-104"><xref:System.Drawing.Graphics> представляет поверхность для рисования [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] и является объектом, который используется для создания графических изображений.</span><span class="sxs-lookup"><span data-stu-id="4d52a-104">The <xref:System.Drawing.Graphics> object represents a [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="4d52a-105">Работа с графикой состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="4d52a-105">There are two steps in working with graphics:</span></span>  
  
1.  <span data-ttu-id="4d52a-106">Создание объекта <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="4d52a-106">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2.  <span data-ttu-id="4d52a-107">Использование объекта <xref:System.Drawing.Graphics> для рисования линий и фигур, отображения текста или изображений и управления ими.</span><span class="sxs-lookup"><span data-stu-id="4d52a-107">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="4d52a-108">Создание объектов Graphics</span><span class="sxs-lookup"><span data-stu-id="4d52a-108">Creating a Graphics Object</span></span>  
 <span data-ttu-id="4d52a-109">Объекты Graphics могут создаваться различными способами.</span><span class="sxs-lookup"><span data-stu-id="4d52a-109">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="4d52a-110">Чтобы создать объект Graphics</span><span class="sxs-lookup"><span data-stu-id="4d52a-110">To create a graphics object</span></span>  
  
-   <span data-ttu-id="4d52a-111">Получите ссылку на объект Graphics как часть <xref:System.Windows.Forms.PaintEventArgs> в событии <xref:System.Windows.Forms.Control.Paint>  формы или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4d52a-111">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="4d52a-112">Это обычный способ получения ссылки на объект Graphics при создании кода рисования для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4d52a-112">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="4d52a-113">Аналогичным образом можно получить объект Graphics как свойство <xref:System.Drawing.Printing.PrintPageEventArgs> при обработке события <xref:System.Drawing.Printing.PrintDocument.PrintPage> для <xref:System.Drawing.Printing.PrintDocument>.</span><span class="sxs-lookup"><span data-stu-id="4d52a-113">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="4d52a-114">- или -</span><span class="sxs-lookup"><span data-stu-id="4d52a-114">-or-</span></span>  
  
-   <span data-ttu-id="4d52a-115">Вызовите метод <xref:System.Windows.Forms.Control.CreateGraphics%2A> элемента управления или формы, чтобы получить ссылку на <xref:System.Drawing.Graphics>, представляющий поверхность рисования объекта формы или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4d52a-115">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="4d52a-116">Используйте этот метод, чтобы рисовать на уже существующей форме или элементе управления.</span><span class="sxs-lookup"><span data-stu-id="4d52a-116">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="4d52a-117">- или -</span><span class="sxs-lookup"><span data-stu-id="4d52a-117">-or-</span></span>  
  
-   <span data-ttu-id="4d52a-118">Создайте объект <xref:System.Drawing.Graphics> из любого объекта, который наследует от <xref:System.Drawing.Image>.</span><span class="sxs-lookup"><span data-stu-id="4d52a-118">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="4d52a-119">Этот подход полезен в тех случаях, когда нужно изменить уже существующий образ.</span><span class="sxs-lookup"><span data-stu-id="4d52a-119">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="4d52a-120">В следующих разделах приводятся сведения о каждом из этих процессов.</span><span class="sxs-lookup"><span data-stu-id="4d52a-120">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="4d52a-121">PaintEventArgs в обработчике события рисования</span><span class="sxs-lookup"><span data-stu-id="4d52a-121">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="4d52a-122">При программировании <xref:System.Windows.Forms.PaintEventHandler> для элементов управления или <xref:System.Drawing.Printing.PrintDocument.PrintPage> для <xref:System.Drawing.Printing.PrintDocument> объект Graphics предоставляется как одно из свойств объекта <xref:System.Windows.Forms.PaintEventArgs> или <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="4d52a-122">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="4d52a-123">Для получения ссылки на объект Graphics из PaintEventArgs в событии рисования</span><span class="sxs-lookup"><span data-stu-id="4d52a-123">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1.  <span data-ttu-id="4d52a-124">Объявите объект <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="4d52a-124">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2.  <span data-ttu-id="4d52a-125">Присвойте переменной ссылку на объект <xref:System.Drawing.Graphics>, передаваемый как часть <xref:System.Windows.Forms.PaintEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="4d52a-125">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3.  <span data-ttu-id="4d52a-126">Вставьте код для рисования формы или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4d52a-126">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="4d52a-127">В следующем примере показано, как ссылаться на объект <xref:System.Drawing.Graphics> из <xref:System.Windows.Forms.PaintEventArgs> в событии <xref:System.Windows.Forms.Control.Paint>:</span><span class="sxs-lookup"><span data-stu-id="4d52a-127">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
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
  
## <a name="creategraphics-method"></a><span data-ttu-id="4d52a-128">Метод CreateGraphics</span><span class="sxs-lookup"><span data-stu-id="4d52a-128">CreateGraphics Method</span></span>  
 <span data-ttu-id="4d52a-129">Можно также использовать метод <xref:System.Windows.Forms.Control.CreateGraphics%2A> элемента управления или формы, чтобы получить ссылку на объект <xref:System.Drawing.Graphics>, представляющий поверхность рисования формы или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4d52a-129">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="4d52a-130">Чтобы создать объект Graphics с помощью метода CreateGraphics</span><span class="sxs-lookup"><span data-stu-id="4d52a-130">To create a Graphics object with the CreateGraphics method</span></span>  
  
-   <span data-ttu-id="4d52a-131">Вызовите метод <xref:System.Windows.Forms.Control.CreateGraphics%2A> формы или элемента управления, на которых необходимо отрисовывать графику.</span><span class="sxs-lookup"><span data-stu-id="4d52a-131">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
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
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="4d52a-132">Создание из объекта Image</span><span class="sxs-lookup"><span data-stu-id="4d52a-132">Create from an Image Object</span></span>  
 <span data-ttu-id="4d52a-133">Кроме того, можно создать объект Graphics из любого объекта, производного от класса <xref:System.Drawing.Image>.</span><span class="sxs-lookup"><span data-stu-id="4d52a-133">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="4d52a-134">Чтобы создать объект Graphics из изображения</span><span class="sxs-lookup"><span data-stu-id="4d52a-134">To create a Graphics object from an Image</span></span>  
  
-   <span data-ttu-id="4d52a-135">Вызовите метод <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType>, указав имя переменной типа Image, из которой требуется создать объект <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="4d52a-135">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="4d52a-136">В следующем примере показано, как использовать объект <xref:System.Drawing.Bitmap>:</span><span class="sxs-lookup"><span data-stu-id="4d52a-136">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
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
>  <span data-ttu-id="4d52a-137">Вы можете создавать объекты <xref:System.Drawing.Graphics> только из неиндексированных BMP-файлов, например, 16, 24 и 32-разрядных BMP-файлов.</span><span class="sxs-lookup"><span data-stu-id="4d52a-137">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="4d52a-138">Каждый пиксель неиндексированного BMP-файла содержит сведения о цвете, в отличие от пикселей индексированного BMP-файла, содержащих указатели на таблицу цветов.</span><span class="sxs-lookup"><span data-stu-id="4d52a-138">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="4d52a-139">Рисование и изменение фигур и изображений</span><span class="sxs-lookup"><span data-stu-id="4d52a-139">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="4d52a-140">После создания объект <xref:System.Drawing.Graphics> можно использовать для рисования линий и фигур, отрисовки текста, а также показа и изменения изображений.</span><span class="sxs-lookup"><span data-stu-id="4d52a-140">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="4d52a-141">Основные объекты, которые используются с объектами <xref:System.Drawing.Graphics>:</span><span class="sxs-lookup"><span data-stu-id="4d52a-141">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
-   <span data-ttu-id="4d52a-142">Класс <xref:System.Drawing.Pen>, используемый для рисования линий, контуров и отрисовки других геометрических объектов.</span><span class="sxs-lookup"><span data-stu-id="4d52a-142">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
-   <span data-ttu-id="4d52a-143">Класс <xref:System.Drawing.Brush>, используемый для заливки графических областей, например фигур, изображений или текста.</span><span class="sxs-lookup"><span data-stu-id="4d52a-143">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
-   <span data-ttu-id="4d52a-144">Класс <xref:System.Drawing.Font>, содержащий описание фигур, которые должны использоваться при отрисовке текста.</span><span class="sxs-lookup"><span data-stu-id="4d52a-144">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
-   <span data-ttu-id="4d52a-145">Структура <xref:System.Drawing.Color>, представляющая различные цвета для отображения.</span><span class="sxs-lookup"><span data-stu-id="4d52a-145">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="4d52a-146">Чтобы использовать объект Graphics, который вы создали</span><span class="sxs-lookup"><span data-stu-id="4d52a-146">To use the Graphics object you have created</span></span>  
  
-   <span data-ttu-id="4d52a-147">Используйте любой из вышеперечисленных объектов для рисования того, что вам нужно.</span><span class="sxs-lookup"><span data-stu-id="4d52a-147">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="4d52a-148">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="4d52a-148">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="4d52a-149">Для отрисовки</span><span class="sxs-lookup"><span data-stu-id="4d52a-149">To render</span></span>|<span data-ttu-id="4d52a-150">См.</span><span class="sxs-lookup"><span data-stu-id="4d52a-150">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="4d52a-151">Прямых линий</span><span class="sxs-lookup"><span data-stu-id="4d52a-151">Lines</span></span>|[<span data-ttu-id="4d52a-152">Практическое руководство. Нарисовать линию в форме Windows</span><span class="sxs-lookup"><span data-stu-id="4d52a-152">How to: Draw a Line on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="4d52a-153">Фигур</span><span class="sxs-lookup"><span data-stu-id="4d52a-153">Shapes</span></span>|[<span data-ttu-id="4d52a-154">Практическое руководство. Рисование контурной фигуры</span><span class="sxs-lookup"><span data-stu-id="4d52a-154">How to: Draw an Outlined Shape</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="4d52a-155">Текста</span><span class="sxs-lookup"><span data-stu-id="4d52a-155">Text</span></span>|[<span data-ttu-id="4d52a-156">Практическое руководство. Рисование текста в форме Windows</span><span class="sxs-lookup"><span data-stu-id="4d52a-156">How to: Draw Text on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="4d52a-157">Изображений</span><span class="sxs-lookup"><span data-stu-id="4d52a-157">Images</span></span>|[<span data-ttu-id="4d52a-158">Практическое руководство. Вывод изображений с использованием GDI +</span><span class="sxs-lookup"><span data-stu-id="4d52a-158">How to: Render Images with GDI+</span></span>](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="4d52a-159">См. также</span><span class="sxs-lookup"><span data-stu-id="4d52a-159">See also</span></span>
- [<span data-ttu-id="4d52a-160">Приступая к программированию графики</span><span class="sxs-lookup"><span data-stu-id="4d52a-160">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [<span data-ttu-id="4d52a-161">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4d52a-161">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="4d52a-162">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="4d52a-162">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)
- [<span data-ttu-id="4d52a-163">Практическое руководство. Вывод изображений с использованием GDI +</span><span class="sxs-lookup"><span data-stu-id="4d52a-163">How to: Render Images with GDI+</span></span>](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)
