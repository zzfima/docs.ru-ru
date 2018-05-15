---
title: Практическое руководство. Загрузка изображения с помощью конструктора (Windows Form)
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 5eb85c6f3ca232f8b53ac01d57ee71f73415cf83
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="8c123-102">Практическое руководство. Загрузка изображения с помощью конструктора (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="8c123-102">How to: Load a Picture Using the Designer (Windows Forms)</span></span>
<span data-ttu-id="8c123-103">С помощью Windows Forms <xref:System.Windows.Forms.PictureBox> управления, можно загружать и отображать рисунок на форме во время разработки, задав <xref:System.Windows.Forms.PictureBox.Image%2A> свойство допустимого рисунка.</span><span class="sxs-lookup"><span data-stu-id="8c123-103">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="8c123-104">В следующей таблице показаны допустимые типы файлов.</span><span class="sxs-lookup"><span data-stu-id="8c123-104">The following table shows the acceptable file types.</span></span>  
  
|<span data-ttu-id="8c123-105">Тип</span><span class="sxs-lookup"><span data-stu-id="8c123-105">Type</span></span>|<span data-ttu-id="8c123-106">Расширение имени файла</span><span class="sxs-lookup"><span data-stu-id="8c123-106">File name extension</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="8c123-107">Bitmap</span><span class="sxs-lookup"><span data-stu-id="8c123-107">Bitmap</span></span>|<span data-ttu-id="8c123-108">.bmp</span><span class="sxs-lookup"><span data-stu-id="8c123-108">.bmp</span></span>|  
|<span data-ttu-id="8c123-109">Значок</span><span class="sxs-lookup"><span data-stu-id="8c123-109">Icon</span></span>|<span data-ttu-id="8c123-110">ICO</span><span class="sxs-lookup"><span data-stu-id="8c123-110">.ico</span></span>|  
|<span data-ttu-id="8c123-111">GIF</span><span class="sxs-lookup"><span data-stu-id="8c123-111">GIF</span></span>|<span data-ttu-id="8c123-112">GIF</span><span class="sxs-lookup"><span data-stu-id="8c123-112">.gif</span></span>|  
|<span data-ttu-id="8c123-113">Метафайл</span><span class="sxs-lookup"><span data-stu-id="8c123-113">Metafile</span></span>|<span data-ttu-id="8c123-114">.wmf</span><span class="sxs-lookup"><span data-stu-id="8c123-114">.wmf</span></span>|  
|<span data-ttu-id="8c123-115">JPEG</span><span class="sxs-lookup"><span data-stu-id="8c123-115">JPEG</span></span>|<span data-ttu-id="8c123-116">.jpg</span><span class="sxs-lookup"><span data-stu-id="8c123-116">.jpg</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="8c123-117">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="8c123-117">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="8c123-118">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="8c123-118">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="8c123-119">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="8c123-119">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="8c123-120">Для отображения рисунка во время разработки</span><span class="sxs-lookup"><span data-stu-id="8c123-120">To display a picture at design time</span></span>  
  
1.  <span data-ttu-id="8c123-121">Рисование <xref:System.Windows.Forms.PictureBox> элемента управления в форме.</span><span class="sxs-lookup"><span data-stu-id="8c123-121">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>  
  
2.  <span data-ttu-id="8c123-122">В окне «Свойства» выберите <xref:System.Windows.Forms.PictureBox.Image%2A> свойства, а затем нажмите кнопку с многоточием для отображения **откройте** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="8c123-122">On the Properties window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then click the ellipsis button to display the **Open** dialog box.</span></span>  
  
3.  <span data-ttu-id="8c123-123">Если вы ищете файлов определенного типа (например, GIF-файлы), выберите ее в **файлы типа** поле.</span><span class="sxs-lookup"><span data-stu-id="8c123-123">If you are looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>  
  
4.  <span data-ttu-id="8c123-124">Выберите файл, который требуется отобразить.</span><span class="sxs-lookup"><span data-stu-id="8c123-124">Select the file you want to display.</span></span>  
  
### <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="8c123-125">Чтобы очистить рисунок во время разработки</span><span class="sxs-lookup"><span data-stu-id="8c123-125">To clear the picture at design time</span></span>  
  
1.  <span data-ttu-id="8c123-126">На **свойства** выберите <xref:System.Windows.Forms.PictureBox.Image%2A> свойство и щелкните правой кнопкой мыши отображается слева от имени объекта рисунка небольшой эскиз.</span><span class="sxs-lookup"><span data-stu-id="8c123-126">On the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property and right-click the small thumbnail image that appears to the left of the name of the image object.</span></span> <span data-ttu-id="8c123-127">Выберите **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="8c123-127">Choose **Reset**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c123-128">См. также</span><span class="sxs-lookup"><span data-stu-id="8c123-128">See Also</span></span>  
 <xref:System.Windows.Forms.PictureBox>  
 [<span data-ttu-id="8c123-129">Общие сведения об элементе управления PictureBox</span><span class="sxs-lookup"><span data-stu-id="8c123-129">PictureBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [<span data-ttu-id="8c123-130">Практическое руководство. Изменение размера или размещения изображения во время выполнения</span><span class="sxs-lookup"><span data-stu-id="8c123-130">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)  
 [<span data-ttu-id="8c123-131">Практическое руководство. Установка изображений во время выполнения</span><span class="sxs-lookup"><span data-stu-id="8c123-131">How to: Set Pictures at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [<span data-ttu-id="8c123-132">Элемент управления PictureBox</span><span class="sxs-lookup"><span data-stu-id="8c123-132">PictureBox Control</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
