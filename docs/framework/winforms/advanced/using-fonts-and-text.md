---
title: Шрифты и текст
ms.date: 03/30/2017
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing in Windows Forms
- examples [Windows Forms], fonts and text
- fonts [Windows Forms], using in Windows Forms
- strings [Windows Forms], drawing in Windows Forms
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
ms.openlocfilehash: 73a4af5fe7367e777fcb83af8c84c09be91e5b1e
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505118"
---
# <a name="using-fonts-and-text"></a><span data-ttu-id="f9c6a-102">Шрифты и текст</span><span class="sxs-lookup"><span data-stu-id="f9c6a-102">Using Fonts and Text</span></span>
<span data-ttu-id="f9c6a-103">Существует несколько классов, предоставляемых GDI + и GDI для рисования текста в формах Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-103">There are several classes offered by GDI+ and GDI for drawing text on Windows Forms.</span></span> <span data-ttu-id="f9c6a-104">GDI + <xref:System.Drawing.Graphics> содержит несколько <xref:System.Drawing.Graphics.DrawString%2A> методы, которые позволяют указать различные свойства текста, таких как местоположение, ограничивающий прямоугольник, шрифт и формат.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-104">The GDI+ <xref:System.Drawing.Graphics> class has several <xref:System.Drawing.Graphics.DrawString%2A> methods that allow you to specify various features of text, such as location, bounding rectangle, font, and format.</span></span> <span data-ttu-id="f9c6a-105">Кроме того, можно нарисовать и измерить текста с использованием GDI, с помощью статического <xref:System.Windows.Forms.TextRenderer.DrawText%2A> и <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> методы `TextRenderer` класса.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-105">In addition, you can draw and measure text with GDI using the static <xref:System.Windows.Forms.TextRenderer.DrawText%2A> and <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> methods offered by the `TextRenderer` class.</span></span> <span data-ttu-id="f9c6a-106">Методы GDI также позволяют указывать расположение, шрифт и формат.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-106">The GDI methods also allow you to specify location, font, and format.</span></span> <span data-ttu-id="f9c6a-107">Вы можете GDI или GDI + для прорисовки текста; Тем не менее GDI обычно обеспечивает более высокую производительность и более точные измерения текста.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-107">You can choose either GDI or GDI+ for text rendering; however, GDI generally offers better performance and more accurate text measuring.</span></span> <span data-ttu-id="f9c6a-108">Другие классы, которые влияют на отрисовку текста включают `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, и `TextFormatFlags`.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-108">Other classes that contribute to text rendering include `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, and `TextFormatFlags`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f9c6a-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="f9c6a-109">In This Section</span></span>  
 [<span data-ttu-id="f9c6a-110">Практическое руководство. Шрифты и их семейств</span><span class="sxs-lookup"><span data-stu-id="f9c6a-110">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)  
 <span data-ttu-id="f9c6a-111">Демонстрируется создание `Font` и `FontFamily` объектов.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-111">Shows how to create `Font` and `FontFamily` objects.</span></span>  
  
 [<span data-ttu-id="f9c6a-112">Практическое руководство. Рисование текста в указанном расположении</span><span class="sxs-lookup"><span data-stu-id="f9c6a-112">How to: Draw Text at a Specified Location</span></span>](how-to-draw-text-at-a-specified-location.md)  
 <span data-ttu-id="f9c6a-113">Описывает способ рисования текста в определенном расположении с помощью GDI + и GDI.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-113">Describes how to draw text in a certain location using GDI+ and GDI.</span></span>  
  
 [<span data-ttu-id="f9c6a-114">Практическое руководство. Многострочный вывод текста в прямоугольнике</span><span class="sxs-lookup"><span data-stu-id="f9c6a-114">How to: Draw Wrapped Text in a Rectangle</span></span>](how-to-draw-wrapped-text-in-a-rectangle.md)  
 <span data-ttu-id="f9c6a-115">Объясняется, как для рисования текста в прямоугольнике с помощью GDI + и GDI.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-115">Explains how to draw text in a rectangle using GDI+ and GDI.</span></span>  
  
 [<span data-ttu-id="f9c6a-116">Практическое руководство. Рисование текста с использованием GDI</span><span class="sxs-lookup"><span data-stu-id="f9c6a-116">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)  
 <span data-ttu-id="f9c6a-117">В этой статье демонстрируется использование GDI для рисования текста.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-117">Demonstrates how to use GDI for drawing text.</span></span>  
  
 [<span data-ttu-id="f9c6a-118">Практическое руководство. Выравнивание рисуемого текста</span><span class="sxs-lookup"><span data-stu-id="f9c6a-118">How to: Align Drawn Text</span></span>](how-to-align-drawn-text.md)  
 <span data-ttu-id="f9c6a-119">Показано, как для форматирования текста GDI + и GDI.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-119">Shows how to format GDI+ and GDI text.</span></span>  
  
 [<span data-ttu-id="f9c6a-120">Практическое руководство. Вывод текста по вертикали</span><span class="sxs-lookup"><span data-stu-id="f9c6a-120">How to: Create Vertical Text</span></span>](how-to-create-vertical-text.md)  
 <span data-ttu-id="f9c6a-121">Описывает способ рисования текста, выровненного по вертикали с помощью GDI +.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-121">Describes how to draw vertically aligned text with GDI+.</span></span>  
  
 [<span data-ttu-id="f9c6a-122">Практическое руководство. Установка позиций табуляции для выводимого текста</span><span class="sxs-lookup"><span data-stu-id="f9c6a-122">How to: Set Tab Stops in Drawn Text</span></span>](how-to-set-tab-stops-in-drawn-text.md)  
 <span data-ttu-id="f9c6a-123">Рисование текста с позициями табуляции с помощью GDI +.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-123">Shows how draw text with tab stops with GDI+.</span></span>  
  
 [<span data-ttu-id="f9c6a-124">Практическое руководство. Перебор установленных шрифтов</span><span class="sxs-lookup"><span data-stu-id="f9c6a-124">How to: Enumerate Installed Fonts</span></span>](how-to-enumerate-installed-fonts.md)  
 <span data-ttu-id="f9c6a-125">Объясняется, как список установленных шрифтов.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-125">Explains how to list the names of installed fonts.</span></span>  
  
 [<span data-ttu-id="f9c6a-126">Практическое руководство. Создание частной коллекции шрифтов</span><span class="sxs-lookup"><span data-stu-id="f9c6a-126">How to: Create a Private Font Collection</span></span>](how-to-create-a-private-font-collection.md)  
 <span data-ttu-id="f9c6a-127">Описывает создание <xref:System.Drawing.Text.PrivateFontCollection> объекта.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-127">Describes how to create a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 [<span data-ttu-id="f9c6a-128">Практическое руководство. Получение метрик шрифтов</span><span class="sxs-lookup"><span data-stu-id="f9c6a-128">How to: Obtain Font Metrics</span></span>](how-to-obtain-font-metrics.md)  
 <span data-ttu-id="f9c6a-129">Демонстрируется получение метрик шрифтов, такие как восхождение клетки и спуска.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-129">Shows how to obtain font metrics such as cell ascent and descent.</span></span>  
  
 [<span data-ttu-id="f9c6a-130">Практическое руководство. Сглаживание текста</span><span class="sxs-lookup"><span data-stu-id="f9c6a-130">How to: Use Antialiasing with Text</span></span>](how-to-use-antialiasing-with-text.md)  
 <span data-ttu-id="f9c6a-131">В данной статье описывается использование сглаживание при рисовании текста.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-131">Explains how to use antialiasing when drawing text.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f9c6a-132">Ссылка</span><span class="sxs-lookup"><span data-stu-id="f9c6a-132">Reference</span></span>  
 <xref:System.Drawing.Font>  
 <span data-ttu-id="f9c6a-133">Описывает данный класс и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-133">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.FontFamily>  
 <span data-ttu-id="f9c6a-134">Описывает данный класс и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-134">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 <span data-ttu-id="f9c6a-135">Описывает данный класс и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-135">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextRenderer>  
 <span data-ttu-id="f9c6a-136">Описывает данный класс и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-136">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 <span data-ttu-id="f9c6a-137">Описывает данный класс и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-137">Describes this class and contains links to all of its members.</span></span>
