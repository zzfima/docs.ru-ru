---
title: Практическое руководство. Отрисовка изображений с использованием GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], creating
- GDI+, rendering existing images
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
ms.openlocfilehash: da637152737510847830e885fdcd065ab92f16b3
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505757"
---
# <a name="how-to-render-images-with-gdi"></a><span data-ttu-id="e61b4-102">Практическое руководство. Отрисовка изображений с использованием GDI+</span><span class="sxs-lookup"><span data-stu-id="e61b4-102">How to: Render Images with GDI+</span></span>
<span data-ttu-id="e61b4-103">GDI + можно использовать для вывода изображений, которые существуют в виде файлов в ваших приложениях.</span><span class="sxs-lookup"><span data-stu-id="e61b4-103">You can use GDI+ to render images that exist as files in your applications.</span></span> <span data-ttu-id="e61b4-104">Это сделать, создав новый объект <xref:System.Drawing.Image> класс (такие как <xref:System.Drawing.Bitmap>), создавая <xref:System.Drawing.Graphics> объекта, который ссылается на поверхность рисования, вы хотите использовать и вызов <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="e61b4-104">You do this by creating a new object of an <xref:System.Drawing.Image> class (such as <xref:System.Drawing.Bitmap>), creating a <xref:System.Drawing.Graphics> object that refers to the drawing surface you want to use, and calling the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="e61b4-105">Изображение будет выведено на поверхность для рисования, представленную классом Graphics.</span><span class="sxs-lookup"><span data-stu-id="e61b4-105">The image will be painted onto the drawing surface represented by the graphics class.</span></span> <span data-ttu-id="e61b4-106">Можно использовать редактор изображений для создания и редактирования файлов изображений во время разработки и визуализировать их с помощью GDI + во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e61b4-106">You can use the Image Editor to create and edit image files at design time, and render them with GDI+ at run time.</span></span> <span data-ttu-id="e61b4-107">Дополнительные сведения см. в разделе [Редактор изображений для значков](/cpp/windows/image-editor-for-icons).</span><span class="sxs-lookup"><span data-stu-id="e61b4-107">For more information, see [Image Editor for Icons](/cpp/windows/image-editor-for-icons).</span></span>  
  
### <a name="to-render-an-image-with-gdi"></a><span data-ttu-id="e61b4-108">Вывод изображения с помощью GDI+</span><span class="sxs-lookup"><span data-stu-id="e61b4-108">To render an image with GDI+</span></span>  
  
1. <span data-ttu-id="e61b4-109">Создайте объект, представляющий изображение, которое необходимо отобразить.</span><span class="sxs-lookup"><span data-stu-id="e61b4-109">Create an object representing the image you want to display.</span></span> <span data-ttu-id="e61b4-110">Этот объект должен быть членом класса, который наследует от <xref:System.Drawing.Image>, такие как <xref:System.Drawing.Bitmap> или <xref:System.Drawing.Imaging.Metafile>.</span><span class="sxs-lookup"><span data-stu-id="e61b4-110">This object must be a member of a class that inherits from <xref:System.Drawing.Image>, such as <xref:System.Drawing.Bitmap> or <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="e61b4-111">Пример:</span><span class="sxs-lookup"><span data-stu-id="e61b4-111">An example is shown:</span></span>  
  
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
  
2. <span data-ttu-id="e61b4-112">Создание <xref:System.Drawing.Graphics> , представляющий поверхность рисования, вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="e61b4-112">Create a <xref:System.Drawing.Graphics> object that represents the drawing surface you want to use.</span></span> <span data-ttu-id="e61b4-113">Дополнительные сведения см. в разделе [Практическое руководство. Создание объектов Graphics для рисования](how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="e61b4-113">For more information, see [How to: Create Graphics Objects for Drawing](how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
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
  
3. <span data-ttu-id="e61b4-114">Вызовите <xref:System.Drawing.Graphics.DrawImage%2A> графического объекта для вывода изображения.</span><span class="sxs-lookup"><span data-stu-id="e61b4-114">Call the <xref:System.Drawing.Graphics.DrawImage%2A> of your graphics object to render the image.</span></span> <span data-ttu-id="e61b4-115">Необходимо указать как само выводимое изображение, так и координаты вывода.</span><span class="sxs-lookup"><span data-stu-id="e61b4-115">You must specify both the image to be drawn, and the coordinates where it is to be drawn.</span></span>  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e61b4-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e61b4-116">See also</span></span>

- [<span data-ttu-id="e61b4-117">Приступая к программированию графики</span><span class="sxs-lookup"><span data-stu-id="e61b4-117">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="e61b4-118">Практическое руководство. Создание объектов Graphics для рисования</span><span class="sxs-lookup"><span data-stu-id="e61b4-118">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="e61b4-119">Перья, линии и прямоугольники в GDI+</span><span class="sxs-lookup"><span data-stu-id="e61b4-119">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
- [<span data-ttu-id="e61b4-120">Практическое руководство. Рисование текста в форме Windows</span><span class="sxs-lookup"><span data-stu-id="e61b4-120">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)
- [<span data-ttu-id="e61b4-121">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e61b4-121">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="e61b4-122">Рисование линий и замкнутых фигур</span><span class="sxs-lookup"><span data-stu-id="e61b4-122">Drawing Lines or Closed Figures</span></span>](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)
- [<span data-ttu-id="e61b4-123">Редактор изображений для значков</span><span class="sxs-lookup"><span data-stu-id="e61b4-123">Image Editor for Icons</span></span>](/cpp/windows/image-editor-for-icons)
