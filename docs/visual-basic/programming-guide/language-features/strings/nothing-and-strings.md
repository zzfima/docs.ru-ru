---
title: Nothing и строки в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: 5fbcf86261892e3eb8e43ee8eaa3728cd8e42ced
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841892"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="774b2-102">Nothing и строки в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="774b2-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="774b2-103">Среда выполнения Visual Basic и [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] оценки `Nothing` по-разному когда доходит до строки.</span><span class="sxs-lookup"><span data-stu-id="774b2-103">The Visual Basic runtime and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="774b2-104">Среда выполнения Visual Basic и .NET Framework</span><span class="sxs-lookup"><span data-stu-id="774b2-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="774b2-105">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="774b2-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 <span data-ttu-id="774b2-106">Среда выполнения Visual Basic обычно оценивает `Nothing` как пустая строка (»»).</span><span class="sxs-lookup"><span data-stu-id="774b2-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="774b2-107">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] — Нет, тем не менее и создает исключение каждый раз, когда предпринята попытка выполнения операции строк на `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="774b2-107">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="774b2-108">См. также</span><span class="sxs-lookup"><span data-stu-id="774b2-108">See also</span></span>

- [<span data-ttu-id="774b2-109">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="774b2-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
