---
title: Практическое руководство. Создание строки из значений массива символьного типа
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: bf37ceba901e712df10ad4b39f9ad74194843136
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346772"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="0324f-102">Практическое руководство. Создание строки из значений массива символьного типа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0324f-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="0324f-103">В этом примере создается строка «ABCD» из отдельных символов.</span><span class="sxs-lookup"><span data-stu-id="0324f-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0324f-104">Пример</span><span class="sxs-lookup"><span data-stu-id="0324f-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="0324f-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="0324f-105">Compile the code</span></span>  
 <span data-ttu-id="0324f-106">Этот метод не имеет особых требований.</span><span class="sxs-lookup"><span data-stu-id="0324f-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="0324f-107">Синтаксис `"a"c`, где один `c` следует за одиночным символом в кавычках, используется для создания символьного литерала.</span><span class="sxs-lookup"><span data-stu-id="0324f-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0324f-108">Надежное программирование</span><span class="sxs-lookup"><span data-stu-id="0324f-108">Robust Programming</span></span>  
 <span data-ttu-id="0324f-109">Символы NULL (эквивалентные `Chr(0)`) в строке могут привести к непредвиденным результатам при использовании строки.</span><span class="sxs-lookup"><span data-stu-id="0324f-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="0324f-110">Символ null будет включаться в строку, но символы, следующие за символом NULL, не будут отображаться в некоторых ситуациях.</span><span class="sxs-lookup"><span data-stu-id="0324f-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0324f-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="0324f-111">See also</span></span>

- <xref:System.String>
- [<span data-ttu-id="0324f-112">Тип данных Char</span><span class="sxs-lookup"><span data-stu-id="0324f-112">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="0324f-113">Типы данных</span><span class="sxs-lookup"><span data-stu-id="0324f-113">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
