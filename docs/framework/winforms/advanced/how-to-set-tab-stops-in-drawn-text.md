---
title: Как выполнить Установка позиций табуляции для выводимого текста
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: 4bf9328b63be88f487995f7b9691683167271c46
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54635810"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a><span data-ttu-id="56864-102">Как выполнить Установка позиций табуляции для выводимого текста</span><span class="sxs-lookup"><span data-stu-id="56864-102">How to: Set Tab Stops in Drawn Text</span></span>
<span data-ttu-id="56864-103">Позиции табуляции для текста можно задать путем вызова <xref:System.Drawing.StringFormat.SetTabStops%2A> метод <xref:System.Drawing.StringFormat> объекта и неудачами, <xref:System.Drawing.StringFormat> объект <xref:System.Drawing.Graphics.DrawString%2A> метод <xref:System.Drawing.Graphics> класса.</span><span class="sxs-lookup"><span data-stu-id="56864-103">You can set tab stops for text by calling the <xref:System.Drawing.StringFormat.SetTabStops%2A> method of a <xref:System.Drawing.StringFormat> object and then passing that <xref:System.Drawing.StringFormat> object to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56864-104"><xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> Делает, поддерживают добавление позиций табуляции для отображаемого текста, несмотря на то, что вы можете развернуть существующую вкладку перестает использовать <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> флаг.</span><span class="sxs-lookup"><span data-stu-id="56864-104">The <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> does not support adding tab stops to drawn text, although you can expand existing tab stops using the <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> flag.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56864-105">Пример</span><span class="sxs-lookup"><span data-stu-id="56864-105">Example</span></span>  
 <span data-ttu-id="56864-106">В следующем примере позициями табуляции в 150, 250 и 350.</span><span class="sxs-lookup"><span data-stu-id="56864-106">The following example sets tab stops at 150, 250, and 350.</span></span> <span data-ttu-id="56864-107">Затем код отображает список имен и результатов теста с вкладками.</span><span class="sxs-lookup"><span data-stu-id="56864-107">Then, the code displays a tabbed list of names and test scores.</span></span>  
  
 <span data-ttu-id="56864-108">На следующем рисунке текста.</span><span class="sxs-lookup"><span data-stu-id="56864-108">The following illustration shows the tabbed text.</span></span>  
  
 <span data-ttu-id="56864-109">![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")</span><span class="sxs-lookup"><span data-stu-id="56864-109">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")</span></span>  
  
 <span data-ttu-id="56864-110">Следующий код передаются два аргумента <xref:System.Drawing.StringFormat.SetTabStops%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="56864-110">The following code passes two arguments to the <xref:System.Drawing.StringFormat.SetTabStops%2A> method.</span></span> <span data-ttu-id="56864-111">Вторым аргументом является массив, содержащий смещения позиций табуляции.</span><span class="sxs-lookup"><span data-stu-id="56864-111">The second argument is an array that contains tab offsets.</span></span> <span data-ttu-id="56864-112">Первый аргумент, переданный <xref:System.Drawing.StringFormat.SetTabStops%2A> равно 0, это означает, что первое смещение в массиве измеряется начиная с позиции 0, левого края ограничивающего прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="56864-112">The first argument passed to <xref:System.Drawing.StringFormat.SetTabStops%2A> is 0, which indicates that the first offset in the array is measured from position 0, the left edge of the bounding rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="56864-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="56864-113">Compiling the Code</span></span>  
  
-   <span data-ttu-id="56864-114">Предыдущий пример кода предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="56864-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56864-115">См. также</span><span class="sxs-lookup"><span data-stu-id="56864-115">See also</span></span>
- [<span data-ttu-id="56864-116">Работами со шрифтами и текстом</span><span class="sxs-lookup"><span data-stu-id="56864-116">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
- [<span data-ttu-id="56864-117">Практическое руководство. Рисование текста с использованием GDI</span><span class="sxs-lookup"><span data-stu-id="56864-117">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
