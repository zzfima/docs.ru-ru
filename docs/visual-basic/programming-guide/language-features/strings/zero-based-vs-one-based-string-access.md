---
title: 'Что лучше: отсчет строк с нуля или Доступ от единицы строки в Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: cc8f286de41d7e44225e889e73ff3c7b1fdbd881
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591745"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="2b2a1-102">Что лучше: отсчет строк с нуля или Доступ от единицы строки в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2b2a1-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="2b2a1-103">В этом разделе сравниваются, как Visual Basic и .NET Framework предоставляют доступ к символам в строке.</span><span class="sxs-lookup"><span data-stu-id="2b2a1-103">This topic compares how Visual Basic and the .NET Framework provide access to the characters in a string.</span></span> <span data-ttu-id="2b2a1-104">Платформа .NET Framework всегда предоставляет (с нуля) доступ к символов в строке, тогда как Visual Basic предоставляет доступ, отсчитываемый от нуля и от единицы, в зависимости от функции.</span><span class="sxs-lookup"><span data-stu-id="2b2a1-104">The .NET Framework always provides zero-based access to the characters in a string, whereas Visual Basic provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="2b2a1-105">От единицы</span><span class="sxs-lookup"><span data-stu-id="2b2a1-105">One-Based</span></span>  
 <span data-ttu-id="2b2a1-106">Пример функции Visual Basic от единицы, рассмотрите возможность `Mid` функции.</span><span class="sxs-lookup"><span data-stu-id="2b2a1-106">For an example of a one-based Visual Basic function, consider the `Mid` function.</span></span> <span data-ttu-id="2b2a1-107">Он принимает аргумент, указывающий позицию символа, с которой начинается подстрока, начиная с позиции 1.</span><span class="sxs-lookup"><span data-stu-id="2b2a1-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="2b2a1-108">.NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> принимает индекс символа в строке, по которому подстроки является запуск, начиная с позиции 0.</span><span class="sxs-lookup"><span data-stu-id="2b2a1-108">The .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="2b2a1-109">Таким образом, если имеется строка «ABCDE» отдельных символов, нумеруются 1,2,3,4,5 для использования с `Mid` функция, но как 0,1,2,3,4 для использования с <xref:System.String.Substring%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="2b2a1-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="2b2a1-110">Отсчитываемый от нуля</span><span class="sxs-lookup"><span data-stu-id="2b2a1-110">Zero-Based</span></span>  
 <span data-ttu-id="2b2a1-111">Пример функции Visual Basic (с нуля), рассмотрите возможность `Split` функции.</span><span class="sxs-lookup"><span data-stu-id="2b2a1-111">For an example of a zero-based Visual Basic function, consider the `Split` function.</span></span> <span data-ttu-id="2b2a1-112">Она разбивает строку и возвращает массив, содержащий подстроки.</span><span class="sxs-lookup"><span data-stu-id="2b2a1-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="2b2a1-113">.NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> метод также разбивает строку и возвращает массив, содержащий подстроки.</span><span class="sxs-lookup"><span data-stu-id="2b2a1-113">The .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="2b2a1-114">Так как `Split` функции и <xref:System.String.Split%2A> метод возвращать массивы .NET Framework, они должны быть отсчитываемый от нуля.</span><span class="sxs-lookup"><span data-stu-id="2b2a1-114">Because the `Split` function and <xref:System.String.Split%2A> method return .NET Framework arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b2a1-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2b2a1-115">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [<span data-ttu-id="2b2a1-116">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2b2a1-116">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
