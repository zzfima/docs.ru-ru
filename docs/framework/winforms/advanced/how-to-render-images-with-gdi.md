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
ms.openlocfilehash: e038da545bb3f56cc757710bcaa93aa2c86bfa67
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342554"
---
# <a name="how-to-render-images-with-gdi"></a><span data-ttu-id="409ac-102">Практическое руководство. Отрисовка изображений с использованием GDI+</span><span class="sxs-lookup"><span data-stu-id="409ac-102">How to: Render Images with GDI+</span></span>
<span data-ttu-id="409ac-103">Для вывода изображений, которые существуют в виде файлов в приложениях, можно использовать [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="409ac-103">You can use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to render images that exist as files in your applications.</span></span> <span data-ttu-id="409ac-104">Это сделать, создав новый объект <xref:System.Drawing.Image> класс (такие как <xref:System.Drawing.Bitmap>), создавая <xref:System.Drawing.Graphics> объекта, который ссылается на поверхность рисования, вы хотите использовать и вызов <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="409ac-104">You do this by creating a new object of an <xref:System.Drawing.Image> class (such as <xref:System.Drawing.Bitmap>), creating a <xref:System.Drawing.Graphics> object that refers to the drawing surface you want to use, and calling the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="409ac-105">Изображение будет выведено на поверхность для рисования, представленную классом Graphics.</span><span class="sxs-lookup"><span data-stu-id="409ac-105">The image will be painted onto the drawing surface represented by the graphics class.</span></span> <span data-ttu-id="409ac-106">Можно создавать и редактировать файлы изображений во время разработки с помощью редактора изображений и отображать их во время выполнения, используя [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="409ac-106">You can use the Image Editor to create and edit image files at design time, and render them with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] at run time.</span></span> <span data-ttu-id="409ac-107">Дополнительные сведения см. в разделе [Редактор изображений для значков](/cpp/windows/image-editor-for-icons).</span><span class="sxs-lookup"><span data-stu-id="409ac-107">For more information, see [Image Editor for Icons](/cpp/windows/image-editor-for-icons).</span></span>  
  
### <a name="to-render-an-image-with-gdi"></a><span data-ttu-id="409ac-108">Вывод изображения с помощью GDI+</span><span class="sxs-lookup"><span data-stu-id="409ac-108">To render an image with GDI+</span></span>  
  
1. <span data-ttu-id="409ac-109">Создайте объект, представляющий изображение, которое необходимо отобразить.</span><span class="sxs-lookup"><span data-stu-id="409ac-109">Create an object representing the image you want to display.</span></span> <span data-ttu-id="409ac-110">Этот объект должен быть членом класса, который наследует от <xref:System.Drawing.Image>, такие как <xref:System.Drawing.Bitmap> или <xref:System.Drawing.Imaging.Metafile>.</span><span class="sxs-lookup"><span data-stu-id="409ac-110">This object must be a member of a class that inherits from <xref:System.Drawing.Image>, such as <xref:System.Drawing.Bitmap> or <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="409ac-111">Пример:</span><span class="sxs-lookup"><span data-stu-id="409ac-111">An example is shown:</span></span>  
  
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
  
2. <span data-ttu-id="409ac-112">Создание <xref:System.Drawing.Graphics> , представляющий поверхность рисования, вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="409ac-112">Create a <xref:System.Drawing.Graphics> object that represents the drawing surface you want to use.</span></span> <span data-ttu-id="409ac-113">Дополнительные сведения см. в разделе [Как Создание объектов Graphics для рисования](how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="409ac-113">For more information, see [How to: Create Graphics Objects for Drawing](how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
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
  
3. <span data-ttu-id="409ac-114">Вызовите <xref:System.Drawing.Graphics.DrawImage%2A> графического объекта для вывода изображения.</span><span class="sxs-lookup"><span data-stu-id="409ac-114">Call the <xref:System.Drawing.Graphics.DrawImage%2A> of your graphics object to render the image.</span></span> <span data-ttu-id="409ac-115">Необходимо указать как само выводимое изображение, так и координаты вывода.</span><span class="sxs-lookup"><span data-stu-id="409ac-115">You must specify both the image to be drawn, and the coordinates where it is to be drawn.</span></span>  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="409ac-116">См. также</span><span class="sxs-lookup"><span data-stu-id="409ac-116">See also</span></span>

- [<span data-ttu-id="409ac-117">Приступая к программированию графики</span><span class="sxs-lookup"><span data-stu-id="409ac-117">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="409ac-118">Практическое руководство. Создание объектов Graphics для рисования</span><span class="sxs-lookup"><span data-stu-id="409ac-118">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="409ac-119">Перья, линии и прямоугольники в GDI+</span><span class="sxs-lookup"><span data-stu-id="409ac-119">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
- [<span data-ttu-id="409ac-120">Практическое руководство. Рисование текста в форме Windows</span><span class="sxs-lookup"><span data-stu-id="409ac-120">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)
- [<span data-ttu-id="409ac-121">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="409ac-121">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="409ac-122">Рисование линий и замкнутых фигур</span><span class="sxs-lookup"><span data-stu-id="409ac-122">Drawing Lines or Closed Figures</span></span>](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)
- [<span data-ttu-id="409ac-123">Редактор изображений для значков</span><span class="sxs-lookup"><span data-stu-id="409ac-123">Image Editor for Icons</span></span>](/cpp/windows/image-editor-for-icons)
