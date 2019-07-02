---
title: Объекты Graphics и Drawing в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: e110203605c31f90f71c949f81c18ebf464d52eb
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505540"
---
# <a name="graphics-and-drawing-in-windows-forms"></a><span data-ttu-id="0a869-102">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0a869-102">Graphics and Drawing in Windows Forms</span></span>
<span data-ttu-id="0a869-103">Среда CLR использует расширенную реализацию из Windows графических устройств интерфейса (GDI) вызывается GDI +.</span><span class="sxs-lookup"><span data-stu-id="0a869-103">The common language runtime uses an advanced implementation of the Windows Graphics Device Interface (GDI) called GDI+.</span></span> <span data-ttu-id="0a869-104">С помощью GDI + Создание графических объектов, рисовать текст и управлять графическими изображениями как объектами.</span><span class="sxs-lookup"><span data-stu-id="0a869-104">With GDI+ you can create graphics, draw text, and manipulate graphical images as objects.</span></span> <span data-ttu-id="0a869-105">GDI + разработана для обеспечения производительности и удобства использования.</span><span class="sxs-lookup"><span data-stu-id="0a869-105">GDI+ is designed to offer performance and ease of use.</span></span> <span data-ttu-id="0a869-106">GDI + можно использовать для отрисовки графических изображений в Windows Forms и элементах управления.</span><span class="sxs-lookup"><span data-stu-id="0a869-106">You can use GDI+ to render graphical images on Windows Forms and controls.</span></span> <span data-ttu-id="0a869-107">Несмотря на то, что нельзя использовать GDI + непосредственно на веб-форм, можно отобразить графические изображения через элемент управления веб-сервера Image.</span><span class="sxs-lookup"><span data-stu-id="0a869-107">Although you cannot use GDI+ directly on Web Forms, you can display graphical images through the Image Web Server control.</span></span>  
  
 <span data-ttu-id="0a869-108">В этом разделе вы найдете описаны основы программирования GDI +.</span><span class="sxs-lookup"><span data-stu-id="0a869-108">In this section, you will find topics that introduce the fundamentals of GDI+ programming.</span></span> <span data-ttu-id="0a869-109">Хотя он не является полным справочником, в нем содержатся сведения об объектах <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> и <xref:System.Drawing.Color> и способах выполнения таких задач, как рисование фигур, создание текста, отображение рисунков.</span><span class="sxs-lookup"><span data-stu-id="0a869-109">Although not intended to be a comprehensive reference, this section includes information about the <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush>, and <xref:System.Drawing.Color> objects, and explains how to perform such tasks as drawing shapes, drawing text, or displaying images.</span></span> <span data-ttu-id="0a869-110">Дополнительные сведения см. в разделе [GDI + ссылку](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span><span class="sxs-lookup"><span data-stu-id="0a869-110">For more information, see [GDI+ Reference](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span></span>  
  
 <span data-ttu-id="0a869-111">Если вы хотите немедленно приступить к работе, см. статью [Приступая к программированию графики](getting-started-with-graphics-programming.md).</span><span class="sxs-lookup"><span data-stu-id="0a869-111">If you'd like to jump in and get started right away, see [Getting Started with Graphics Programming](getting-started-with-graphics-programming.md).</span></span> <span data-ttu-id="0a869-112">Она содержит разделы, посвященные использованию кода для рисования линий, фигур, текста и других элементов в формах Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0a869-112">It has topics on how to use code to draw lines, shapes, text, and more on Windows forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0a869-113">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="0a869-113">In This Section</span></span>  
 [<span data-ttu-id="0a869-114">Общие сведения о графике</span><span class="sxs-lookup"><span data-stu-id="0a869-114">Graphics Overview</span></span>](graphics-overview-windows-forms.md)  
 <span data-ttu-id="0a869-115">Общие сведения об управляемых классах, связанных с графикой.</span><span class="sxs-lookup"><span data-stu-id="0a869-115">Provides an introduction to the graphics-related managed classes.</span></span>  
  
 [<span data-ttu-id="0a869-116">Управляемый код GDI+</span><span class="sxs-lookup"><span data-stu-id="0a869-116">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
 <span data-ttu-id="0a869-117">Сведения об управляемых классах GDI +.</span><span class="sxs-lookup"><span data-stu-id="0a869-117">Provides information about the managed GDI+ classes.</span></span>  
  
 [<span data-ttu-id="0a869-118">Использование управляемых графических классов</span><span class="sxs-lookup"><span data-stu-id="0a869-118">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)  
 <span data-ttu-id="0a869-119">Демонстрирует, как для завершения различных задач с помощью GDI + управляемые классы.</span><span class="sxs-lookup"><span data-stu-id="0a869-119">Demonstrates how to complete a variety of tasks using the GDI+ managed classes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0a869-120">Ссылка</span><span class="sxs-lookup"><span data-stu-id="0a869-120">Reference</span></span>  
 <xref:System.Drawing>  
 <span data-ttu-id="0a869-121">Предоставляет доступ к основным графическим функциям GDI +.</span><span class="sxs-lookup"><span data-stu-id="0a869-121">Provides access to GDI+ basic graphics functionality.</span></span>  
  
 <xref:System.Drawing.Drawing2D>  
 <span data-ttu-id="0a869-122">Расширенные функциональные возможности для создания двухмерной и векторной графики.</span><span class="sxs-lookup"><span data-stu-id="0a869-122">Provides advanced two-dimensional and vector graphics functionality.</span></span>  
  
 <xref:System.Drawing.Imaging>  
 <span data-ttu-id="0a869-123">Предоставляет расширенный набор графических функций GDI +.</span><span class="sxs-lookup"><span data-stu-id="0a869-123">Provides advanced GDI+ imaging functionality.</span></span>  
  
 <xref:System.Drawing.Text>  
 <span data-ttu-id="0a869-124">Предоставляет расширенный набор типографических функций GDI +.</span><span class="sxs-lookup"><span data-stu-id="0a869-124">Provides advanced GDI+ typography functionality.</span></span> <span data-ttu-id="0a869-125">Классы в этом пространстве имен позволяют создавать и использовать коллекции шрифтов.</span><span class="sxs-lookup"><span data-stu-id="0a869-125">The classes in this namespace can be used to create and use collections of fonts.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="0a869-126">Функции печати.</span><span class="sxs-lookup"><span data-stu-id="0a869-126">Provides printing functionality.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0a869-127">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="0a869-127">Related Sections</span></span>  
 [<span data-ttu-id="0a869-128">Рисование и отрисовка пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="0a869-128">Custom Control Painting and Rendering</span></span>](../controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="0a869-129">Подробные сведения о способах написания кода для рисования элементов управления.</span><span class="sxs-lookup"><span data-stu-id="0a869-129">Details how to provide code for painting controls.</span></span>
