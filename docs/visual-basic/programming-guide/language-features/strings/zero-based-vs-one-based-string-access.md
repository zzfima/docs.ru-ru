---
title: 'Что лучше: отсчет строк с нуля или Доступ от единицы строки в Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: a6ceb10d4a3cb9463551d8c85375ddbbb607ffdc
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830335"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="7e177-102">Что лучше: отсчет строк с нуля или Доступ от единицы строки в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7e177-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="7e177-103">В этом разделе сравнивается как Visual Basic и [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] предоставляют доступ к символам в строке.</span><span class="sxs-lookup"><span data-stu-id="7e177-103">This topic compares how Visual Basic and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] provide access to the characters in a string.</span></span> <span data-ttu-id="7e177-104">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Всегда обеспечивает (с нуля) доступ к символам в строке, тогда как Visual Basic предоставляет доступ, отсчитываемый от нуля и от единицы, в зависимости от функции.</span><span class="sxs-lookup"><span data-stu-id="7e177-104">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] always provides zero-based access to the characters in a string, whereas Visual Basic provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="7e177-105">От единицы</span><span class="sxs-lookup"><span data-stu-id="7e177-105">One-Based</span></span>  
 <span data-ttu-id="7e177-106">Пример функции Visual Basic от единицы, рассмотрите возможность `Mid` функции.</span><span class="sxs-lookup"><span data-stu-id="7e177-106">For an example of a one-based Visual Basic function, consider the `Mid` function.</span></span> <span data-ttu-id="7e177-107">Он принимает аргумент, указывающий позицию символа, с которой начинается подстрока, начиная с позиции 1.</span><span class="sxs-lookup"><span data-stu-id="7e177-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="7e177-108">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> Принимает индекс символа в строке, по которому подстроки является запуск, начиная с позиции 0.</span><span class="sxs-lookup"><span data-stu-id="7e177-108">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="7e177-109">Таким образом, если имеется строка «ABCDE» отдельных символов, нумеруются 1,2,3,4,5 для использования с `Mid` функция, но как 0,1,2,3,4 для использования с <xref:System.String.Substring%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="7e177-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="7e177-110">Отсчитываемый от нуля</span><span class="sxs-lookup"><span data-stu-id="7e177-110">Zero-Based</span></span>  
 <span data-ttu-id="7e177-111">Пример функции Visual Basic (с нуля), рассмотрите возможность `Split` функции.</span><span class="sxs-lookup"><span data-stu-id="7e177-111">For an example of a zero-based Visual Basic function, consider the `Split` function.</span></span> <span data-ttu-id="7e177-112">Она разбивает строку и возвращает массив, содержащий подстроки.</span><span class="sxs-lookup"><span data-stu-id="7e177-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="7e177-113">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> Метод также разбивает строку и возвращает массив, содержащий подстроки.</span><span class="sxs-lookup"><span data-stu-id="7e177-113">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="7e177-114">Так как `Split` функции и <xref:System.String.Split%2A> метод возвращает [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] массивы, они должны быть отсчитываемый от нуля.</span><span class="sxs-lookup"><span data-stu-id="7e177-114">Because the `Split` function and <xref:System.String.Split%2A> method return [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e177-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7e177-115">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [<span data-ttu-id="7e177-116">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7e177-116">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
