---
title: Nothing и строки в Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d7693e712884a500495e4573900e7d9a049c2879
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="333d3-102">Nothing и строки в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="333d3-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="333d3-103">Среда выполнения Visual Basic и [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] оценки `Nothing` по-разному когда дело доходит до строки.</span><span class="sxs-lookup"><span data-stu-id="333d3-103">The Visual Basic runtime and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="333d3-104">Среда выполнения Visual Basic и .NET Framework</span><span class="sxs-lookup"><span data-stu-id="333d3-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="333d3-105">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="333d3-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]  
  
 <span data-ttu-id="333d3-106">Среда выполнения Visual Basic обычно расценивает `Nothing` как пустая строка (»»).</span><span class="sxs-lookup"><span data-stu-id="333d3-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="333d3-107">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] — Нет, однако и создается исключение при попытке выполнить операцию строки на `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="333d3-107">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="333d3-108">См. также</span><span class="sxs-lookup"><span data-stu-id="333d3-108">See Also</span></span>  
 [<span data-ttu-id="333d3-109">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="333d3-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
