---
title: Практическое руководство. Поиск в строке (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: b690aa78a2cf07b0db5bdd28d7d71ed4a79fbf61
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58823302"
---
# <a name="how-to-search-within-a-string-visual-basic"></a><span data-ttu-id="cc5ba-102">Практическое руководство. Поиск в строке (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc5ba-102">How to: Search Within a String (Visual Basic)</span></span>
<span data-ttu-id="cc5ba-103">В этом примере вызывается <xref:System.String.IndexOf%2A> метод <xref:System.String> объекта для отображения индекса первого вхождения подстроки.</span><span class="sxs-lookup"><span data-stu-id="cc5ba-103">This example calls the <xref:System.String.IndexOf%2A> method on a <xref:System.String> object to report the index of the first occurrence of a substring.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc5ba-104">Пример</span><span class="sxs-lookup"><span data-stu-id="cc5ba-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cc5ba-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="cc5ba-105">Compiling the Code</span></span>  
 <span data-ttu-id="cc5ba-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="cc5ba-106">This example requires:</span></span>  
  
-   <span data-ttu-id="cc5ba-107">`Imports` Инструкция <xref:System> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="cc5ba-107">An `Imports` statement specifying the <xref:System> namespace.</span></span> <span data-ttu-id="cc5ba-108">Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="cc5ba-108">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="cc5ba-109">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="cc5ba-109">Robust Programming</span></span>  
 <span data-ttu-id="cc5ba-110"><xref:System.String.IndexOf%2A> Метод сообщает расположение первого символа первого вхождения подстроки.</span><span class="sxs-lookup"><span data-stu-id="cc5ba-110">The <xref:System.String.IndexOf%2A> method reports the location of the first character of the first occurrence of the substring.</span></span> <span data-ttu-id="cc5ba-111">Индекс отсчитывается от 0, это означает, что первый символ строки имеет индекс 0.</span><span class="sxs-lookup"><span data-stu-id="cc5ba-111">The index is 0-based, which means the first character of a string has an index of 0.</span></span>  
  
 <span data-ttu-id="cc5ba-112">Если <xref:System.String.IndexOf%2A> не удается найти подстроку, возвращается значение -1.</span><span class="sxs-lookup"><span data-stu-id="cc5ba-112">If <xref:System.String.IndexOf%2A> does not find the substring, it returns -1.</span></span>  
  
 <span data-ttu-id="cc5ba-113"><xref:System.String.IndexOf%2A> Метод учитывает регистр и использует текущего языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="cc5ba-113">The <xref:System.String.IndexOf%2A> method is case-sensitive and uses the current culture.</span></span>  
  
 <span data-ttu-id="cc5ba-114">Для лучшей защиты от ошибок может потребоваться заключить строку поиска в `Try` блока [попробуйте... CATCH... Оператор Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) конструкции.</span><span class="sxs-lookup"><span data-stu-id="cc5ba-114">For optimal error control, you might want to enclose the string search in the `Try` block of a [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) construction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc5ba-115">См. также</span><span class="sxs-lookup"><span data-stu-id="cc5ba-115">See also</span></span>

- <xref:System.String.IndexOf%2A>
- [<span data-ttu-id="cc5ba-116">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="cc5ba-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="cc5ba-117">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cc5ba-117">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
- [<span data-ttu-id="cc5ba-118">Строки</span><span class="sxs-lookup"><span data-stu-id="cc5ba-118">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
