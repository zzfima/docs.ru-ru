---
title: Nothing и строки в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: d03781209f0f9b021d540bd251c6c6025ad21422
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2018
ms.locfileid: "42754065"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="04147-102">Nothing и строки в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="04147-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="04147-103">Среда выполнения Visual Basic и [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] оценки `Nothing` по-разному когда доходит до строки.</span><span class="sxs-lookup"><span data-stu-id="04147-103">The Visual Basic runtime and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="04147-104">Среда выполнения Visual Basic и .NET Framework</span><span class="sxs-lookup"><span data-stu-id="04147-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="04147-105">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="04147-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]  
  
 <span data-ttu-id="04147-106">Среда выполнения Visual Basic обычно оценивает `Nothing` как пустая строка (»»).</span><span class="sxs-lookup"><span data-stu-id="04147-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="04147-107">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] — Нет, тем не менее и создает исключение каждый раз, когда предпринята попытка выполнения операции строк на `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="04147-107">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04147-108">См. также</span><span class="sxs-lookup"><span data-stu-id="04147-108">See Also</span></span>  
 [<span data-ttu-id="04147-109">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="04147-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
