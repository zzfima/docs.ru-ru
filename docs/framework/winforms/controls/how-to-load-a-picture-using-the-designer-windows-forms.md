---
title: Практическое руководство. Загрузка изображения с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 12b90d561a18fcffaafb9c45b7fa6be6dd060215
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736327"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="308ad-102">Практическое руководство. Загрузка изображения с помощью конструктора (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="308ad-102">How to: Load a Picture Using the Designer (Windows Forms)</span></span>

<span data-ttu-id="308ad-103">С помощью элемента управления Windows Forms <xref:System.Windows.Forms.PictureBox> можно загружать и отображать изображение в форме во время разработки, присвоив свойству <xref:System.Windows.Forms.PictureBox.Image%2A> допустимое изображение.</span><span class="sxs-lookup"><span data-stu-id="308ad-103">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="308ad-104">В следующей таблице приведены допустимые типы файлов.</span><span class="sxs-lookup"><span data-stu-id="308ad-104">The following table shows the acceptable file types.</span></span>

|<span data-ttu-id="308ad-105">Тип</span><span class="sxs-lookup"><span data-stu-id="308ad-105">Type</span></span>|<span data-ttu-id="308ad-106">Расширение имени файла</span><span class="sxs-lookup"><span data-stu-id="308ad-106">File name extension</span></span>|
|---|---|
|<span data-ttu-id="308ad-107">Bitmap</span><span class="sxs-lookup"><span data-stu-id="308ad-107">Bitmap</span></span>|<span data-ttu-id="308ad-108">BMP</span><span class="sxs-lookup"><span data-stu-id="308ad-108">.bmp</span></span>|
|<span data-ttu-id="308ad-109">Значок</span><span class="sxs-lookup"><span data-stu-id="308ad-109">Icon</span></span>|<span data-ttu-id="308ad-110">ICO</span><span class="sxs-lookup"><span data-stu-id="308ad-110">.ico</span></span>|
|<span data-ttu-id="308ad-111">GIF</span><span class="sxs-lookup"><span data-stu-id="308ad-111">GIF</span></span>|<span data-ttu-id="308ad-112">GIF</span><span class="sxs-lookup"><span data-stu-id="308ad-112">.gif</span></span>|
|<span data-ttu-id="308ad-113">Метафайл</span><span class="sxs-lookup"><span data-stu-id="308ad-113">Metafile</span></span>|<span data-ttu-id="308ad-114">. WMF</span><span class="sxs-lookup"><span data-stu-id="308ad-114">.wmf</span></span>|
|<span data-ttu-id="308ad-115">JPEG</span><span class="sxs-lookup"><span data-stu-id="308ad-115">JPEG</span></span>|<span data-ttu-id="308ad-116">JPG</span><span class="sxs-lookup"><span data-stu-id="308ad-116">.jpg</span></span>|

## <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="308ad-117">Отображение рисунка во время разработки</span><span class="sxs-lookup"><span data-stu-id="308ad-117">To display a picture at design time</span></span>

1. <span data-ttu-id="308ad-118">Нарисуйте элемент управления <xref:System.Windows.Forms.PictureBox> в форме.</span><span class="sxs-lookup"><span data-stu-id="308ad-118">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>

2. <span data-ttu-id="308ad-119">В окне **Свойства** выберите свойство <xref:System.Windows.Forms.PictureBox.Image%2A>, а затем нажмите кнопку с многоточием, чтобы открыть диалоговое окно **Открытие** .</span><span class="sxs-lookup"><span data-stu-id="308ad-119">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then select the ellipsis button to display the **Open** dialog box.</span></span>

3. <span data-ttu-id="308ad-120">Если вы ищете конкретный тип файла (например, GIF-файлы), выберите его в поле **файлы типа** .</span><span class="sxs-lookup"><span data-stu-id="308ad-120">If you're looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>

4. <span data-ttu-id="308ad-121">Выберите файл, который требуется отобразить.</span><span class="sxs-lookup"><span data-stu-id="308ad-121">Select the file you want to display.</span></span>

## <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="308ad-122">Очистка рисунка во время разработки</span><span class="sxs-lookup"><span data-stu-id="308ad-122">To clear the picture at design time</span></span>

1. <span data-ttu-id="308ad-123">В окне **Свойства** выберите свойство <xref:System.Windows.Forms.PictureBox.Image%2A>.</span><span class="sxs-lookup"><span data-stu-id="308ad-123">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property.</span></span> <span data-ttu-id="308ad-124">Щелкните правой кнопкой мыши маленький эскиз изображения, который отображается слева от имени объекта Image, и выберите команду **сбросить**.</span><span class="sxs-lookup"><span data-stu-id="308ad-124">Right-click the small thumbnail image that appears to the left of the name of the image object, and then choose **Reset**.</span></span>

## <a name="see-also"></a><span data-ttu-id="308ad-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="308ad-125">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="308ad-126">Общие сведения об элементе управления PictureBox</span><span class="sxs-lookup"><span data-stu-id="308ad-126">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="308ad-127">Практическое руководство. Изменение размера или размещения изображения во время выполнения</span><span class="sxs-lookup"><span data-stu-id="308ad-127">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="308ad-128">Практическое руководство. Установка изображений во время выполнения</span><span class="sxs-lookup"><span data-stu-id="308ad-128">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="308ad-129">Элемент управления PictureBox</span><span class="sxs-lookup"><span data-stu-id="308ad-129">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
