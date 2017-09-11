---
title: "Символьные типы данных (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- data types [Visual Basic], character
- String data type, character data types
- character data types [Visual Basic]
- Char data type, character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
caps.latest.revision: 23
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
ms.openlocfilehash: 3407f614d5898f4fccf04e0363ec31669661b60a
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="character-data-types-visual-basic"></a><span data-ttu-id="7ea20-102">Символьные типы данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ea20-102">Character Data Types (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="7ea20-103">предоставляет *символьные типы данных* для работы с символами, печати и отображения.</span><span class="sxs-lookup"><span data-stu-id="7ea20-103"> provides *character data types* to deal with printable and displayable characters.</span></span> <span data-ttu-id="7ea20-104">Хотя оба они работают с символами Юникода, `Char` содержит один символ, тогда как `String` содержит неопределенное число символов.</span><span class="sxs-lookup"><span data-stu-id="7ea20-104">While they both deal with Unicode characters, `Char` holds a single character whereas `String` contains an indefinite number of characters.</span></span>  
  
 <span data-ttu-id="7ea20-105">Для таблицы, которая отображает сравнение side-by-side [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] типы данных в разделе [типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span><span class="sxs-lookup"><span data-stu-id="7ea20-105">For a table that displays a side-by-side comparison of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="char-type"></a><span data-ttu-id="7ea20-106">Тип char</span><span class="sxs-lookup"><span data-stu-id="7ea20-106">Char Type</span></span>  
 <span data-ttu-id="7ea20-107">`Char` Тип данных является символ Юникода (16-разрядная версия)&2; байта.</span><span class="sxs-lookup"><span data-stu-id="7ea20-107">The `Char` data type is a single two-byte (16-bit) Unicode character.</span></span> <span data-ttu-id="7ea20-108">Если переменная всегда хранит ровно один знак, объявите ее в качестве `Char`.</span><span class="sxs-lookup"><span data-stu-id="7ea20-108">If a variable always stores exactly one character, declare it as `Char`.</span></span> <span data-ttu-id="7ea20-109">Например:</span><span class="sxs-lookup"><span data-stu-id="7ea20-109">For example:</span></span>  
  
 <span data-ttu-id="7ea20-110">[!code-vb[VbVbalrCharTypes&#1;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="7ea20-110">[!code-vb[VbVbalrCharTypes#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_1.vb)]</span></span>  
  
 <span data-ttu-id="7ea20-111">Каждое возможное значение в `Char` или `String` переменная *кодовой*, или код символа в кодировке Юникод.</span><span class="sxs-lookup"><span data-stu-id="7ea20-111">Each possible value in a `Char` or `String` variable is a *code point*, or character code, in the Unicode character set.</span></span> <span data-ttu-id="7ea20-112">Символы Юникода включают базовый набор символов ASCII, различные другие буквы алфавита, знаки ударения, символы валют, дроби, диакритические знаки и математические и технические символы.</span><span class="sxs-lookup"><span data-stu-id="7ea20-112">Unicode characters include the basic ASCII character set, various other alphabet letters, accents, currency symbols, fractions, diacritics, and mathematical and technical symbols.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ea20-113">Набор символов Юникода резервирует кодовые точки от D800 до DFFF (55296 до 55551) для *суррогатные пары*, который требуется два 16-разрядных значения и представляют одну кодовую точку.</span><span class="sxs-lookup"><span data-stu-id="7ea20-113">The Unicode character set reserves the code points D800 through DFFF (55296 through 55551 decimal) for *surrogate pairs*, which require two 16-bit values to represent a single code point.</span></span> <span data-ttu-id="7ea20-114">Объект `Char` переменная не может содержать суррогатную пару и `String` использует две позиции для хранения таких пар.</span><span class="sxs-lookup"><span data-stu-id="7ea20-114">A `Char` variable cannot hold a surrogate pair, and a `String` uses two positions to hold such a pair.</span></span>  
  
 <span data-ttu-id="7ea20-115">Дополнительные сведения см. в разделе [тип данных Char](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="7ea20-115">For more information, see [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span></span>  
  
## <a name="string-type"></a><span data-ttu-id="7ea20-116">Тип строки</span><span class="sxs-lookup"><span data-stu-id="7ea20-116">String Type</span></span>  
 <span data-ttu-id="7ea20-117">`String` Тип данных представляет собой последовательность из нуля или более символов Юникода (16-разрядная версия)&2; байта.</span><span class="sxs-lookup"><span data-stu-id="7ea20-117">The `String` data type is a sequence of zero or more two-byte (16-bit) Unicode characters.</span></span> <span data-ttu-id="7ea20-118">Если переменная может содержать неограниченное количество символов, он объявляется как `String`.</span><span class="sxs-lookup"><span data-stu-id="7ea20-118">If a variable can contain an indefinite number of characters, declare it as `String`.</span></span> <span data-ttu-id="7ea20-119">Пример:</span><span class="sxs-lookup"><span data-stu-id="7ea20-119">For example:</span></span>  
  
 <span data-ttu-id="7ea20-120">[!code-vb[VbVbalrCharTypes&#2;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="7ea20-120">[!code-vb[VbVbalrCharTypes#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_2.vb)]</span></span>  
  
 <span data-ttu-id="7ea20-121">Дополнительные сведения см. в разделе [строковый тип данных](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="7ea20-121">For more information, see [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ea20-122">См. также</span><span class="sxs-lookup"><span data-stu-id="7ea20-122">See Also</span></span>  
 <span data-ttu-id="7ea20-123">[Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="7ea20-123">[Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
<span data-ttu-id="7ea20-124"> [Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="7ea20-124"> [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span></span>  
<span data-ttu-id="7ea20-125"> [Универсальные типы в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="7ea20-125"> [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span></span>  
<span data-ttu-id="7ea20-126"> [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="7ea20-126"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="7ea20-127"> [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="7ea20-127"> [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="7ea20-128"> [Устранение неполадок типы данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="7ea20-128"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="7ea20-129"> [Знаки типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span><span class="sxs-lookup"><span data-stu-id="7ea20-129"> [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span></span>
