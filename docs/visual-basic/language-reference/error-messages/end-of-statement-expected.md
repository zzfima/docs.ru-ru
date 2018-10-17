---
title: Ожидается окончание оператора
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: 8df756009ebe3a0613ec47018d938151829214df
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2018
ms.locfileid: "49372321"
---
# <a name="end-of-statement-expected"></a><span data-ttu-id="9b02c-102">Ожидается окончание оператора</span><span class="sxs-lookup"><span data-stu-id="9b02c-102">End of statement expected</span></span>
<span data-ttu-id="9b02c-103">Оператор является синтаксически завершенным, однако дополнительный программный элемент элементом, выполненной инструкции.</span><span class="sxs-lookup"><span data-stu-id="9b02c-103">The statement is syntactically complete, but an additional programming element follows the element that completes the statement.</span></span> <span data-ttu-id="9b02c-104">Признак конца строки является обязательным в конце каждой инструкции.</span><span class="sxs-lookup"><span data-stu-id="9b02c-104">A line terminator is required at the end of every statement.</span></span>
  
 <span data-ttu-id="9b02c-105">Признак конца строки делит символов файла исходного кода в Visual Basic на строки.</span><span class="sxs-lookup"><span data-stu-id="9b02c-105">A line terminator divides the characters of a Visual Basic source file into lines.</span></span> <span data-ttu-id="9b02c-106">Признаки конца строки относятся Юникода каретки возвращаемого символа (& HD), Юникод перевода строки символ (& высокой ДОСТУПНОСТИ), и символ, за которым следует символ перевода строки Юникода возврата каретки Юникода.</span><span class="sxs-lookup"><span data-stu-id="9b02c-106">Examples of line terminators are the Unicode carriage return character (&HD), the Unicode linefeed character (&HA), and the Unicode carriage return character followed by the Unicode linefeed character.</span></span> <span data-ttu-id="9b02c-107">Дополнительные сведения о признаки конца строки, см. в разделе [спецификация языка Visual Basic](~/_vblang/spec/lexical-grammar.md#line-terminators).</span><span class="sxs-lookup"><span data-stu-id="9b02c-107">For more information about line terminators, see the [Visual Basic Language Specification](~/_vblang/spec/lexical-grammar.md#line-terminators).</span></span>
  
 <span data-ttu-id="9b02c-108">**Идентификатор ошибки:** BC30205</span><span class="sxs-lookup"><span data-stu-id="9b02c-108">**Error ID:** BC30205</span></span>
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9b02c-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="9b02c-109">To correct this error</span></span>
  
1.  <span data-ttu-id="9b02c-110">Установите этот флажок, чтобы увидеть, если два отдельных оператора случайно помещенных в той же строке.</span><span class="sxs-lookup"><span data-stu-id="9b02c-110">Check to see if two different statements have inadvertently been put on the same line.</span></span>
  
2.  <span data-ttu-id="9b02c-111">Вставьте знак завершения строки после элемента, выполняемой инструкции.</span><span class="sxs-lookup"><span data-stu-id="9b02c-111">Insert a line terminator after the element that completes the statement.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9b02c-112">См. также</span><span class="sxs-lookup"><span data-stu-id="9b02c-112">See Also</span></span>  
 [<span data-ttu-id="9b02c-113">Практическое руководство. Разбиение и объединение инструкций в коде</span><span class="sxs-lookup"><span data-stu-id="9b02c-113">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 [<span data-ttu-id="9b02c-114">Операторы</span><span class="sxs-lookup"><span data-stu-id="9b02c-114">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
