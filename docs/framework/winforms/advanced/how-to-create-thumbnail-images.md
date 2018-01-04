---
title: "Практическое руководство. Создание эскизов изображений"
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
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b8eeb856fabd895e171c0ad8739ae6a63b5c7065
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-thumbnail-images"></a><span data-ttu-id="d4cd5-102">Практическое руководство. Создание эскизов изображений</span><span class="sxs-lookup"><span data-stu-id="d4cd5-102">How to: Create Thumbnail Images</span></span>
<span data-ttu-id="d4cd5-103">Эскиз — это уменьшенная изображения.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-103">A thumbnail image is a small version of an image.</span></span> <span data-ttu-id="d4cd5-104">Можно создать эскиз путем вызова <xref:System.Drawing.Image.GetThumbnailImage%2A> метод <xref:System.Drawing.Image> объекта.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-104">You can create a thumbnail image by calling the <xref:System.Drawing.Image.GetThumbnailImage%2A> method of an <xref:System.Drawing.Image> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4cd5-105">Пример</span><span class="sxs-lookup"><span data-stu-id="d4cd5-105">Example</span></span>  
 <span data-ttu-id="d4cd5-106">В следующем примере создается <xref:System.Drawing.Image> объекта из JPG-файла.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-106">The following example constructs an <xref:System.Drawing.Image> object from a JPG file.</span></span> <span data-ttu-id="d4cd5-107">Исходное изображение имеет ширину 640 пикселей и высотой 479 пикселей.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-107">The original image has a width of 640 pixels and a height of 479 pixels.</span></span> <span data-ttu-id="d4cd5-108">Код создает эскиз изображения, имеет ширину 100 пикселей и высотой 100 пикселей.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-108">The code creates a thumbnail image that has a width of 100 pixels and a height of 100 pixels.</span></span>  
  
 <span data-ttu-id="d4cd5-109">На следующем рисунке эскиз.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-109">The following illustration shows the thumbnail image.</span></span>  
  
 <span data-ttu-id="d4cd5-110">![Эскиз](../../../../docs/framework/winforms/advanced/media/thumbnail1.png "Thumbnail1")</span><span class="sxs-lookup"><span data-stu-id="d4cd5-110">![Thumbnail Image](../../../../docs/framework/winforms/advanced/media/thumbnail1.png "Thumbnail1")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4cd5-111">В этом примере метод обратного вызова объявлен, но никогда не используется.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-111">In this example, a callback method is declared, but never used.</span></span> <span data-ttu-id="d4cd5-112">Это поддерживается всеми версиями GDI +.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-112">This supports all versions of GDI+.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d4cd5-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="d4cd5-113">Compiling the Code</span></span>  
 <span data-ttu-id="d4cd5-114">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="d4cd5-115">Чтобы запустить пример, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-115">To run the example, follow these steps:</span></span>  
  
1.  <span data-ttu-id="d4cd5-116">Создайте новое приложение Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-116">Create a new Windows Forms application.</span></span>  
  
2.  <span data-ttu-id="d4cd5-117">Добавьте в форму в примере кода.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-117">Add the example code to the form.</span></span>  
  
3.  <span data-ttu-id="d4cd5-118">Создание обработчика для формы <xref:System.Windows.Forms.Control.Paint> событий</span><span class="sxs-lookup"><span data-stu-id="d4cd5-118">Create a handler for the form's <xref:System.Windows.Forms.Control.Paint> event</span></span>  
  
4.  <span data-ttu-id="d4cd5-119">В <xref:System.Windows.Forms.Control.Paint> обработчик, вызовите `GetThumbnail` метод и передайте `e` для <xref:System.Windows.Forms.PaintEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-119">In the <xref:System.Windows.Forms.Control.Paint> handler, call the `GetThumbnail` method and pass `e` for <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
5.  <span data-ttu-id="d4cd5-120">Найдите файл образа, который вы хотите создать эскиз.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-120">Find an image file that you want to make a thumbnail of.</span></span>  
  
6.  <span data-ttu-id="d4cd5-121">В `GetThumbnail` метода, укажите путь и имя файла для изображения.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-121">In the `GetThumbnail` method, specify the path and file name to your image.</span></span>  
  
7.  <span data-ttu-id="d4cd5-122">Нажмите клавишу F5 для запуска примера.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-122">Press F5 to run the example.</span></span>  
  
     <span data-ttu-id="d4cd5-123">В форме появится эскиз 100 на 100.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-123">A 100 by 100 thumbnail image appears on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4cd5-124">См. также</span><span class="sxs-lookup"><span data-stu-id="d4cd5-124">See Also</span></span>  
 [<span data-ttu-id="d4cd5-125">Изображения, точечные рисунки и метафайлы</span><span class="sxs-lookup"><span data-stu-id="d4cd5-125">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="d4cd5-126">Работа с растровыми и векторными изображениями, значками и метафайлами</span><span class="sxs-lookup"><span data-stu-id="d4cd5-126">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
