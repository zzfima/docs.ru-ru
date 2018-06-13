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
ms.openlocfilehash: 3c25ddcfb3a566055afd5e233c2a69b3b7a8c66e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526492"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="b96be-102">Практическое руководство. Создание объектов Graphics для рисования</span><span class="sxs-lookup"><span data-stu-id="b96be-102">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="b96be-103">Перед тем как выводить линий и фигур, отображения текста или отображения и управлять ими с [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], необходимо создать <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="b96be-103">Before you can draw lines and shapes, render text, or display and manipulate images with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="b96be-104"><xref:System.Drawing.Graphics> Представляет [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] поверхности для рисования и является объектом, который используется для создания графических изображений.</span><span class="sxs-lookup"><span data-stu-id="b96be-104">The <xref:System.Drawing.Graphics> object represents a [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="b96be-105">При работе с графикой существует два действия:</span><span class="sxs-lookup"><span data-stu-id="b96be-105">There are two steps in working with graphics:</span></span>  
  
1.  <span data-ttu-id="b96be-106">Создание <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="b96be-106">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2.  <span data-ttu-id="b96be-107">С помощью <xref:System.Drawing.Graphics> объект для рисования линий и фигур, отображения текста или отображения и управления ими.</span><span class="sxs-lookup"><span data-stu-id="b96be-107">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="b96be-108">Создание графических объектов</span><span class="sxs-lookup"><span data-stu-id="b96be-108">Creating a Graphics Object</span></span>  
 <span data-ttu-id="b96be-109">Графические объекты могут создаваться различными способами.</span><span class="sxs-lookup"><span data-stu-id="b96be-109">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="b96be-110">Чтобы создать объект графики</span><span class="sxs-lookup"><span data-stu-id="b96be-110">To create a graphics object</span></span>  
  
-   <span data-ttu-id="b96be-111">Получить ссылку на объект graphics как часть <xref:System.Windows.Forms.PaintEventArgs> в <xref:System.Windows.Forms.Control.Paint> событий формы или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b96be-111">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="b96be-112">Это обычный способ получения ссылки на графический объект при создании кода рисования для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b96be-112">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="b96be-113">Аналогичным образом можно получить графический объект как свойство <xref:System.Drawing.Printing.PrintPageEventArgs> при обработке <xref:System.Drawing.Printing.PrintDocument.PrintPage> событий для <xref:System.Drawing.Printing.PrintDocument>.</span><span class="sxs-lookup"><span data-stu-id="b96be-113">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="b96be-114">- или -</span><span class="sxs-lookup"><span data-stu-id="b96be-114">-or-</span></span>  
  
-   <span data-ttu-id="b96be-115">Вызовите <xref:System.Windows.Forms.Control.CreateGraphics%2A> метод элемента управления или формы, чтобы получить ссылку на <xref:System.Drawing.Graphics> , представляющий поверхность рисования объекта формы или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b96be-115">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="b96be-116">Используйте этот метод, чтобы рисовать на формы или элемента управления, который уже существует.</span><span class="sxs-lookup"><span data-stu-id="b96be-116">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="b96be-117">- или -</span><span class="sxs-lookup"><span data-stu-id="b96be-117">-or-</span></span>  
  
-   <span data-ttu-id="b96be-118">Создание <xref:System.Drawing.Graphics> объект из любого объекта, который наследует от <xref:System.Drawing.Image>.</span><span class="sxs-lookup"><span data-stu-id="b96be-118">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="b96be-119">Этот подход полезен, когда требуется изменить существующее изображение.</span><span class="sxs-lookup"><span data-stu-id="b96be-119">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="b96be-120">В следующих разделах приводятся сведения о каждой из этих процессов.</span><span class="sxs-lookup"><span data-stu-id="b96be-120">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="b96be-121">PaintEventArgs в обработчике событий рисования</span><span class="sxs-lookup"><span data-stu-id="b96be-121">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="b96be-122">При программировании <xref:System.Windows.Forms.PaintEventHandler> для элементов управления или <xref:System.Drawing.Printing.PrintDocument.PrintPage> для <xref:System.Drawing.Printing.PrintDocument>, графический объект предоставляется как одно из свойств объекта <xref:System.Windows.Forms.PaintEventArgs> или <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="b96be-122">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="b96be-123">Для получения ссылки на графические объекты из PaintEventArgs в событие рисования</span><span class="sxs-lookup"><span data-stu-id="b96be-123">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1.  <span data-ttu-id="b96be-124">Объявите <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="b96be-124">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2.  <span data-ttu-id="b96be-125">Назначьте переменной для ссылки на <xref:System.Drawing.Graphics> объект, передаваемый как часть <xref:System.Windows.Forms.PaintEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="b96be-125">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3.  <span data-ttu-id="b96be-126">Вставьте код для рисования формы или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b96be-126">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="b96be-127">В следующем примере показано, как ссылаться на <xref:System.Drawing.Graphics> объекта из <xref:System.Windows.Forms.PaintEventArgs> в <xref:System.Windows.Forms.Control.Paint> событий:</span><span class="sxs-lookup"><span data-stu-id="b96be-127">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
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
  
## <a name="creategraphics-method"></a><span data-ttu-id="b96be-128">Метод CreateGraphics</span><span class="sxs-lookup"><span data-stu-id="b96be-128">CreateGraphics Method</span></span>  
 <span data-ttu-id="b96be-129">Можно также использовать <xref:System.Windows.Forms.Control.CreateGraphics%2A> метод элемента управления или формы, чтобы получить ссылку на <xref:System.Drawing.Graphics> , представляющий поверхность рисования объекта формы или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b96be-129">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="b96be-130">Чтобы создать объект графики с метод CreateGraphics</span><span class="sxs-lookup"><span data-stu-id="b96be-130">To create a Graphics object with the CreateGraphics method</span></span>  
  
