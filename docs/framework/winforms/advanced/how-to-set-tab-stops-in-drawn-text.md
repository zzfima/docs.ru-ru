---
title: Практическое руководство. Установка позиций табуляции для выводимого текста
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: 8821f6170b8ba588e3197ef54eab14c2719a6cc3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947821"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a><span data-ttu-id="d8037-102">Практическое руководство. Установка позиций табуляции для выводимого текста</span><span class="sxs-lookup"><span data-stu-id="d8037-102">How to: Set Tab Stops in Drawn Text</span></span>
<span data-ttu-id="d8037-103">Можно задать позиции табуляции для текста, вызвав <xref:System.Drawing.StringFormat.SetTabStops%2A> метод <xref:System.Drawing.StringFormat> объекта и <xref:System.Drawing.Graphics.DrawString%2A> передав этот <xref:System.Drawing.StringFormat> объект методу <xref:System.Drawing.Graphics> класса.</span><span class="sxs-lookup"><span data-stu-id="d8037-103">You can set tab stops for text by calling the <xref:System.Drawing.StringFormat.SetTabStops%2A> method of a <xref:System.Drawing.StringFormat> object and then passing that <xref:System.Drawing.StringFormat> object to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d8037-104">Не поддерживает добавление табуляции к рисуемому тексту, хотя существующие позиции табуляции можно развернуть <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> с помощью флага. <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d8037-104">The <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> does not support adding tab stops to drawn text, although you can expand existing tab stops using the <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> flag.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8037-105">Пример</span><span class="sxs-lookup"><span data-stu-id="d8037-105">Example</span></span>  
 <span data-ttu-id="d8037-106">В следующем примере задаются позиции табуляции в 150, 250 и 350.</span><span class="sxs-lookup"><span data-stu-id="d8037-106">The following example sets tab stops at 150, 250, and 350.</span></span> <span data-ttu-id="d8037-107">Затем в коде отображается список имен и оценок теста с вкладками.</span><span class="sxs-lookup"><span data-stu-id="d8037-107">Then, the code displays a tabbed list of names and test scores.</span></span>  
  
 <span data-ttu-id="d8037-108">На следующем рисунке показан текст с вкладками:</span><span class="sxs-lookup"><span data-stu-id="d8037-108">The following illustration shows the tabbed text:</span></span>  
  
 ![Снимок экрана, на котором показан список имен и оценок с вкладками.](./media/how-to-set-tab-stops-in-drawn-text/tab-list-names-test-scores.png)  
  
 <span data-ttu-id="d8037-110">Следующий код передает <xref:System.Drawing.StringFormat.SetTabStops%2A> методу два аргумента.</span><span class="sxs-lookup"><span data-stu-id="d8037-110">The following code passes two arguments to the <xref:System.Drawing.StringFormat.SetTabStops%2A> method.</span></span> <span data-ttu-id="d8037-111">Вторым аргументом является массив, содержащий смещения табуляции.</span><span class="sxs-lookup"><span data-stu-id="d8037-111">The second argument is an array that contains tab offsets.</span></span> <span data-ttu-id="d8037-112">Первый аргумент, передаваемый <xref:System.Drawing.StringFormat.SetTabStops%2A> в, равен 0, что означает, что первое смещение в массиве измеряется от позиции 0, левого края ограничивающего прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="d8037-112">The first argument passed to <xref:System.Drawing.StringFormat.SetTabStops%2A> is 0, which indicates that the first offset in the array is measured from position 0, the left edge of the bounding rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d8037-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="d8037-113">Compiling the Code</span></span>  
  
- <span data-ttu-id="d8037-114">Предыдущий пример предназначен для использования с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, <xref:System.Windows.Forms.PaintEventHandler>что является параметром.</span><span class="sxs-lookup"><span data-stu-id="d8037-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8037-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d8037-115">See also</span></span>

- [<span data-ttu-id="d8037-116">Работами со шрифтами и текстом</span><span class="sxs-lookup"><span data-stu-id="d8037-116">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="d8037-117">Практическое руководство. Рисование текста с помощью GDI</span><span class="sxs-lookup"><span data-stu-id="d8037-117">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
