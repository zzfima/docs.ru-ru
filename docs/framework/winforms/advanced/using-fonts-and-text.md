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
ms.openlocfilehash: d157b51e24009d847dede9ea6a9f81c8898c5b06
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526267"
---
# <a name="using-fonts-and-text"></a><span data-ttu-id="35b3c-102">Шрифты и текст</span><span class="sxs-lookup"><span data-stu-id="35b3c-102">Using Fonts and Text</span></span>
<span data-ttu-id="35b3c-103">Существует несколько классов, предоставляемых [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] и [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] для рисования текста в формах Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="35b3c-103">There are several classes offered by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] for drawing text on Windows Forms.</span></span> <span data-ttu-id="35b3c-104">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> Содержит несколько <xref:System.Drawing.Graphics.DrawString%2A> методы, которые позволяют указать различные свойства текста, такие как расположение, ограничивающий прямоугольник, шрифт и формат.</span><span class="sxs-lookup"><span data-stu-id="35b3c-104">The [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> class has several <xref:System.Drawing.Graphics.DrawString%2A> methods that allow you to specify various features of text, such as location, bounding rectangle, font, and format.</span></span> <span data-ttu-id="35b3c-105">Кроме того, можно нарисовать и измерить текста с [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] с помощью статического <xref:System.Windows.Forms.TextRenderer.DrawText%2A> и <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> методы, предоставляемые `TextRenderer` класса.</span><span class="sxs-lookup"><span data-stu-id="35b3c-105">In addition, you can draw and measure text with [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] using the static <xref:System.Windows.Forms.TextRenderer.DrawText%2A> and <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> methods offered by the `TextRenderer` class.</span></span> <span data-ttu-id="35b3c-106">[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Методы также позволяют указывать расположение, шрифт и формат.</span><span class="sxs-lookup"><span data-stu-id="35b3c-106">The [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] methods also allow you to specify location, font, and format.</span></span> <span data-ttu-id="35b3c-107">Вы также можете выбрать [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] или [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] для отрисовки текста; Однако [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] обычно предлагает более высокую производительность и более точного текста измерения.</span><span class="sxs-lookup"><span data-stu-id="35b3c-107">You can choose either [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] or [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] for text rendering; however, [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] generally offers better performance and more accurate text measuring.</span></span> <span data-ttu-id="35b3c-108">Включить других классов, предназначенных для отрисовки текста `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, и `TextFormatFlags`.</span><span class="sxs-lookup"><span data-stu-id="35b3c-108">Other classes that contribute to text rendering include `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, and `TextFormatFlags`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35b3c-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="35b3c-109">In This Section</span></span>  
 [<span data-ttu-id="35b3c-110">Практическое руководство. Разработка шрифтов и их семейств</span><span class="sxs-lookup"><span data-stu-id="35b3c-110">How to: Construct Font Families and Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 <span data-ttu-id="35b3c-111">Показано, как создать `Font` и `FontFamily` объектов.</span><span class="sxs-lookup"><span data-stu-id="35b3c-111">Shows how to create `Font` and `FontFamily` objects.</span></span>  
  
 [<span data-ttu-id="35b3c-112">Практическое руководство. Рисование текста в указанной позиции</span><span class="sxs-lookup"><span data-stu-id="35b3c-112">How to: Draw Text at a Specified Location</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)  
 <span data-ttu-id="35b3c-113">Рисование текста в нужном месте с помощью [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] и [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35b3c-113">Describes how to draw text in a certain location using [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 [<span data-ttu-id="35b3c-114">Практическое руководство. Многострочный вывод текста в прямоугольнике</span><span class="sxs-lookup"><span data-stu-id="35b3c-114">How to: Draw Wrapped Text in a Rectangle</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)  
 <span data-ttu-id="35b3c-115">Рисование текста в прямоугольнике с помощью [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] и [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35b3c-115">Explains how to draw text in a rectangle using [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 [<span data-ttu-id="35b3c-116">Практическое руководство. Рисование текста с использованием GDI</span><span class="sxs-lookup"><span data-stu-id="35b3c-116">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 <span data-ttu-id="35b3c-117">Демонстрируется использование [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] для рисования текста.</span><span class="sxs-lookup"><span data-stu-id="35b3c-117">Demonstrates how to use [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] for drawing text.</span></span>  
  
 [<span data-ttu-id="35b3c-118">Практическое руководство. Выравнивание рисуемого текста</span><span class="sxs-lookup"><span data-stu-id="35b3c-118">How to: Align Drawn Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-align-drawn-text.md)  
 <span data-ttu-id="35b3c-119">Форматирование [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] и [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] текста.</span><span class="sxs-lookup"><span data-stu-id="35b3c-119">Shows how to format [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] text.</span></span>  
  
 [<span data-ttu-id="35b3c-120">Практическое руководство. Вывод текста по вертикали</span><span class="sxs-lookup"><span data-stu-id="35b3c-120">How to: Create Vertical Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-vertical-text.md)  
 <span data-ttu-id="35b3c-121">Рисование текста, выровненного по вертикали с [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35b3c-121">Describes how to draw vertically aligned text with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
 [<span data-ttu-id="35b3c-122">Практическое руководство. Установка позиций табуляции для выводимого текста</span><span class="sxs-lookup"><span data-stu-id="35b3c-122">How to: Set Tab Stops in Drawn Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-set-tab-stops-in-drawn-text.md)  
 <span data-ttu-id="35b3c-123">Рисование текста с позициями табуляции с [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35b3c-123">Shows how draw text with tab stops with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
 [<span data-ttu-id="35b3c-124">Практическое руководство. Перебор установленных шрифтов</span><span class="sxs-lookup"><span data-stu-id="35b3c-124">How to: Enumerate Installed Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-enumerate-installed-fonts.md)  
 <span data-ttu-id="35b3c-125">Объясняется, как вывести список имен установленных шрифтов.</span><span class="sxs-lookup"><span data-stu-id="35b3c-125">Explains how to list the names of installed fonts.</span></span>  
  
 [<span data-ttu-id="35b3c-126">Практическое руководство. Создание частной коллекции шрифтов</span><span class="sxs-lookup"><span data-stu-id="35b3c-126">How to: Create a Private Font Collection</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-private-font-collection.md)  
 <span data-ttu-id="35b3c-127">Описывает способ создания <xref:System.Drawing.Text.PrivateFontCollection> объекта.</span><span class="sxs-lookup"><span data-stu-id="35b3c-127">Describes how to create a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 [<span data-ttu-id="35b3c-128">Практическое руководство. Получение метрик шрифтов</span><span class="sxs-lookup"><span data-stu-id="35b3c-128">How to: Obtain Font Metrics</span></span>](../../../../docs/framework/winforms/advanced/how-to-obtain-font-metrics.md)  
 <span data-ttu-id="35b3c-129">Показано, как получение метрик шрифтов, такие как Восхождение ячейки и спуск.</span><span class="sxs-lookup"><span data-stu-id="35b3c-129">Shows how to obtain font metrics such as cell ascent and descent.</span></span>  
  
 [<span data-ttu-id="35b3c-130">Практическое руководство. Сглаживание текста</span><span class="sxs-lookup"><span data-stu-id="35b3c-130">How to: Use Antialiasing with Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)  
 <span data-ttu-id="35b3c-131">Описание способов использования сглаживание при рисовании текста.</span><span class="sxs-lookup"><span data-stu-id="35b3c-131">Explains how to use antialiasing when drawing text.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="35b3c-132">Ссылка</span><span class="sxs-lookup"><span data-stu-id="35b3c-132">Reference</span></span>  
 <xref:System.Drawing.Font>  
 <span data-ttu-id="35b3c-133">Описывает данный класс и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="35b3c-133">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.FontFamily>  
 <span data-ttu-id="35b3c-134">Описывает данный класс и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="35b3c-134">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 <span data-ttu-id="35b3c-135">Описывает данный класс и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="35b3c-135">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextRenderer>  
 <span data-ttu-id="35b3c-136">Описывает данный класс и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="35b3c-136">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 <span data-ttu-id="35b3c-137">Описывает данный класс и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="35b3c-137">Describes this class and contains links to all of its members.</span></span>
