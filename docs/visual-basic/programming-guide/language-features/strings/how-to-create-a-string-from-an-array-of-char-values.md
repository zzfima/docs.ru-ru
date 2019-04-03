---
title: Практическое руководство. Создать строку из массива значений типа Char (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 1f72cb86ffa38dc929062fab2f5592a781f2de27
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831830"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="49cc9-102">Практическое руководство. Создать строку из массива значений типа Char (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49cc9-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="49cc9-103">Этот пример создает строки «abcd» из отдельных символов.</span><span class="sxs-lookup"><span data-stu-id="49cc9-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49cc9-104">Пример</span><span class="sxs-lookup"><span data-stu-id="49cc9-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="49cc9-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="49cc9-105">Compiling the Code</span></span>  
 <span data-ttu-id="49cc9-106">Этот метод не имеет специальных требований.</span><span class="sxs-lookup"><span data-stu-id="49cc9-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="49cc9-107">Синтаксис `"a"c`, когда одному `c` соответствует отдельный символ в кавычки, используется для создания символьного литерала.</span><span class="sxs-lookup"><span data-stu-id="49cc9-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="49cc9-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="49cc9-108">Robust Programming</span></span>  
 <span data-ttu-id="49cc9-109">Символы NULL (эквивалентно `Chr(0)`) в строке могут привести к непредвиденным результатам при использовании этой строки.</span><span class="sxs-lookup"><span data-stu-id="49cc9-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="49cc9-110">Нуль-символ будет включен в строку, но символы, следующие нуль-символ будет отображаться в некоторых ситуациях.</span><span class="sxs-lookup"><span data-stu-id="49cc9-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49cc9-111">См. также</span><span class="sxs-lookup"><span data-stu-id="49cc9-111">See also</span></span>

- <xref:System.String>
- [<span data-ttu-id="49cc9-112">Тип данных Char</span><span class="sxs-lookup"><span data-stu-id="49cc9-112">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="49cc9-113">Типы данных</span><span class="sxs-lookup"><span data-stu-id="49cc9-113">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
