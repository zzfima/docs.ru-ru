---
title: Как выполнить Вывод изображений с использованием GDI +
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], creating
- GDI+, rendering existing images
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
ms.openlocfilehash: a289aee211d5115d80e7ad0d9152b05a0eaf5487
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567815"
---
# <a name="how-to-render-images-with-gdi"></a><span data-ttu-id="909cd-102">Как выполнить Вывод изображений с использованием GDI +</span><span class="sxs-lookup"><span data-stu-id="909cd-102">How to: Render Images with GDI+</span></span>
<span data-ttu-id="909cd-103">Для вывода изображений, которые существуют в виде файлов в приложениях, можно использовать [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="909cd-103">You can use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to render images that exist as files in your applications.</span></span> <span data-ttu-id="909cd-104">Это сделать, создав новый объект <xref:System.Drawing.Image> класс (такие как <xref:System.Drawing.Bitmap>), создавая <xref:System.Drawing.Graphics> объекта, который ссылается на поверхность рисования, вы хотите использовать и вызов <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="909cd-104">You do this by creating a new object of an <xref:System.Drawing.Image> class (such as <xref:System.Drawing.Bitmap>), creating a <xref:System.Drawing.Graphics> object that refers to the drawing surface you want to use, and calling the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="909cd-105">Изображение будет выведено на поверхность для рисования, представленную классом Graphics.</span><span class="sxs-lookup"><span data-stu-id="909cd-105">The image will be painted onto the drawing surface represented by the graphics class.</span></span> <span data-ttu-id="909cd-106">Можно создавать и редактировать файлы изображений во время разработки с помощью редактора изображений и отображать их во время выполнения, используя [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="909cd-106">You can use the Image Editor to create and edit image files at design time, and render them with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] at run time.</span></span> <span data-ttu-id="909cd-107">Дополнительные сведения см. в разделе [Редактор изображений для значков](/cpp/windows/image-editor-for-icons).</span><span class="sxs-lookup"><span data-stu-id="909cd-107">For more information, see [Image Editor for Icons](/cpp/windows/image-editor-for-icons).</span></span>  
  
### <a name="to-render-an-image-with-gdi"></a><span data-ttu-id="909cd-108">Вывод изображения с помощью GDI+</span><span class="sxs-lookup"><span data-stu-id="909cd-108">To render an image with GDI+</span></span>  
  
1.  <span data-ttu-id="909cd-109">Создайте объект, представляющий изображение, которое необходимо отобразить.</span><span class="sxs-lookup"><span data-stu-id="909cd-109">Create an object representing the image you want to display.</span></span> <span data-ttu-id="909cd-110">Этот объект должен быть членом класса, который наследует от <xref:System.Drawing.Image>, такие как <xref:System.Drawing.Bitmap> или <xref:System.Drawing.Imaging.Metafile>.</span><span class="sxs-lookup"><span data-stu-id="909cd-110">This object must be a member of a class that inherits from <xref:System.Drawing.Image>, such as <xref:System.Drawing.Bitmap> or <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="909cd-111">Пример:</span><span class="sxs-lookup"><span data-stu-id="909cd-111">An example is shown:</span></span>  
  
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
  
2.  <span data-ttu-id="909cd-112">Создание <xref:System.Drawing.Graphics> , представляющий поверхность рисования, вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="909cd-112">Create a <xref:System.Drawing.Graphics> object that represents the drawing surface you want to use.</span></span> <span data-ttu-id="909cd-113">Дополнительные сведения см. в разделе [Как Создание объектов Graphics для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="909cd-113">For more information, see [How to: Create Graphics Objects for Drawing](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
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
  
3.  <span data-ttu-id="909cd-114">Вызовите <xref:System.Drawing.Graphics.DrawImage%2A> графического объекта для вывода изображения.</span><span class="sxs-lookup"><span data-stu-id="909cd-114">Call the <xref:System.Drawing.Graphics.DrawImage%2A> of your graphics object to render the image.</span></span> <span data-ttu-id="909cd-115">Необходимо указать как само выводимое изображение, так и координаты вывода.</span><span class="sxs-lookup"><span data-stu-id="909cd-115">You must specify both the image to be drawn, and the coordinates where it is to be drawn.</span></span>  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="909cd-116">См. также</span><span class="sxs-lookup"><span data-stu-id="909cd-116">See also</span></span>
- [<span data-ttu-id="909cd-117">Приступая к программированию графики</span><span class="sxs-lookup"><span data-stu-id="909cd-117">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [<span data-ttu-id="909cd-118">Практическое руководство. Создание объектов Graphics для рисования</span><span class="sxs-lookup"><span data-stu-id="909cd-118">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="909cd-119">Перья, линии и прямоугольники в GDI+</span><span class="sxs-lookup"><span data-stu-id="909cd-119">Pens, Lines, and Rectangles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
- [<span data-ttu-id="909cd-120">Практическое руководство. Рисование текста в форме Windows</span><span class="sxs-lookup"><span data-stu-id="909cd-120">How to: Draw Text on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)
- [<span data-ttu-id="909cd-121">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="909cd-121">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="909cd-122">Рисование линий и замкнутых фигур</span><span class="sxs-lookup"><span data-stu-id="909cd-122">Drawing Lines or Closed Figures</span></span>](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)
- [<span data-ttu-id="909cd-123">Редактор изображений для значков</span><span class="sxs-lookup"><span data-stu-id="909cd-123">Image Editor for Icons</span></span>](/cpp/windows/image-editor-for-icons)
