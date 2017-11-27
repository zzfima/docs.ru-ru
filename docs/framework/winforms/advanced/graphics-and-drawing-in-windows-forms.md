---
title: "Объекты Graphics и Drawing в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b2e8bde5d1c2904723282f03a815f17c5cc7622d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="graphics-and-drawing-in-windows-forms"></a><span data-ttu-id="acfde-102">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="acfde-102">Graphics and Drawing in Windows Forms</span></span>
<span data-ttu-id="acfde-103">Среда CLR использует расширенную реализацию интерфейса графических устройств Windows ([!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]) под названием [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="acfde-103">The common language runtime uses an advanced implementation of the Windows Graphics Device Interface ([!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]) called [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="acfde-104">С помощью [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] можно создавать графические элементы, рисовать текст и управлять графическими изображениями как объектами.</span><span class="sxs-lookup"><span data-stu-id="acfde-104">With [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] you can create graphics, draw text, and manipulate graphical images as objects.</span></span> <span data-ttu-id="acfde-105">Интерфейс [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] отличается высоким быстродействием и удобен в использовании.</span><span class="sxs-lookup"><span data-stu-id="acfde-105">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] is designed to offer performance and ease of use.</span></span> <span data-ttu-id="acfde-106">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] можно использовать для отрисовки графических изображений в формах и элементах управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="acfde-106">You can use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to render graphical images on Windows Forms and controls.</span></span> <span data-ttu-id="acfde-107">Хотя [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] нельзя использовать непосредственно в веб-формах, графические изображения можно выводить через элемент управления веб-сервера Image.</span><span class="sxs-lookup"><span data-stu-id="acfde-107">Although you cannot use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] directly on Web Forms, you can display graphical images through the Image Web Server control.</span></span>  
  
 <span data-ttu-id="acfde-108">В этом разделе описаны основы программирования с использованием [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="acfde-108">In this section, you will find topics that introduce the fundamentals of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] programming.</span></span> <span data-ttu-id="acfde-109">Хотя он не является полным справочником, в нем содержатся сведения об объектах <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> и <xref:System.Drawing.Color> и способах выполнения таких задач, как рисование фигур, создание текста, отображение рисунков.</span><span class="sxs-lookup"><span data-stu-id="acfde-109">Although not intended to be a comprehensive reference, this section includes information about the <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush>, and <xref:System.Drawing.Color> objects, and explains how to perform such tasks as drawing shapes, drawing text, or displaying images.</span></span> <span data-ttu-id="acfde-110">Дополнительные сведения см. в разделе [GDI + ссылка](https://msdn.microsoft.com/library/vs/alm/ms533799.aspx).</span><span class="sxs-lookup"><span data-stu-id="acfde-110">For more information, see [GDI+ Reference](https://msdn.microsoft.com/library/vs/alm/ms533799.aspx).</span></span>  
  
 <span data-ttu-id="acfde-111">Если вы хотите немедленно приступить к работе, см. статью [Приступая к программированию графики](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md).</span><span class="sxs-lookup"><span data-stu-id="acfde-111">If you'd like to jump in and get started right away, see [Getting Started with Graphics Programming](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md).</span></span> <span data-ttu-id="acfde-112">Она содержит разделы, посвященные использованию кода для рисования линий, фигур, текста и других элементов в формах Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="acfde-112">It has topics on how to use code to draw lines, shapes, text, and more on Windows forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="acfde-113">Содержание</span><span class="sxs-lookup"><span data-stu-id="acfde-113">In This Section</span></span>  
 [<span data-ttu-id="acfde-114">Общие сведения о графике</span><span class="sxs-lookup"><span data-stu-id="acfde-114">Graphics Overview</span></span>](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)  
 <span data-ttu-id="acfde-115">Общие сведения об управляемых классах, связанных с графикой.</span><span class="sxs-lookup"><span data-stu-id="acfde-115">Provides an introduction to the graphics-related managed classes.</span></span>  
  
 [<span data-ttu-id="acfde-116">Управляемый код GDI+</span><span class="sxs-lookup"><span data-stu-id="acfde-116">About GDI+ Managed Code</span></span>](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
 <span data-ttu-id="acfde-117">Сведения об управляемых классах [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="acfde-117">Provides information about the managed [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes.</span></span>  
  
 [<span data-ttu-id="acfde-118">Использование управляемых графических классов</span><span class="sxs-lookup"><span data-stu-id="acfde-118">Using Managed Graphics Classes</span></span>](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)  
 <span data-ttu-id="acfde-119">Демонстрируется выполнение различных задач с помощью управляемых классов [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="acfde-119">Demonstrates how to complete a variety of tasks using the [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] managed classes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="acfde-120">Ссылка</span><span class="sxs-lookup"><span data-stu-id="acfde-120">Reference</span></span>  
 <xref:System.Drawing>  
 <span data-ttu-id="acfde-121">Доступ к основным графическим функциям [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="acfde-121">Provides access to [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] basic graphics functionality.</span></span>  
  
 <xref:System.Drawing.Drawing2D>  
 <span data-ttu-id="acfde-122">Расширенные функциональные возможности для создания двухмерной и векторной графики.</span><span class="sxs-lookup"><span data-stu-id="acfde-122">Provides advanced two-dimensional and vector graphics functionality.</span></span>  
  
 <xref:System.Drawing.Imaging>  
 <span data-ttu-id="acfde-123">Расширенный набор графических функций [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="acfde-123">Provides advanced [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] imaging functionality.</span></span>  
  
 <xref:System.Drawing.Text>  
 <span data-ttu-id="acfde-124">Расширенный набор типографических функций [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="acfde-124">Provides advanced [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] typography functionality.</span></span> <span data-ttu-id="acfde-125">Классы в этом пространстве имен позволяют создавать и использовать коллекции шрифтов.</span><span class="sxs-lookup"><span data-stu-id="acfde-125">The classes in this namespace can be used to create and use collections of fonts.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="acfde-126">Функции печати.</span><span class="sxs-lookup"><span data-stu-id="acfde-126">Provides printing functionality.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="acfde-127">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="acfde-127">Related Sections</span></span>  
 [<span data-ttu-id="acfde-128">Рисование и отрисовка пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="acfde-128">Custom Control Painting and Rendering</span></span>](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="acfde-129">Подробные сведения о способах написания кода для рисования элементов управления.</span><span class="sxs-lookup"><span data-stu-id="acfde-129">Details how to provide code for painting controls.</span></span>
