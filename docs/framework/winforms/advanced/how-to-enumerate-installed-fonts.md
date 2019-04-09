---
title: Практическое руководство. Перебор установленных шрифтов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
ms.openlocfilehash: 92f27399cce9e03a4679c8a34fbdafcf28c32252
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155016"
---
# <a name="how-to-enumerate-installed-fonts"></a><span data-ttu-id="83593-102">Практическое руководство. Перебор установленных шрифтов</span><span class="sxs-lookup"><span data-stu-id="83593-102">How to: Enumerate Installed Fonts</span></span>
<span data-ttu-id="83593-103"><xref:System.Drawing.Text.InstalledFontCollection> Класс наследует от <xref:System.Drawing.Text.FontCollection> абстрактного базового класса.</span><span class="sxs-lookup"><span data-stu-id="83593-103">The <xref:System.Drawing.Text.InstalledFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="83593-104">Можно использовать <xref:System.Drawing.Text.InstalledFontCollection> объект для перечисления шрифтов, установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="83593-104">You can use an <xref:System.Drawing.Text.InstalledFontCollection> object to enumerate the fonts installed on the computer.</span></span> <span data-ttu-id="83593-105"><xref:System.Drawing.Text.FontCollection.Families%2A> Свойство <xref:System.Drawing.Text.InstalledFontCollection> объект представляет собой массив <xref:System.Drawing.FontFamily> объектов.</span><span class="sxs-lookup"><span data-stu-id="83593-105">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of an <xref:System.Drawing.Text.InstalledFontCollection> object is an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83593-106">Пример</span><span class="sxs-lookup"><span data-stu-id="83593-106">Example</span></span>  
 <span data-ttu-id="83593-107">Приведенный ниже список имен семейств шрифтов, установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="83593-107">The following example lists the names of all the font families installed on the computer.</span></span> <span data-ttu-id="83593-108">Код получает <xref:System.Drawing.FontFamily.Name%2A> свойства каждого <xref:System.Drawing.FontFamily> объекта в массиве, возвращенном <xref:System.Drawing.Text.FontCollection.Families%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="83593-108">The code retrieves the <xref:System.Drawing.FontFamily.Name%2A> property of each <xref:System.Drawing.FontFamily> object in the array returned by the <xref:System.Drawing.Text.FontCollection.Families%2A> property.</span></span> <span data-ttu-id="83593-109">По мере извлечения имен семейств, они объединяются в форме, разделенный запятыми список.</span><span class="sxs-lookup"><span data-stu-id="83593-109">As the family names are retrieved, they are concatenated to form a comma-separated list.</span></span> <span data-ttu-id="83593-110">Затем <xref:System.Drawing.Graphics.DrawString%2A> метод <xref:System.Drawing.Graphics> класс создает список с разделителями запятыми в прямоугольнике.</span><span class="sxs-lookup"><span data-stu-id="83593-110">Then the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class draws the comma-separated list in a rectangle.</span></span>  
  
 <span data-ttu-id="83593-111">Если запустить пример кода, выходные данные будут, как показано на следующем рисунке:</span><span class="sxs-lookup"><span data-stu-id="83593-111">If you run the example code, the output will be similar to that shown in the following illustration:</span></span>  
  
 ![Снимок экрана, показывающий гарнитуры.](./media/how-to-enumerate-installed-fonts/list-installed-font-families.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="83593-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="83593-113">Compiling the Code</span></span>  
 <span data-ttu-id="83593-114">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="83593-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span> <span data-ttu-id="83593-115">Кроме того, следует импортировать <xref:System.Drawing.Text> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="83593-115">In addition, you should import the <xref:System.Drawing.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83593-116">См. также</span><span class="sxs-lookup"><span data-stu-id="83593-116">See also</span></span>

- [<span data-ttu-id="83593-117">Шрифты и текст</span><span class="sxs-lookup"><span data-stu-id="83593-117">Using Fonts and Text</span></span>](using-fonts-and-text.md)
