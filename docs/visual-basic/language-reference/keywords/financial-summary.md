---
title: "Сводка по финансовым функциям (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- financial functions
- payment
ms.assetid: 474f973e-7103-42b7-aa4d-367c935e07e1
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 47224a79942bd2b4adbe652f920be774e9f1c73d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="financial-summary-visual-basic"></a><span data-ttu-id="87bf5-102">Сводка по финансовым функциям (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="87bf5-102">Financial Summary (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="87bf5-103">ключевые слова языка и члены библиотек времени выполнения упорядочены по назначению и использованию.</span><span class="sxs-lookup"><span data-stu-id="87bf5-103"> language keywords and run-time library members are organized by purpose and use.</span></span>  
  
|<span data-ttu-id="87bf5-104">Действие</span><span class="sxs-lookup"><span data-stu-id="87bf5-104">Action</span></span>|<span data-ttu-id="87bf5-105">Элемент языка</span><span class="sxs-lookup"><span data-stu-id="87bf5-105">Language element</span></span>|  
|------------|----------------------|  
|<span data-ttu-id="87bf5-106">Расчета амортизации.</span><span class="sxs-lookup"><span data-stu-id="87bf5-106">Calculate depreciation.</span></span>|<span data-ttu-id="87bf5-107"><xref:Microsoft.VisualBasic.Financial.DDB%2A>, <xref:Microsoft.VisualBasic.Financial.SLN%2A>, <xref:Microsoft.VisualBasic.Financial.SYD%2A></xref:Microsoft.VisualBasic.Financial.SYD%2A></xref:Microsoft.VisualBasic.Financial.SLN%2A></xref:Microsoft.VisualBasic.Financial.DDB%2A></span><span class="sxs-lookup"><span data-stu-id="87bf5-107"><xref:Microsoft.VisualBasic.Financial.DDB%2A>, <xref:Microsoft.VisualBasic.Financial.SLN%2A>, <xref:Microsoft.VisualBasic.Financial.SYD%2A></span></span>|  
|<span data-ttu-id="87bf5-108">Вычисление будущей стоимости.</span><span class="sxs-lookup"><span data-stu-id="87bf5-108">Calculate future value.</span></span>|<span data-ttu-id="87bf5-109"><xref:Microsoft.VisualBasic.Financial.FV%2A></xref:Microsoft.VisualBasic.Financial.FV%2A></span><span class="sxs-lookup"><span data-stu-id="87bf5-109"><xref:Microsoft.VisualBasic.Financial.FV%2A></span></span>|  
|<span data-ttu-id="87bf5-110">Вычисление процентной ставки.</span><span class="sxs-lookup"><span data-stu-id="87bf5-110">Calculate interest rate.</span></span>|<span data-ttu-id="87bf5-111"><xref:Microsoft.VisualBasic.Financial.Rate%2A></xref:Microsoft.VisualBasic.Financial.Rate%2A></span><span class="sxs-lookup"><span data-stu-id="87bf5-111"><xref:Microsoft.VisualBasic.Financial.Rate%2A></span></span>|  
|<span data-ttu-id="87bf5-112">Вычисляет внутреннюю норму прибыли.</span><span class="sxs-lookup"><span data-stu-id="87bf5-112">Calculate internal rate of return.</span></span>|<span data-ttu-id="87bf5-113"><xref:Microsoft.VisualBasic.Financial.IRR%2A>,<xref:Microsoft.VisualBasic.Financial.MIRR%2A></xref:Microsoft.VisualBasic.Financial.MIRR%2A></xref:Microsoft.VisualBasic.Financial.IRR%2A></span><span class="sxs-lookup"><span data-stu-id="87bf5-113"><xref:Microsoft.VisualBasic.Financial.IRR%2A>, <xref:Microsoft.VisualBasic.Financial.MIRR%2A></span></span>|  
|<span data-ttu-id="87bf5-114">Вычисление количества периодов.</span><span class="sxs-lookup"><span data-stu-id="87bf5-114">Calculate number of periods.</span></span>|<span data-ttu-id="87bf5-115"><xref:Microsoft.VisualBasic.Financial.NPer%2A></xref:Microsoft.VisualBasic.Financial.NPer%2A></span><span class="sxs-lookup"><span data-stu-id="87bf5-115"><xref:Microsoft.VisualBasic.Financial.NPer%2A></span></span>|  
|<span data-ttu-id="87bf5-116">Вычисление платежей.</span><span class="sxs-lookup"><span data-stu-id="87bf5-116">Calculate payments.</span></span>|<span data-ttu-id="87bf5-117"><xref:Microsoft.VisualBasic.Financial.IPmt%2A>, <xref:Microsoft.VisualBasic.Financial.Pmt%2A>, <xref:Microsoft.VisualBasic.Financial.PPmt%2A></xref:Microsoft.VisualBasic.Financial.PPmt%2A></xref:Microsoft.VisualBasic.Financial.Pmt%2A></xref:Microsoft.VisualBasic.Financial.IPmt%2A></span><span class="sxs-lookup"><span data-stu-id="87bf5-117"><xref:Microsoft.VisualBasic.Financial.IPmt%2A>, <xref:Microsoft.VisualBasic.Financial.Pmt%2A>, <xref:Microsoft.VisualBasic.Financial.PPmt%2A></span></span>|  
|<span data-ttu-id="87bf5-118">Вычисление текущей стоимости.</span><span class="sxs-lookup"><span data-stu-id="87bf5-118">Calculate present value.</span></span>|<span data-ttu-id="87bf5-119"><xref:Microsoft.VisualBasic.Financial.NPV%2A>,<xref:Microsoft.VisualBasic.Financial.PV%2A></xref:Microsoft.VisualBasic.Financial.PV%2A></xref:Microsoft.VisualBasic.Financial.NPV%2A></span><span class="sxs-lookup"><span data-stu-id="87bf5-119"><xref:Microsoft.VisualBasic.Financial.NPV%2A>, <xref:Microsoft.VisualBasic.Financial.PV%2A></span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87bf5-120">См. также</span><span class="sxs-lookup"><span data-stu-id="87bf5-120">See Also</span></span>  
 <span data-ttu-id="87bf5-121">[Ключевые слова](../../../visual-basic/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="87bf5-121">[Keywords](../../../visual-basic/language-reference/keywords/index.md) </span></span>  
<span data-ttu-id="87bf5-122"> [Члены библиотеки времени выполнения Visual Basic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="87bf5-122"> [Visual Basic Runtime Library Members](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>
