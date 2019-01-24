---
title: Как выполнить Шрифты и их семейств
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- font families [Windows Forms], constructing
- fonts [Windows Forms], constructing
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
ms.openlocfilehash: 6f939ab90252697d09d594e4d9300ec101c8f2e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540680"
---
# <a name="how-to-construct-font-families-and-fonts"></a><span data-ttu-id="16f39-102">Как выполнить Шрифты и их семейств</span><span class="sxs-lookup"><span data-stu-id="16f39-102">How to: Construct Font Families and Fonts</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="16f39-103">Группирует шрифты с тем же шрифт, но различные стили в семейства шрифтов.</span><span class="sxs-lookup"><span data-stu-id="16f39-103">groups fonts with the same typeface but different styles into font families.</span></span> <span data-ttu-id="16f39-104">Например семейство шрифтов Arial содержит следующие шрифты:</span><span class="sxs-lookup"><span data-stu-id="16f39-104">For example, the Arial font family contains the following fonts:</span></span>  
  
-   <span data-ttu-id="16f39-105">Arial обычного</span><span class="sxs-lookup"><span data-stu-id="16f39-105">Arial Regular</span></span>  
  
-   <span data-ttu-id="16f39-106">Arial полужирным шрифтом</span><span class="sxs-lookup"><span data-stu-id="16f39-106">Arial Bold</span></span>  
  
-   <span data-ttu-id="16f39-107">Arial курсив</span><span class="sxs-lookup"><span data-stu-id="16f39-107">Arial Italic</span></span>  
  
-   <span data-ttu-id="16f39-108">Arial полужирный курсив</span><span class="sxs-lookup"><span data-stu-id="16f39-108">Arial Bold Italic</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="16f39-109">используются четыре стиля для формирования семейств шрифтов: обычный, полужирный, курсив и полужирный курсив.</span><span class="sxs-lookup"><span data-stu-id="16f39-109">uses four styles to form families: regular, bold, italic, and bold italic.</span></span> <span data-ttu-id="16f39-110">Прилагательные, такие как *сузить* и *округленное* не учитываются стили; вместо этого они являются частью имя семейства.</span><span class="sxs-lookup"><span data-stu-id="16f39-110">Adjectives such as *narrow* and *rounded* are not considered styles; rather they are part of the family name.</span></span> <span data-ttu-id="16f39-111">Например Arial Narrow является семейством шрифтов со следующими членами:</span><span class="sxs-lookup"><span data-stu-id="16f39-111">For example, Arial Narrow is a font family with the following members:</span></span>  
  
-   <span data-ttu-id="16f39-112">Arial обычного узкий</span><span class="sxs-lookup"><span data-stu-id="16f39-112">Arial Narrow Regular</span></span>  
  
-   <span data-ttu-id="16f39-113">Полужирным шрифтом Arial узкая</span><span class="sxs-lookup"><span data-stu-id="16f39-113">Arial Narrow Bold</span></span>  
  
-   <span data-ttu-id="16f39-114">Arial узкий курсив</span><span class="sxs-lookup"><span data-stu-id="16f39-114">Arial Narrow Italic</span></span>  
  
-   <span data-ttu-id="16f39-115">Arial узкий полужирный курсив</span><span class="sxs-lookup"><span data-stu-id="16f39-115">Arial Narrow Bold Italic</span></span>  
  
 <span data-ttu-id="16f39-116">Прежде чем можно рисовать текст с [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], необходимо создать <xref:System.Drawing.FontFamily> объекта и <xref:System.Drawing.Font> объекта.</span><span class="sxs-lookup"><span data-stu-id="16f39-116">Before you can draw text with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you need to construct a <xref:System.Drawing.FontFamily> object and a <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="16f39-117"><xref:System.Drawing.FontFamily> Объект определяет гарнитуру (например, Arial) и <xref:System.Drawing.Font> объект определяет размер, стиль и единиц.</span><span class="sxs-lookup"><span data-stu-id="16f39-117">The <xref:System.Drawing.FontFamily> object specifies the typeface (for example, Arial), and the <xref:System.Drawing.Font> object specifies the size, style, and units.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16f39-118">Пример</span><span class="sxs-lookup"><span data-stu-id="16f39-118">Example</span></span>  
 <span data-ttu-id="16f39-119">В следующем примере создается обычного начертания шрифта Arial с размером 16 пикселей.</span><span class="sxs-lookup"><span data-stu-id="16f39-119">The following example constructs a regular style Arial font with a size of 16 pixels.</span></span> <span data-ttu-id="16f39-120">В следующем коде, первый аргумент, переданный <xref:System.Drawing.Font.%23ctor%2A> конструктор является <xref:System.Drawing.FontFamily> объекта.</span><span class="sxs-lookup"><span data-stu-id="16f39-120">In the following code, the first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the <xref:System.Drawing.FontFamily> object.</span></span> <span data-ttu-id="16f39-121">Второй аргумент задает размер шрифта, измеряемая в единицах, идентифицируемый четвертый аргумент.</span><span class="sxs-lookup"><span data-stu-id="16f39-121">The second argument specifies the size of the font measured in units identified by the fourth argument.</span></span> <span data-ttu-id="16f39-122">Третий параметр указывает стиль.</span><span class="sxs-lookup"><span data-stu-id="16f39-122">The third argument identifies the style.</span></span>  
  
 <span data-ttu-id="16f39-123"><xref:System.Drawing.GraphicsUnit.Pixel> является членом <xref:System.Drawing.GraphicsUnit> перечисления, и <xref:System.Drawing.FontStyle.Regular> является членом <xref:System.Drawing.FontStyle> перечисления.</span><span class="sxs-lookup"><span data-stu-id="16f39-123"><xref:System.Drawing.GraphicsUnit.Pixel> is a member of the <xref:System.Drawing.GraphicsUnit> enumeration, and <xref:System.Drawing.FontStyle.Regular> is a member of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="16f39-124">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="16f39-124">Compiling the Code</span></span>  
 <span data-ttu-id="16f39-125">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="16f39-125">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16f39-126">См. также</span><span class="sxs-lookup"><span data-stu-id="16f39-126">See also</span></span>
- [<span data-ttu-id="16f39-127">Работами со шрифтами и текстом</span><span class="sxs-lookup"><span data-stu-id="16f39-127">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
- [<span data-ttu-id="16f39-128">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="16f39-128">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
