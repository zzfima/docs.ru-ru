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
ms.openlocfilehash: 3ed1fb6a9a7fc8e7ded6ae0e124ca7dcbf0f3c98
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716963"
---
# <a name="how-to-create-thumbnail-images"></a><span data-ttu-id="f413b-102">Практическое руководство. Создание эскизов изображений</span><span class="sxs-lookup"><span data-stu-id="f413b-102">How to: Create Thumbnail Images</span></span>
<span data-ttu-id="f413b-103">Эскиз — это компактная версия образа.</span><span class="sxs-lookup"><span data-stu-id="f413b-103">A thumbnail image is a small version of an image.</span></span> <span data-ttu-id="f413b-104">Можно создать изображение эскиза путем вызова <xref:System.Drawing.Image.GetThumbnailImage%2A> метод <xref:System.Drawing.Image> объекта.</span><span class="sxs-lookup"><span data-stu-id="f413b-104">You can create a thumbnail image by calling the <xref:System.Drawing.Image.GetThumbnailImage%2A> method of an <xref:System.Drawing.Image> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f413b-105">Пример</span><span class="sxs-lookup"><span data-stu-id="f413b-105">Example</span></span>  
 <span data-ttu-id="f413b-106">В следующем примере создается <xref:System.Drawing.Image> объект из JPG-файла.</span><span class="sxs-lookup"><span data-stu-id="f413b-106">The following example constructs an <xref:System.Drawing.Image> object from a JPG file.</span></span> <span data-ttu-id="f413b-107">Исходное изображение имеет 640 пикселей в ширину и высоту 479 пикселей.</span><span class="sxs-lookup"><span data-stu-id="f413b-107">The original image has a width of 640 pixels and a height of 479 pixels.</span></span> <span data-ttu-id="f413b-108">Код создает эскиз с 100 пикселей в ширину и высоту 100 пикселей.</span><span class="sxs-lookup"><span data-stu-id="f413b-108">The code creates a thumbnail image that has a width of 100 pixels and a height of 100 pixels.</span></span>  
  
 <span data-ttu-id="f413b-109">На следующем рисунке эскиз.</span><span class="sxs-lookup"><span data-stu-id="f413b-109">The following illustration shows the thumbnail image.</span></span>  
  
 <span data-ttu-id="f413b-110">![Эскиз](./media/thumbnail1.png "Thumbnail1")</span><span class="sxs-lookup"><span data-stu-id="f413b-110">![Thumbnail Image](./media/thumbnail1.png "Thumbnail1")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f413b-111">В этом примере метод обратного вызова является объявлен, но никогда не используется.</span><span class="sxs-lookup"><span data-stu-id="f413b-111">In this example, a callback method is declared, but never used.</span></span> <span data-ttu-id="f413b-112">Это поддерживается всеми версиями GDI +.</span><span class="sxs-lookup"><span data-stu-id="f413b-112">This supports all versions of GDI+.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f413b-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f413b-113">Compiling the Code</span></span>  
 <span data-ttu-id="f413b-114">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="f413b-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="f413b-115">Чтобы запустить пример, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f413b-115">To run the example, follow these steps:</span></span>  
  
1.  <span data-ttu-id="f413b-116">Создайте новое приложение Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f413b-116">Create a new Windows Forms application.</span></span>  
  
2.  <span data-ttu-id="f413b-117">В примере кода добавьте в форму.</span><span class="sxs-lookup"><span data-stu-id="f413b-117">Add the example code to the form.</span></span>  
  
3.  <span data-ttu-id="f413b-118">Создайте обработчик для формы <xref:System.Windows.Forms.Control.Paint> событий</span><span class="sxs-lookup"><span data-stu-id="f413b-118">Create a handler for the form's <xref:System.Windows.Forms.Control.Paint> event</span></span>  
  
4.  <span data-ttu-id="f413b-119">В <xref:System.Windows.Forms.Control.Paint> обработчик, вызов `GetThumbnail` метод и передать `e` для <xref:System.Windows.Forms.PaintEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="f413b-119">In the <xref:System.Windows.Forms.Control.Paint> handler, call the `GetThumbnail` method and pass `e` for <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
5.  <span data-ttu-id="f413b-120">Найдите файл изображения, который требуется создать эскиз.</span><span class="sxs-lookup"><span data-stu-id="f413b-120">Find an image file that you want to make a thumbnail of.</span></span>  
  
6.  <span data-ttu-id="f413b-121">В `GetThumbnail` метод, укажите путь и имя файла для изображения.</span><span class="sxs-lookup"><span data-stu-id="f413b-121">In the `GetThumbnail` method, specify the path and file name to your image.</span></span>  
  
7.  <span data-ttu-id="f413b-122">Нажмите клавишу F5 для запуска примера.</span><span class="sxs-lookup"><span data-stu-id="f413b-122">Press F5 to run the example.</span></span>  
  
     <span data-ttu-id="f413b-123">В форме появится эскиз 100 на 100.</span><span class="sxs-lookup"><span data-stu-id="f413b-123">A 100 by 100 thumbnail image appears on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f413b-124">См. также</span><span class="sxs-lookup"><span data-stu-id="f413b-124">See also</span></span>
- [<span data-ttu-id="f413b-125">Изображения, точечные рисунки и метафайлы</span><span class="sxs-lookup"><span data-stu-id="f413b-125">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="f413b-126">Работа с растровыми и векторными изображениями, значками и метафайлами</span><span class="sxs-lookup"><span data-stu-id="f413b-126">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
