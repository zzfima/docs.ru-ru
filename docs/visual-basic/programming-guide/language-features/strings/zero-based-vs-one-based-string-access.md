---
title: Сравнение доступа к строкам, начинающимся с нуля
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: 97e60038bc7ec0f030939d0980b786bffebcfb9a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354291"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="67242-102">Что лучше: отсчет индексации с нуля или с единицы? (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67242-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="67242-103">В этом разделе сравнивается, как Visual Basic и .NET Framework предоставляют доступ к символам в строке.</span><span class="sxs-lookup"><span data-stu-id="67242-103">This topic compares how Visual Basic and the .NET Framework provide access to the characters in a string.</span></span> <span data-ttu-id="67242-104">.NET Framework всегда предоставляет доступ к символам в строке с нуля, тогда как Visual Basic предоставляет доступ с нуля и с одной стороны, в зависимости от функции.</span><span class="sxs-lookup"><span data-stu-id="67242-104">The .NET Framework always provides zero-based access to the characters in a string, whereas Visual Basic provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="67242-105">С учетом единицы</span><span class="sxs-lookup"><span data-stu-id="67242-105">One-Based</span></span>  
 <span data-ttu-id="67242-106">Пример одноVisual Basicной функции можно получить с помощью функции `Mid`.</span><span class="sxs-lookup"><span data-stu-id="67242-106">For an example of a one-based Visual Basic function, consider the `Mid` function.</span></span> <span data-ttu-id="67242-107">Он принимает аргумент, который указывает на позиции символа, с которого начнется подстрока, начиная с позиции 1.</span><span class="sxs-lookup"><span data-stu-id="67242-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="67242-108">Метод .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> принимает индекс символа в строке, с которой начинается подстрока, начиная с позиции 0.</span><span class="sxs-lookup"><span data-stu-id="67242-108">The .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="67242-109">Таким способом, если имеется строка «ABCD», то отдельные символы нумеруются 1, 2, 3, 4, 5 для использования с функцией `Mid`, но 0, 1, 2, 3, 4 для использования с методом <xref:System.String.Substring%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="67242-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="67242-110">С отсчетом от нуля</span><span class="sxs-lookup"><span data-stu-id="67242-110">Zero-Based</span></span>  
 <span data-ttu-id="67242-111">Пример функции Visual Basic, начинающейся с нуля, можно получить с помощью функции `Split`.</span><span class="sxs-lookup"><span data-stu-id="67242-111">For an example of a zero-based Visual Basic function, consider the `Split` function.</span></span> <span data-ttu-id="67242-112">Он разделяет строку и возвращает массив, содержащий подстроки.</span><span class="sxs-lookup"><span data-stu-id="67242-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="67242-113">Метод .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> также разделяет строку и возвращает массив, содержащий подстроки.</span><span class="sxs-lookup"><span data-stu-id="67242-113">The .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="67242-114">Поскольку функция `Split` и метод <xref:System.String.Split%2A> возвращают .NET Framework массивы, они должны относиться от нуля.</span><span class="sxs-lookup"><span data-stu-id="67242-114">Because the `Split` function and <xref:System.String.Split%2A> method return .NET Framework arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67242-115">См. также</span><span class="sxs-lookup"><span data-stu-id="67242-115">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [<span data-ttu-id="67242-116">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="67242-116">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
