---
title: Практическое руководство. Использование проверки попадания с регионом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: a9435724e7674fd196ad70bdfd0ab43808a53058
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709757"
---
# <a name="how-to-use-hit-testing-with-a-region"></a><span data-ttu-id="f558b-102">Практическое руководство. Использование проверки попадания с регионом</span><span class="sxs-lookup"><span data-stu-id="f558b-102">How to: Use Hit Testing with a Region</span></span>
<span data-ttu-id="f558b-103">Проверка попадания предназначена для определения, находится ли курсор над данным объектом, например значок или кнопки.</span><span class="sxs-lookup"><span data-stu-id="f558b-103">The purpose of hit testing is to determine whether the cursor is over a given object, such as an icon or a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f558b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="f558b-104">Example</span></span>  
 <span data-ttu-id="f558b-105">В следующем примере создается область креста, являющаяся объединением двух прямоугольников.</span><span class="sxs-lookup"><span data-stu-id="f558b-105">The following example creates a plus-shaped region by forming the union of two rectangular regions.</span></span> <span data-ttu-id="f558b-106">Предполагается, что переменная `point` содержит расположение последнего щелчка.</span><span class="sxs-lookup"><span data-stu-id="f558b-106">Assume that the variable `point` holds the location of the most recent click.</span></span> <span data-ttu-id="f558b-107">Код проверяет, является ли `point` находится в регионе креста.</span><span class="sxs-lookup"><span data-stu-id="f558b-107">The code checks to see whether `point` is in the plus-shaped region.</span></span> <span data-ttu-id="f558b-108">Если точка находится в регионе (нажатия), область заполняется непрозрачной красной кистью.</span><span class="sxs-lookup"><span data-stu-id="f558b-108">If the point is in the region (a hit), the region is filled with an opaque red brush.</span></span> <span data-ttu-id="f558b-109">В противном случае область заполняется полупрозрачные компоненты Красная кисть.</span><span class="sxs-lookup"><span data-stu-id="f558b-109">Otherwise, the region is filled with a semitransparent red brush.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f558b-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f558b-110">Compiling the Code</span></span>  
 <span data-ttu-id="f558b-111">Предыдущий пример кода предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="f558b-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f558b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f558b-112">See also</span></span>
- <xref:System.Drawing.Region>
- [<span data-ttu-id="f558b-113">Области в GDI+</span><span class="sxs-lookup"><span data-stu-id="f558b-113">Regions in GDI+</span></span>](regions-in-gdi.md)
- [<span data-ttu-id="f558b-114">Практическое руководство. Используйте задание области отсечения</span><span class="sxs-lookup"><span data-stu-id="f558b-114">How to: Use Clipping with a Region</span></span>](how-to-use-clipping-with-a-region.md)
