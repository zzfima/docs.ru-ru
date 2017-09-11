---
title: "Отсчитываемый от нуля vs. Доступ на основе одной строки в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
caps.latest.revision: 11
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
ms.openlocfilehash: d8d1000f134fa8f99509d12727b9fbd84cb0e831
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="800fb-102">Отсчитываемый от нуля vs. Доступ на основе одной строки в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="800fb-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="800fb-103">В этом разделе сравнивается как [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] и [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] предоставляют доступ к символам в строке.</span><span class="sxs-lookup"><span data-stu-id="800fb-103">This topic compares how [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] and the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] provide access to the characters in a string.</span></span> <span data-ttu-id="800fb-104">[!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] Всегда обеспечивает (с нуля) доступ к символам в строке, в то время как [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] предоставляет доступ, отсчитываемый от нуля и от единицы, в зависимости от функции.</span><span class="sxs-lookup"><span data-stu-id="800fb-104">The [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] always provides zero-based access to the characters in a string, whereas [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="800fb-105">Единицы</span><span class="sxs-lookup"><span data-stu-id="800fb-105">One-Based</span></span>  
 <span data-ttu-id="800fb-106">Пример с единицы [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] функция, рассмотрите возможность `Mid` функции.</span><span class="sxs-lookup"><span data-stu-id="800fb-106">For an example of a one-based [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] function, consider the `Mid` function.</span></span> <span data-ttu-id="800fb-107">Он принимает аргумент, указывающий положение символа, с которой начинается подстрока, начиная с позиции 1.</span><span class="sxs-lookup"><span data-stu-id="800fb-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="800fb-108">[!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Substring%2A?displayProperty=fullName>Принимает индекс символа в строке является подстрока для запуска, начиная с позиции 0.</xref:System.String.Substring%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="800fb-108">The [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Substring%2A?displayProperty=fullName> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="800fb-109">Таким образом, если имеется строка «ABCDE» отдельные символы нумеруются как 1,2,3,4,5 для использования с `Mid` функции, но как 0,1,2,3,4 для использования с <xref:System.String.Substring%2A?displayProperty=fullName>метод.</xref:System.String.Substring%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="800fb-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=fullName> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="800fb-110">Отсчитываемый от нуля</span><span class="sxs-lookup"><span data-stu-id="800fb-110">Zero-Based</span></span>  
 <span data-ttu-id="800fb-111">Пример (с нуля) [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] функция, рассмотрите возможность `Split` функции.</span><span class="sxs-lookup"><span data-stu-id="800fb-111">For an example of a zero-based [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] function, consider the `Split` function.</span></span> <span data-ttu-id="800fb-112">Он разбивает строку и возвращает массив, содержащий подстроки.</span><span class="sxs-lookup"><span data-stu-id="800fb-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="800fb-113">[!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Split%2A?displayProperty=fullName>Также метод разбивает строку и возвращает массив, содержащий подстроки.</xref:System.String.Split%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="800fb-113">The [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Split%2A?displayProperty=fullName> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="800fb-114">Поскольку `Split` функции и <xref:System.String.Split%2A>возвращении метода [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] массивы, они должны быть от нуля.</xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="800fb-114">Because the `Split` function and <xref:System.String.Split%2A> method return [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="800fb-115">См. также</span><span class="sxs-lookup"><span data-stu-id="800fb-115">See Also</span></span>  
 <span data-ttu-id="800fb-116"><xref:Microsoft.VisualBasic.Strings.Mid%2A></xref:Microsoft.VisualBasic.Strings.Mid%2A></span><span class="sxs-lookup"><span data-stu-id="800fb-116"><xref:Microsoft.VisualBasic.Strings.Mid%2A></span></span>   
 <span data-ttu-id="800fb-117"><xref:Microsoft.VisualBasic.Strings.Split%2A></xref:Microsoft.VisualBasic.Strings.Split%2A></span><span class="sxs-lookup"><span data-stu-id="800fb-117"><xref:Microsoft.VisualBasic.Strings.Split%2A></span></span>   
 <span data-ttu-id="800fb-118"><xref:System.String.Substring%2A></xref:System.String.Substring%2A></span><span class="sxs-lookup"><span data-stu-id="800fb-118"><xref:System.String.Substring%2A></span></span>   
 <span data-ttu-id="800fb-119"><xref:System.String.Split%2A></xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="800fb-119"><xref:System.String.Split%2A></span></span>   
<span data-ttu-id="800fb-120"> [Знакомство со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)</span><span class="sxs-lookup"><span data-stu-id="800fb-120"> [Introduction to Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)</span></span>
