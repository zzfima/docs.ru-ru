---
title: Nothing и строки в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: f5c1ea8cc0728b25e8e874963967aed504e466d7
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591342"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="02c18-102">Nothing и строки в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="02c18-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="02c18-103">Среда выполнения Visual Basic и .NET Framework оценить `Nothing` по-разному когда доходит до строки.</span><span class="sxs-lookup"><span data-stu-id="02c18-103">The Visual Basic runtime and the .NET Framework evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="02c18-104">Среда выполнения Visual Basic и .NET Framework</span><span class="sxs-lookup"><span data-stu-id="02c18-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="02c18-105">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="02c18-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 <span data-ttu-id="02c18-106">Среда выполнения Visual Basic обычно оценивает `Nothing` как пустая строка (»»).</span><span class="sxs-lookup"><span data-stu-id="02c18-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="02c18-107">.NET Framework — нет, тем не менее и создает исключение каждый раз, когда предпринята попытка выполнения операции строк на `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="02c18-107">The .NET Framework does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02c18-108">См. также</span><span class="sxs-lookup"><span data-stu-id="02c18-108">See also</span></span>

- [<span data-ttu-id="02c18-109">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="02c18-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
