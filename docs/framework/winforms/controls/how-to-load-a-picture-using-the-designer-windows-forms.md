---
title: Практическое руководство. Загрузка изображения с помощью конструктора (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 6bdf7c3df0ffd97dd88a4c442a8a73593a0447ee
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336386"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="e1cec-102">Практическое руководство. Загрузка изображения с помощью конструктора (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e1cec-102">How to: Load a Picture Using the Designer (Windows Forms)</span></span>
<span data-ttu-id="e1cec-103">С помощью Windows Forms <xref:System.Windows.Forms.PictureBox> элемента управления, можно загружать и отображать изображение в форме во время разработки, установив <xref:System.Windows.Forms.PictureBox.Image%2A> свойство допустимого рисунка.</span><span class="sxs-lookup"><span data-stu-id="e1cec-103">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="e1cec-104">В следующей таблице показаны допустимые типы файлов.</span><span class="sxs-lookup"><span data-stu-id="e1cec-104">The following table shows the acceptable file types.</span></span>  
  
|<span data-ttu-id="e1cec-105">Тип</span><span class="sxs-lookup"><span data-stu-id="e1cec-105">Type</span></span>|<span data-ttu-id="e1cec-106">Расширение имени файла</span><span class="sxs-lookup"><span data-stu-id="e1cec-106">File name extension</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="e1cec-107">Bitmap</span><span class="sxs-lookup"><span data-stu-id="e1cec-107">Bitmap</span></span>|<span data-ttu-id="e1cec-108">.bmp</span><span class="sxs-lookup"><span data-stu-id="e1cec-108">.bmp</span></span>|  
|<span data-ttu-id="e1cec-109">Значок</span><span class="sxs-lookup"><span data-stu-id="e1cec-109">Icon</span></span>|<span data-ttu-id="e1cec-110">ICO</span><span class="sxs-lookup"><span data-stu-id="e1cec-110">.ico</span></span>|  
|<span data-ttu-id="e1cec-111">GIF</span><span class="sxs-lookup"><span data-stu-id="e1cec-111">GIF</span></span>|<span data-ttu-id="e1cec-112">GIF</span><span class="sxs-lookup"><span data-stu-id="e1cec-112">.gif</span></span>|  
|<span data-ttu-id="e1cec-113">Метафайл</span><span class="sxs-lookup"><span data-stu-id="e1cec-113">Metafile</span></span>|<span data-ttu-id="e1cec-114">.wmf</span><span class="sxs-lookup"><span data-stu-id="e1cec-114">.wmf</span></span>|  
|<span data-ttu-id="e1cec-115">JPEG</span><span class="sxs-lookup"><span data-stu-id="e1cec-115">JPEG</span></span>|<span data-ttu-id="e1cec-116">.jpg</span><span class="sxs-lookup"><span data-stu-id="e1cec-116">.jpg</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="e1cec-117">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="e1cec-117">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="e1cec-118">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="e1cec-118">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="e1cec-119">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="e1cec-119">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="e1cec-120">Для отображения рисунка во время разработки</span><span class="sxs-lookup"><span data-stu-id="e1cec-120">To display a picture at design time</span></span>  
  
1. <span data-ttu-id="e1cec-121">Рисование <xref:System.Windows.Forms.PictureBox> управления на форме.</span><span class="sxs-lookup"><span data-stu-id="e1cec-121">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>  
  
2. <span data-ttu-id="e1cec-122">В окне «Свойства» выберите <xref:System.Windows.Forms.PictureBox.Image%2A> свойства, а затем нажмите кнопку с многоточием для отображения **откройте** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="e1cec-122">On the Properties window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then click the ellipsis button to display the **Open** dialog box.</span></span>  
  
3. <span data-ttu-id="e1cec-123">Если вы ищете файлов определенного типа (например, GIF-файлы), выберите ее в **файлы типа** поле.</span><span class="sxs-lookup"><span data-stu-id="e1cec-123">If you are looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>  
  
4. <span data-ttu-id="e1cec-124">Выберите файл, который вы хотите отобразить.</span><span class="sxs-lookup"><span data-stu-id="e1cec-124">Select the file you want to display.</span></span>  
  
### <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="e1cec-125">Чтобы очистить рисунок во время разработки</span><span class="sxs-lookup"><span data-stu-id="e1cec-125">To clear the picture at design time</span></span>  
  
1. <span data-ttu-id="e1cec-126">На **свойства** выберите <xref:System.Windows.Forms.PictureBox.Image%2A> свойство и щелкните правой кнопкой мыши небольшой эскиза, который отображается слева от имени объекта образа.</span><span class="sxs-lookup"><span data-stu-id="e1cec-126">On the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property and right-click the small thumbnail image that appears to the left of the name of the image object.</span></span> <span data-ttu-id="e1cec-127">Выберите **сбросить**.</span><span class="sxs-lookup"><span data-stu-id="e1cec-127">Choose **Reset**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1cec-128">См. также</span><span class="sxs-lookup"><span data-stu-id="e1cec-128">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="e1cec-129">Общие сведения об элементе управления PictureBox</span><span class="sxs-lookup"><span data-stu-id="e1cec-129">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="e1cec-130">Практическое руководство. Изменение размера или размещения изображения во время выполнения</span><span class="sxs-lookup"><span data-stu-id="e1cec-130">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="e1cec-131">Практическое руководство. Установка изображений во время выполнения</span><span class="sxs-lookup"><span data-stu-id="e1cec-131">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="e1cec-132">Элемент управления PictureBox</span><span class="sxs-lookup"><span data-stu-id="e1cec-132">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