-   <span data-ttu-id="b96be-131">Вызовите <xref:System.Windows.Forms.Control.CreateGraphics%2A> метод формы или элемента управления, по которому необходимо для отрисовки графики.</span><span class="sxs-lookup"><span data-stu-id="b96be-131">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
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
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="b96be-132">Создание из объекта Image</span><span class="sxs-lookup"><span data-stu-id="b96be-132">Create from an Image Object</span></span>  
 <span data-ttu-id="b96be-133">Кроме того, можно создать объект графики из любого объекта, производного от <xref:System.Drawing.Image> класса.</span><span class="sxs-lookup"><span data-stu-id="b96be-133">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="b96be-134">Чтобы создать объект графики из изображения</span><span class="sxs-lookup"><span data-stu-id="b96be-134">To create a Graphics object from an Image</span></span>  
  
-   <span data-ttu-id="b96be-135">Вызовите <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> метод, указав имя переменной образа, из которого требуется создать <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="b96be-135">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="b96be-136">В следующем примере показано, как использовать <xref:System.Drawing.Bitmap> объекта:</span><span class="sxs-lookup"><span data-stu-id="b96be-136">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
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
>  <span data-ttu-id="b96be-137">Можно создать только <xref:System.Drawing.Graphics> объекты из неиндексированных BMP-файлов, например, 16, 24 и 32-разрядных BMP-файлы.</span><span class="sxs-lookup"><span data-stu-id="b96be-137">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="b96be-138">Каждая точка неиндексированного BMP-файла содержит сведения о цвете, в отличие от точек индексированного BMP-файлы, которые содержат указатели на таблицу цветов.</span><span class="sxs-lookup"><span data-stu-id="b96be-138">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
-  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="b96be-139">Рисование и управления ими фигуры и изображения</span><span class="sxs-lookup"><span data-stu-id="b96be-139">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="b96be-140">После его создания, <xref:System.Drawing.Graphics> объект может использоваться для рисования линий и фигур, отображения текста или отображения и управления ими.</span><span class="sxs-lookup"><span data-stu-id="b96be-140">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="b96be-141">Объекты principal, которые используются с <xref:System.Drawing.Graphics> объекта:</span><span class="sxs-lookup"><span data-stu-id="b96be-141">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
-   <span data-ttu-id="b96be-142"><xref:System.Drawing.Pen> Класс, используемый для рисования линий, контуров и отрисовки других геометрических объектов.</span><span class="sxs-lookup"><span data-stu-id="b96be-142">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
-   <span data-ttu-id="b96be-143"><xref:System.Drawing.Brush> Класс, используемый для заливки областей, например фигур, изображений или текста.</span><span class="sxs-lookup"><span data-stu-id="b96be-143">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
-   <span data-ttu-id="b96be-144"><xref:System.Drawing.Font> Класса — содержит описание фигур, которые должны использоваться при отображении текста.</span><span class="sxs-lookup"><span data-stu-id="b96be-144">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
-   <span data-ttu-id="b96be-145"><xref:System.Drawing.Color> Структуры — содержит различные цвета для отображения.</span><span class="sxs-lookup"><span data-stu-id="b96be-145">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="b96be-146">Чтобы использовать графический объект, который вы создали</span><span class="sxs-lookup"><span data-stu-id="b96be-146">To use the Graphics object you have created</span></span>  
  
-   <span data-ttu-id="b96be-147">Работа с соответствующего объекта, перечисленные выше для рисования, что нужно.</span><span class="sxs-lookup"><span data-stu-id="b96be-147">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="b96be-148">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="b96be-148">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="b96be-149">Для подготовки к просмотру</span><span class="sxs-lookup"><span data-stu-id="b96be-149">To render</span></span>|<span data-ttu-id="b96be-150">См.</span><span class="sxs-lookup"><span data-stu-id="b96be-150">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="b96be-151">Прямые линии</span><span class="sxs-lookup"><span data-stu-id="b96be-151">Lines</span></span>|[<span data-ttu-id="b96be-152">Практическое руководство. Рисование линии в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b96be-152">How to: Draw a Line on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="b96be-153">Фигуры</span><span class="sxs-lookup"><span data-stu-id="b96be-153">Shapes</span></span>|[<span data-ttu-id="b96be-154">Практическое руководство. Рисование контурной фигуры</span><span class="sxs-lookup"><span data-stu-id="b96be-154">How to: Draw an Outlined Shape</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="b96be-155">Text</span><span class="sxs-lookup"><span data-stu-id="b96be-155">Text</span></span>|[<span data-ttu-id="b96be-156">Практическое руководство. Рисование текста в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b96be-156">How to: Draw Text on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="b96be-157">Изображения</span><span class="sxs-lookup"><span data-stu-id="b96be-157">Images</span></span>|[<span data-ttu-id="b96be-158">Практическое руководство. Прорисовка изображений с использованием GDI+</span><span class="sxs-lookup"><span data-stu-id="b96be-158">How to: Render Images with GDI+</span></span>](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="b96be-159">См. также</span><span class="sxs-lookup"><span data-stu-id="b96be-159">See Also</span></span>  
 [<span data-ttu-id="b96be-160">Приступая к программированию графики</span><span class="sxs-lookup"><span data-stu-id="b96be-160">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="b96be-161">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b96be-161">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="b96be-162">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="b96be-162">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="b96be-163">Практическое руководство. Прорисовка изображений с использованием GDI+</span><span class="sxs-lookup"><span data-stu-id="b96be-163">How to: Render Images with GDI+</span></span>](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)
