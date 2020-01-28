---
title: Графика и рисование
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: 10ad18d38c84f6e447601ab6c8bf1a953dabb7cf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746399"
---
# <a name="graphics-and-drawing-in-windows-forms"></a><span data-ttu-id="fd46a-102">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fd46a-102">Graphics and Drawing in Windows Forms</span></span>
<span data-ttu-id="fd46a-103">Среда CLR использует расширенную реализацию Windows интерфейс графических устройств (GDI) с именем GDI+.</span><span class="sxs-lookup"><span data-stu-id="fd46a-103">The common language runtime uses an advanced implementation of the Windows Graphics Device Interface (GDI) called GDI+.</span></span> <span data-ttu-id="fd46a-104">С помощью GDI+ можно создавать графики, рисовать текст и манипулировать графическими изображениями как объектами.</span><span class="sxs-lookup"><span data-stu-id="fd46a-104">With GDI+ you can create graphics, draw text, and manipulate graphical images as objects.</span></span> <span data-ttu-id="fd46a-105">Интерфейс GDI+ обеспечивает производительность и простоту использования.</span><span class="sxs-lookup"><span data-stu-id="fd46a-105">GDI+ is designed to offer performance and ease of use.</span></span> <span data-ttu-id="fd46a-106">GDI+ можно использовать для отрисовки графических изображений на Windows Forms и элементы управления.</span><span class="sxs-lookup"><span data-stu-id="fd46a-106">You can use GDI+ to render graphical images on Windows Forms and controls.</span></span> <span data-ttu-id="fd46a-107">Хотя вы не можете использовать GDI+ непосредственно в веб-формах, можно отображать графические изображения с помощью серверного веб-элемента управления Image.</span><span class="sxs-lookup"><span data-stu-id="fd46a-107">Although you cannot use GDI+ directly on Web Forms, you can display graphical images through the Image Web Server control.</span></span>  
  
 <span data-ttu-id="fd46a-108">В этом разделе вы найдете разделы, в которых представлены основные принципы программирования GDI+.</span><span class="sxs-lookup"><span data-stu-id="fd46a-108">In this section, you will find topics that introduce the fundamentals of GDI+ programming.</span></span> <span data-ttu-id="fd46a-109">Хотя он не является полным справочником, в нем содержатся сведения об объектах <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> и <xref:System.Drawing.Color> и способах выполнения таких задач, как рисование фигур, создание текста, отображение рисунков.</span><span class="sxs-lookup"><span data-stu-id="fd46a-109">Although not intended to be a comprehensive reference, this section includes information about the <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush>, and <xref:System.Drawing.Color> objects, and explains how to perform such tasks as drawing shapes, drawing text, or displaying images.</span></span> <span data-ttu-id="fd46a-110">Дополнительные сведения см. в [справочнике по GDI+](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span><span class="sxs-lookup"><span data-stu-id="fd46a-110">For more information, see [GDI+ Reference](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span></span>  
  
 <span data-ttu-id="fd46a-111">Если вы хотите немедленно приступить к работе, см. статью [Приступая к программированию графики](getting-started-with-graphics-programming.md).</span><span class="sxs-lookup"><span data-stu-id="fd46a-111">If you'd like to jump in and get started right away, see [Getting Started with Graphics Programming](getting-started-with-graphics-programming.md).</span></span> <span data-ttu-id="fd46a-112">Она содержит разделы, посвященные использованию кода для рисования линий, фигур, текста и других элементов в формах Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="fd46a-112">It has topics on how to use code to draw lines, shapes, text, and more on Windows forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fd46a-113">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="fd46a-113">In This Section</span></span>  
 [<span data-ttu-id="fd46a-114">Общие сведения о графике</span><span class="sxs-lookup"><span data-stu-id="fd46a-114">Graphics Overview</span></span>](graphics-overview-windows-forms.md)  
 <span data-ttu-id="fd46a-115">Общие сведения об управляемых классах, связанных с графикой.</span><span class="sxs-lookup"><span data-stu-id="fd46a-115">Provides an introduction to the graphics-related managed classes.</span></span>  
  
 [<span data-ttu-id="fd46a-116">Управляемый код GDI+</span><span class="sxs-lookup"><span data-stu-id="fd46a-116">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
 <span data-ttu-id="fd46a-117">Предоставляет сведения об управляемых классах GDI+.</span><span class="sxs-lookup"><span data-stu-id="fd46a-117">Provides information about the managed GDI+ classes.</span></span>  
  
 [<span data-ttu-id="fd46a-118">Использование управляемых графических классов</span><span class="sxs-lookup"><span data-stu-id="fd46a-118">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)  
 <span data-ttu-id="fd46a-119">Демонстрирует выполнение различных задач с помощью управляемых классов GDI+.</span><span class="sxs-lookup"><span data-stu-id="fd46a-119">Demonstrates how to complete a variety of tasks using the GDI+ managed classes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="fd46a-120">Справочные сведения</span><span class="sxs-lookup"><span data-stu-id="fd46a-120">Reference</span></span>  
 <xref:System.Drawing>  
 <span data-ttu-id="fd46a-121">Предоставляет доступ к функциональным возможностям графического интерфейса GDI+ Basic.</span><span class="sxs-lookup"><span data-stu-id="fd46a-121">Provides access to GDI+ basic graphics functionality.</span></span>  
  
 <xref:System.Drawing.Drawing2D>  
 <span data-ttu-id="fd46a-122">Расширенные функциональные возможности для создания двухмерной и векторной графики.</span><span class="sxs-lookup"><span data-stu-id="fd46a-122">Provides advanced two-dimensional and vector graphics functionality.</span></span>  
  
 <xref:System.Drawing.Imaging>  
 <span data-ttu-id="fd46a-123">Предоставляет расширенные функции работы с образами GDI+.</span><span class="sxs-lookup"><span data-stu-id="fd46a-123">Provides advanced GDI+ imaging functionality.</span></span>  
  
 <xref:System.Drawing.Text>  
 <span data-ttu-id="fd46a-124">Предоставляет расширенные функции оформления GDI+.</span><span class="sxs-lookup"><span data-stu-id="fd46a-124">Provides advanced GDI+ typography functionality.</span></span> <span data-ttu-id="fd46a-125">Классы в этом пространстве имен позволяют создавать и использовать коллекции шрифтов.</span><span class="sxs-lookup"><span data-stu-id="fd46a-125">The classes in this namespace can be used to create and use collections of fonts.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="fd46a-126">Функции печати.</span><span class="sxs-lookup"><span data-stu-id="fd46a-126">Provides printing functionality.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fd46a-127">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="fd46a-127">Related Sections</span></span>  
 [<span data-ttu-id="fd46a-128">Рисование и отрисовка пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="fd46a-128">Custom Control Painting and Rendering</span></span>](../controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="fd46a-129">Подробные сведения о способах написания кода для рисования элементов управления.</span><span class="sxs-lookup"><span data-stu-id="fd46a-129">Details how to provide code for painting controls.</span></span>
