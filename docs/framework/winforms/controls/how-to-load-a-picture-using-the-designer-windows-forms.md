---
title: "Практическое руководство. Загрузка изображения с помощью конструктора (Windows Form)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9049bf5f9467401bff098459b8f5ed55c1ee1975
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="10f3e-102">Практическое руководство. Загрузка изображения с помощью конструктора (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="10f3e-102">How to: Load a Picture Using the Designer (Windows Forms)</span></span>
<span data-ttu-id="10f3e-103">С помощью Windows Forms <xref:System.Windows.Forms.PictureBox> управления, можно загружать и отображать рисунок на форме во время разработки, задав <xref:System.Windows.Forms.PictureBox.Image%2A> свойство допустимого рисунка.</span><span class="sxs-lookup"><span data-stu-id="10f3e-103">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="10f3e-104">В следующей таблице показаны допустимые типы файлов.</span><span class="sxs-lookup"><span data-stu-id="10f3e-104">The following table shows the acceptable file types.</span></span>  
  
|<span data-ttu-id="10f3e-105">Тип</span><span class="sxs-lookup"><span data-stu-id="10f3e-105">Type</span></span>|<span data-ttu-id="10f3e-106">Расширение имени файла</span><span class="sxs-lookup"><span data-stu-id="10f3e-106">File name extension</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="10f3e-107">Bitmap</span><span class="sxs-lookup"><span data-stu-id="10f3e-107">Bitmap</span></span>|<span data-ttu-id="10f3e-108">.bmp</span><span class="sxs-lookup"><span data-stu-id="10f3e-108">.bmp</span></span>|  
|<span data-ttu-id="10f3e-109">Значок</span><span class="sxs-lookup"><span data-stu-id="10f3e-109">Icon</span></span>|<span data-ttu-id="10f3e-110">ICO</span><span class="sxs-lookup"><span data-stu-id="10f3e-110">.ico</span></span>|  
|<span data-ttu-id="10f3e-111">GIF</span><span class="sxs-lookup"><span data-stu-id="10f3e-111">GIF</span></span>|<span data-ttu-id="10f3e-112">GIF</span><span class="sxs-lookup"><span data-stu-id="10f3e-112">.gif</span></span>|  
|<span data-ttu-id="10f3e-113">Метафайл</span><span class="sxs-lookup"><span data-stu-id="10f3e-113">Metafile</span></span>|<span data-ttu-id="10f3e-114">.wmf</span><span class="sxs-lookup"><span data-stu-id="10f3e-114">.wmf</span></span>|  
|<span data-ttu-id="10f3e-115">JPEG</span><span class="sxs-lookup"><span data-stu-id="10f3e-115">JPEG</span></span>|<span data-ttu-id="10f3e-116">.jpg</span><span class="sxs-lookup"><span data-stu-id="10f3e-116">.jpg</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="10f3e-117">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="10f3e-117">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="10f3e-118">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="10f3e-118">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="10f3e-119">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="10f3e-119">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="10f3e-120">Для отображения рисунка во время разработки</span><span class="sxs-lookup"><span data-stu-id="10f3e-120">To display a picture at design time</span></span>  
  
1.  <span data-ttu-id="10f3e-121">Рисование <xref:System.Windows.Forms.PictureBox> элемента управления в форме.</span><span class="sxs-lookup"><span data-stu-id="10f3e-121">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>  
  
2.  <span data-ttu-id="10f3e-122">В окне «Свойства» выберите <xref:System.Windows.Forms.PictureBox.Image%2A> свойства, а затем нажмите кнопку с многоточием для отображения **откройте** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="10f3e-122">On the Properties window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then click the ellipsis button to display the **Open** dialog box.</span></span>  
  
3.  <span data-ttu-id="10f3e-123">Если вы ищете файлов определенного типа (например, GIF-файлы), выберите ее в **файлы типа** поле.</span><span class="sxs-lookup"><span data-stu-id="10f3e-123">If you are looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>  
  
4.  <span data-ttu-id="10f3e-124">Выберите файл, который требуется отобразить.</span><span class="sxs-lookup"><span data-stu-id="10f3e-124">Select the file you want to display.</span></span>  
  
### <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="10f3e-125">Чтобы очистить рисунок во время разработки</span><span class="sxs-lookup"><span data-stu-id="10f3e-125">To clear the picture at design time</span></span>  
  
1.  <span data-ttu-id="10f3e-126">На **свойства** выберите <xref:System.Windows.Forms.PictureBox.Image%2A> свойство и щелкните правой кнопкой мыши отображается слева от имени объекта рисунка небольшой эскиз.</span><span class="sxs-lookup"><span data-stu-id="10f3e-126">On the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property and right-click the small thumbnail image that appears to the left of the name of the image object.</span></span> <span data-ttu-id="10f3e-127">Выберите **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="10f3e-127">Choose **Reset**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10f3e-128">См. также</span><span class="sxs-lookup"><span data-stu-id="10f3e-128">See Also</span></span>  
 <xref:System.Windows.Forms.PictureBox>  
 [<span data-ttu-id="10f3e-129">Общие сведения об элементе управления PictureBox</span><span class="sxs-lookup"><span data-stu-id="10f3e-129">PictureBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [<span data-ttu-id="10f3e-130">Практическое руководство. Изменение размера или размещения изображения во время выполнения</span><span class="sxs-lookup"><span data-stu-id="10f3e-130">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)  
 [<span data-ttu-id="10f3e-131">Практическое руководство. Установка изображений во время выполнения</span><span class="sxs-lookup"><span data-stu-id="10f3e-131">How to: Set Pictures at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [<span data-ttu-id="10f3e-132">Элемент управления PictureBox</span><span class="sxs-lookup"><span data-stu-id="10f3e-132">PictureBox Control</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
