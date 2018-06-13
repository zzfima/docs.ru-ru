---
title: Практическое руководство. Создание строки из значений массива символьного типа (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 104b329011d69e10a2926f31ce5d296759a3cce8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647184"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="efab7-102">Практическое руководство. Создание строки из значений массива символьного типа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="efab7-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="efab7-103">Этот пример создает строку «abcd» из отдельных символов.</span><span class="sxs-lookup"><span data-stu-id="efab7-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efab7-104">Пример</span><span class="sxs-lookup"><span data-stu-id="efab7-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-a-string-from-an-array-of-char-values_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="efab7-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="efab7-105">Compiling the Code</span></span>  
 <span data-ttu-id="efab7-106">У этого метода нет особых требований.</span><span class="sxs-lookup"><span data-stu-id="efab7-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="efab7-107">Синтаксис `"a"c`, где одному `c` соответствует отдельный символ в кавычки, используется для создания символьного литерала.</span><span class="sxs-lookup"><span data-stu-id="efab7-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="efab7-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="efab7-108">Robust Programming</span></span>  
 <span data-ttu-id="efab7-109">Символы NULL (эквивалентно `Chr(0)`) в строке могут привести к непредвиденным результатам при использовании этой строки.</span><span class="sxs-lookup"><span data-stu-id="efab7-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="efab7-110">Символ null будет включен в строку, но символы, следующие за будет отображаться в некоторых ситуациях.</span><span class="sxs-lookup"><span data-stu-id="efab7-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efab7-111">См. также</span><span class="sxs-lookup"><span data-stu-id="efab7-111">See Also</span></span>  
 <xref:System.String>  
 [<span data-ttu-id="efab7-112">Тип данных Char</span><span class="sxs-lookup"><span data-stu-id="efab7-112">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [<span data-ttu-id="efab7-113">Типы данных</span><span class="sxs-lookup"><span data-stu-id="efab7-113">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
