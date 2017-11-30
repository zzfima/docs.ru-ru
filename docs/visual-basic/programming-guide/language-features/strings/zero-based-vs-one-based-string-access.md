---
title: "Отсчитываемый от нуля vs. Строка с индексацией доступ в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 911f063d6ca9a3f5d88a1f50d9df7f908a488f66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="0d5a4-102">Отсчитываемый от нуля vs. Строка с индексацией доступ в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0d5a4-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="0d5a4-103">В этом разделе сравнивается как [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] и [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] предоставляют доступ к символам в строке.</span><span class="sxs-lookup"><span data-stu-id="0d5a4-103">This topic compares how [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] provide access to the characters in a string.</span></span> <span data-ttu-id="0d5a4-104">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Всегда предоставляет отсчитываемый от нуля доступ к символам в строке, в то время как [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] предоставляет доступ, отсчитываемый от нуля и от единицы, в зависимости от функции.</span><span class="sxs-lookup"><span data-stu-id="0d5a4-104">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] always provides zero-based access to the characters in a string, whereas [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="0d5a4-105">Единицы</span><span class="sxs-lookup"><span data-stu-id="0d5a4-105">One-Based</span></span>  
 <span data-ttu-id="0d5a4-106">Пример с единицы [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] функция, рассмотрите возможность `Mid` функции.</span><span class="sxs-lookup"><span data-stu-id="0d5a4-106">For an example of a one-based [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] function, consider the `Mid` function.</span></span> <span data-ttu-id="0d5a4-107">Он принимает аргумент, указывающий положение символа, с которой начинается подстрока, начиная с позиции 1.</span><span class="sxs-lookup"><span data-stu-id="0d5a4-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="0d5a4-108">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> Принимает индекс символа в строке является подстрока для запуска, начиная с позиции 0.</span><span class="sxs-lookup"><span data-stu-id="0d5a4-108">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="0d5a4-109">Таким образом, если имеется строка «ABCDE» отдельные символы нумеруются 1,2,3,4,5 для использования с `Mid` функцию, но как 0,1,2,3,4 для использования с <xref:System.String.Substring%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="0d5a4-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="0d5a4-110">Отсчитываемый от нуля</span><span class="sxs-lookup"><span data-stu-id="0d5a4-110">Zero-Based</span></span>  
 <span data-ttu-id="0d5a4-111">Например, начинающийся с нуля [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] функция, рассмотрите возможность `Split` функции.</span><span class="sxs-lookup"><span data-stu-id="0d5a4-111">For an example of a zero-based [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] function, consider the `Split` function.</span></span> <span data-ttu-id="0d5a4-112">Он разбивает строку и возвращает массив, содержащий подстроки.</span><span class="sxs-lookup"><span data-stu-id="0d5a4-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="0d5a4-113">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> Метод также разбивает строку и возвращает массив, содержащий подстроки.</span><span class="sxs-lookup"><span data-stu-id="0d5a4-113">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="0d5a4-114">Поскольку `Split` функции и <xref:System.String.Split%2A> возвращении метода [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] массивы, они должны быть отсчитываемый от нуля.</span><span class="sxs-lookup"><span data-stu-id="0d5a4-114">Because the `Split` function and <xref:System.String.Split%2A> method return [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d5a4-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0d5a4-115">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 <xref:Microsoft.VisualBasic.Strings.Split%2A>  
 <xref:System.String.Substring%2A>  
 <xref:System.String.Split%2A>  
 [<span data-ttu-id="0d5a4-116">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0d5a4-116">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
