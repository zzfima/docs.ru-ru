---
title: Практическое руководство. Разработка шрифтов и их семейств
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- font families [Windows Forms], constructing
- fonts [Windows Forms], constructing
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
ms.openlocfilehash: ceace5950ec135ea4d52081da7d1de7a820583ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-construct-font-families-and-fonts"></a><span data-ttu-id="916b8-102">Практическое руководство. Разработка шрифтов и их семейств</span><span class="sxs-lookup"><span data-stu-id="916b8-102">How to: Construct Font Families and Fonts</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="916b8-103"> шрифты с же гарнитуры, но разными стилями группируются в семейства шрифтов.</span><span class="sxs-lookup"><span data-stu-id="916b8-103"> groups fonts with the same typeface but different styles into font families.</span></span> <span data-ttu-id="916b8-104">Например семейство шрифтов Arial содержит следующие шрифты:</span><span class="sxs-lookup"><span data-stu-id="916b8-104">For example, the Arial font family contains the following fonts:</span></span>  
  
-   <span data-ttu-id="916b8-105">Arial обычного</span><span class="sxs-lookup"><span data-stu-id="916b8-105">Arial Regular</span></span>  
  
-   <span data-ttu-id="916b8-106">Arial полужирным шрифтом</span><span class="sxs-lookup"><span data-stu-id="916b8-106">Arial Bold</span></span>  
  
-   <span data-ttu-id="916b8-107">Arial курсив</span><span class="sxs-lookup"><span data-stu-id="916b8-107">Arial Italic</span></span>  
  
-   <span data-ttu-id="916b8-108">Arial полужирный курсив</span><span class="sxs-lookup"><span data-stu-id="916b8-108">Arial Bold Italic</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="916b8-109"> используются четыре стиля для формирования семейств шрифтов: обычный, полужирный, курсив и полужирный курсив.</span><span class="sxs-lookup"><span data-stu-id="916b8-109"> uses four styles to form families: regular, bold, italic, and bold italic.</span></span> <span data-ttu-id="916b8-110">Прилагательные, такие как *сузить* и *округленное* не считаются стили; они являются частями имен семейств шрифтов.</span><span class="sxs-lookup"><span data-stu-id="916b8-110">Adjectives such as *narrow* and *rounded* are not considered styles; rather they are part of the family name.</span></span> <span data-ttu-id="916b8-111">Например Arial Narrow — семейство шрифтов с следующие члены:</span><span class="sxs-lookup"><span data-stu-id="916b8-111">For example, Arial Narrow is a font family with the following members:</span></span>  
  
-   <span data-ttu-id="916b8-112">Arial обычного узкий</span><span class="sxs-lookup"><span data-stu-id="916b8-112">Arial Narrow Regular</span></span>  
  
-   <span data-ttu-id="916b8-113">Полужирным шрифтом Arial узкая</span><span class="sxs-lookup"><span data-stu-id="916b8-113">Arial Narrow Bold</span></span>  
  
-   <span data-ttu-id="916b8-114">Arial узких курсив</span><span class="sxs-lookup"><span data-stu-id="916b8-114">Arial Narrow Italic</span></span>  
  
-   <span data-ttu-id="916b8-115">Arial узких полужирный курсив</span><span class="sxs-lookup"><span data-stu-id="916b8-115">Arial Narrow Bold Italic</span></span>  
  
 <span data-ttu-id="916b8-116">Перед тем как выводить текст с [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], необходимо создать <xref:System.Drawing.FontFamily> объекта и <xref:System.Drawing.Font> объекта.</span><span class="sxs-lookup"><span data-stu-id="916b8-116">Before you can draw text with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you need to construct a <xref:System.Drawing.FontFamily> object and a <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="916b8-117"><xref:System.Drawing.FontFamily> Объекта определяет гарнитуру (например, Arial) и <xref:System.Drawing.Font> объект определяет размер, стиль и единицы измерения.</span><span class="sxs-lookup"><span data-stu-id="916b8-117">The <xref:System.Drawing.FontFamily> object specifies the typeface (for example, Arial), and the <xref:System.Drawing.Font> object specifies the size, style, and units.</span></span>  
  
## <a name="example"></a><span data-ttu-id="916b8-118">Пример</span><span class="sxs-lookup"><span data-stu-id="916b8-118">Example</span></span>  
 <span data-ttu-id="916b8-119">В следующем примере создается обычного стиля шрифта Arial с размером 16 пикселей.</span><span class="sxs-lookup"><span data-stu-id="916b8-119">The following example constructs a regular style Arial font with a size of 16 pixels.</span></span> <span data-ttu-id="916b8-120">В следующем коде первый аргумент, переданный <xref:System.Drawing.Font.%23ctor%2A> конструктор является <xref:System.Drawing.FontFamily> объекта.</span><span class="sxs-lookup"><span data-stu-id="916b8-120">In the following code, the first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the <xref:System.Drawing.FontFamily> object.</span></span> <span data-ttu-id="916b8-121">Второй аргумент задает размер шрифта, измеряется в единицах, которые идентифицируют четвертый аргумент.</span><span class="sxs-lookup"><span data-stu-id="916b8-121">The second argument specifies the size of the font measured in units identified by the fourth argument.</span></span> <span data-ttu-id="916b8-122">Третий параметр указывает стиль.</span><span class="sxs-lookup"><span data-stu-id="916b8-122">The third argument identifies the style.</span></span>  
  
 <span data-ttu-id="916b8-123"><xref:System.Drawing.GraphicsUnit.Pixel> является членом <xref:System.Drawing.GraphicsUnit> перечисления, и <xref:System.Drawing.FontStyle.Regular> является членом <xref:System.Drawing.FontStyle> перечисления.</span><span class="sxs-lookup"><span data-stu-id="916b8-123"><xref:System.Drawing.GraphicsUnit.Pixel> is a member of the <xref:System.Drawing.GraphicsUnit> enumeration, and <xref:System.Drawing.FontStyle.Regular> is a member of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="916b8-124">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="916b8-124">Compiling the Code</span></span>  
 <span data-ttu-id="916b8-125">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="916b8-125">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="916b8-126">См. также</span><span class="sxs-lookup"><span data-stu-id="916b8-126">See Also</span></span>  
 [<span data-ttu-id="916b8-127">Работами со шрифтами и текстом</span><span class="sxs-lookup"><span data-stu-id="916b8-127">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="916b8-128">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="916b8-128">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
