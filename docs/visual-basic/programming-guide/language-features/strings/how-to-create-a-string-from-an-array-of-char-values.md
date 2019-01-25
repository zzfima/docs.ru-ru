---
title: Как выполнить Создать строку из массива значений типа Char (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: a067474d6b32589a34b031d5c3ea4e5a4be55834
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611466"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="fed66-102">Как выполнить Создать строку из массива значений типа Char (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fed66-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="fed66-103">Этот пример создает строки «abcd» из отдельных символов.</span><span class="sxs-lookup"><span data-stu-id="fed66-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fed66-104">Пример</span><span class="sxs-lookup"><span data-stu-id="fed66-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-a-string-from-an-array-of-char-values_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fed66-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="fed66-105">Compiling the Code</span></span>  
 <span data-ttu-id="fed66-106">Этот метод не имеет специальных требований.</span><span class="sxs-lookup"><span data-stu-id="fed66-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="fed66-107">Синтаксис `"a"c`, когда одному `c` соответствует отдельный символ в кавычки, используется для создания символьного литерала.</span><span class="sxs-lookup"><span data-stu-id="fed66-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="fed66-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="fed66-108">Robust Programming</span></span>  
 <span data-ttu-id="fed66-109">Символы NULL (эквивалентно `Chr(0)`) в строке могут привести к непредвиденным результатам при использовании этой строки.</span><span class="sxs-lookup"><span data-stu-id="fed66-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="fed66-110">Нуль-символ будет включен в строку, но символы, следующие нуль-символ будет отображаться в некоторых ситуациях.</span><span class="sxs-lookup"><span data-stu-id="fed66-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed66-111">См. также</span><span class="sxs-lookup"><span data-stu-id="fed66-111">See also</span></span>
- <xref:System.String>
- [<span data-ttu-id="fed66-112">Тип данных Char</span><span class="sxs-lookup"><span data-stu-id="fed66-112">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="fed66-113">Типы данных</span><span class="sxs-lookup"><span data-stu-id="fed66-113">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
