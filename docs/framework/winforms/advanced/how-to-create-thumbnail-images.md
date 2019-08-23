---
title: Практическое руководство. Создание эскизов изображений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
ms.openlocfilehash: 786a92d99f5e7a0c27f502efa9a5fe617ac4d4d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923760"
---
# <a name="how-to-create-thumbnail-images"></a><span data-ttu-id="efc56-102">Практическое руководство. Создание эскизов изображений</span><span class="sxs-lookup"><span data-stu-id="efc56-102">How to: Create Thumbnail Images</span></span>
<span data-ttu-id="efc56-103">Эскиз изображения — это небольшая версия изображения.</span><span class="sxs-lookup"><span data-stu-id="efc56-103">A thumbnail image is a small version of an image.</span></span> <span data-ttu-id="efc56-104">Можно создать эскиз изображения, вызвав <xref:System.Drawing.Image.GetThumbnailImage%2A> метод <xref:System.Drawing.Image> объекта.</span><span class="sxs-lookup"><span data-stu-id="efc56-104">You can create a thumbnail image by calling the <xref:System.Drawing.Image.GetThumbnailImage%2A> method of an <xref:System.Drawing.Image> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efc56-105">Пример</span><span class="sxs-lookup"><span data-stu-id="efc56-105">Example</span></span>  
 <span data-ttu-id="efc56-106">В следующем примере создается <xref:System.Drawing.Image> объект из JPG-файла.</span><span class="sxs-lookup"><span data-stu-id="efc56-106">The following example constructs an <xref:System.Drawing.Image> object from a JPG file.</span></span> <span data-ttu-id="efc56-107">Исходное изображение имеет ширину 640 пикселей и высоту 479 пикселей.</span><span class="sxs-lookup"><span data-stu-id="efc56-107">The original image has a width of 640 pixels and a height of 479 pixels.</span></span> <span data-ttu-id="efc56-108">Код создает эскиз эскиза с шириной 100 пикселей и высотой 100 пикселей.</span><span class="sxs-lookup"><span data-stu-id="efc56-108">The code creates a thumbnail image that has a width of 100 pixels and a height of 100 pixels.</span></span>  
  
 <span data-ttu-id="efc56-109">На следующем рисунке показан эскиз изображения:</span><span class="sxs-lookup"><span data-stu-id="efc56-109">The following illustration shows the thumbnail image:</span></span>  
  
 ![Снимок экрана, на котором показан эскиз выходных данных.](./media/how-to-create-thumbnail-images/construct-thumbnail-image.png)  
  
> [!NOTE]
> <span data-ttu-id="efc56-111">В этом примере метод обратного вызова объявляется, но не используется.</span><span class="sxs-lookup"><span data-stu-id="efc56-111">In this example, a callback method is declared, but never used.</span></span> <span data-ttu-id="efc56-112">Поддерживает все версии GDI+.</span><span class="sxs-lookup"><span data-stu-id="efc56-112">This supports all versions of GDI+.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="efc56-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="efc56-113">Compiling the Code</span></span>  
 <span data-ttu-id="efc56-114">Предыдущий пример предназначен для использования с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, что <xref:System.Windows.Forms.Control.Paint> является параметром обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="efc56-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="efc56-115">Чтобы запустить пример, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="efc56-115">To run the example, follow these steps:</span></span>  
  
1. <span data-ttu-id="efc56-116">Создайте новое приложение Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="efc56-116">Create a new Windows Forms application.</span></span>  
  
2. <span data-ttu-id="efc56-117">Добавьте пример кода в форму.</span><span class="sxs-lookup"><span data-stu-id="efc56-117">Add the example code to the form.</span></span>  
  
3. <span data-ttu-id="efc56-118">Создание обработчика для <xref:System.Windows.Forms.Control.Paint> события формы</span><span class="sxs-lookup"><span data-stu-id="efc56-118">Create a handler for the form's <xref:System.Windows.Forms.Control.Paint> event</span></span>  
  
4. <span data-ttu-id="efc56-119">В обработчике `GetThumbnail` вызовите метод и передайте `e` для <xref:System.Windows.Forms.PaintEventArgs>. <xref:System.Windows.Forms.Control.Paint></span><span class="sxs-lookup"><span data-stu-id="efc56-119">In the <xref:System.Windows.Forms.Control.Paint> handler, call the `GetThumbnail` method and pass `e` for <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
5. <span data-ttu-id="efc56-120">Найдите файл изображения, эскиз которого нужно создать.</span><span class="sxs-lookup"><span data-stu-id="efc56-120">Find an image file that you want to make a thumbnail of.</span></span>  
  
6. <span data-ttu-id="efc56-121">`GetThumbnail` В методе укажите путь и имя файла для образа.</span><span class="sxs-lookup"><span data-stu-id="efc56-121">In the `GetThumbnail` method, specify the path and file name to your image.</span></span>  
  
7. <span data-ttu-id="efc56-122">Нажмите клавишу F5, чтобы запустить пример.</span><span class="sxs-lookup"><span data-stu-id="efc56-122">Press F5 to run the example.</span></span>  
  
     <span data-ttu-id="efc56-123">На форме появится эскиз с 100 по 100.</span><span class="sxs-lookup"><span data-stu-id="efc56-123">A 100 by 100 thumbnail image appears on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efc56-124">См. также</span><span class="sxs-lookup"><span data-stu-id="efc56-124">See also</span></span>

- [<span data-ttu-id="efc56-125">Изображения, точечные рисунки и метафайлы</span><span class="sxs-lookup"><span data-stu-id="efc56-125">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="efc56-126">Работа с растровыми и векторными изображениями, значками и метафайлами</span><span class="sxs-lookup"><span data-stu-id="efc56-126">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
