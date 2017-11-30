---
title: "Символьные типы данных (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d1066444ba3a98f26fc2a35135a50b2954c6b992
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="character-data-types-visual-basic"></a><span data-ttu-id="57ce3-102">Символьные типы данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57ce3-102">Character Data Types (Visual Basic)</span></span>
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="57ce3-103">предоставляет *символьные типы данных* работать с печатными отображаемую символами и.</span><span class="sxs-lookup"><span data-stu-id="57ce3-103"> provides *character data types* to deal with printable and displayable characters.</span></span> <span data-ttu-id="57ce3-104">Оба они работают с символами Юникода, `Char` содержит один символ, в то время как `String` содержит неопределенное число символов.</span><span class="sxs-lookup"><span data-stu-id="57ce3-104">While they both deal with Unicode characters, `Char` holds a single character whereas `String` contains an indefinite number of characters.</span></span>  
  
 <span data-ttu-id="57ce3-105">Для таблицы, которая отображает сравнение side-by-side [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] типов данных в разделе [типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span><span class="sxs-lookup"><span data-stu-id="57ce3-105">For a table that displays a side-by-side comparison of the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="char-type"></a><span data-ttu-id="57ce3-106">Char-тип</span><span class="sxs-lookup"><span data-stu-id="57ce3-106">Char Type</span></span>  
 <span data-ttu-id="57ce3-107">`Char` Тип данных — это отдельный символ Юникода (16-разрядная версия) 2 байта.</span><span class="sxs-lookup"><span data-stu-id="57ce3-107">The `Char` data type is a single two-byte (16-bit) Unicode character.</span></span> <span data-ttu-id="57ce3-108">Если переменная всегда хранит ровно один символ, он объявляется как `Char`.</span><span class="sxs-lookup"><span data-stu-id="57ce3-108">If a variable always stores exactly one character, declare it as `Char`.</span></span> <span data-ttu-id="57ce3-109">Пример:</span><span class="sxs-lookup"><span data-stu-id="57ce3-109">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_1.vb)]  
  
 <span data-ttu-id="57ce3-110">Каждое возможное значение в `Char` или `String` переменная *кодовой*, или код символа в кодировке Юникод.</span><span class="sxs-lookup"><span data-stu-id="57ce3-110">Each possible value in a `Char` or `String` variable is a *code point*, or character code, in the Unicode character set.</span></span> <span data-ttu-id="57ce3-111">Символы Юникода включают базовый набор символов ASCII, различные другие буквы алфавита, диакритические знаки, символы валют, дроби, диакритические знаки и математические и технические символы.</span><span class="sxs-lookup"><span data-stu-id="57ce3-111">Unicode characters include the basic ASCII character set, various other alphabet letters, accents, currency symbols, fractions, diacritics, and mathematical and technical symbols.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57ce3-112">Набор символов Юникода резервирует кодовые точки от D800 до DFFF (55296 до 55551) для *суррогатной парой*, которых требуется два 16-разрядных значения и представляют одну кодовую точку.</span><span class="sxs-lookup"><span data-stu-id="57ce3-112">The Unicode character set reserves the code points D800 through DFFF (55296 through 55551 decimal) for *surrogate pairs*, which require two 16-bit values to represent a single code point.</span></span> <span data-ttu-id="57ce3-113">Объект `Char` переменная не может содержать суррогатную пару и `String` использует две позиции для хранения таких пар.</span><span class="sxs-lookup"><span data-stu-id="57ce3-113">A `Char` variable cannot hold a surrogate pair, and a `String` uses two positions to hold such a pair.</span></span>  
  
 <span data-ttu-id="57ce3-114">Дополнительные сведения см. в разделе [тип данных Char](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="57ce3-114">For more information, see [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span></span>  
  
## <a name="string-type"></a><span data-ttu-id="57ce3-115">Тип String</span><span class="sxs-lookup"><span data-stu-id="57ce3-115">String Type</span></span>  
 <span data-ttu-id="57ce3-116">`String` Тип данных представляет собой последовательность ноль или более символов Юникода (16-разрядная версия) 2 байта.</span><span class="sxs-lookup"><span data-stu-id="57ce3-116">The `String` data type is a sequence of zero or more two-byte (16-bit) Unicode characters.</span></span> <span data-ttu-id="57ce3-117">Если переменная может содержать неограниченное число знаков, объявите его как `String`.</span><span class="sxs-lookup"><span data-stu-id="57ce3-117">If a variable can contain an indefinite number of characters, declare it as `String`.</span></span> <span data-ttu-id="57ce3-118">Пример:</span><span class="sxs-lookup"><span data-stu-id="57ce3-118">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_2.vb)]  
  
 <span data-ttu-id="57ce3-119">Дополнительные сведения см. в разделе [строкового типа данных](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="57ce3-119">For more information, see [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57ce3-120">См. также</span><span class="sxs-lookup"><span data-stu-id="57ce3-120">See Also</span></span>  
 [<span data-ttu-id="57ce3-121">Простые типы данных</span><span class="sxs-lookup"><span data-stu-id="57ce3-121">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="57ce3-122">Составные типы данных</span><span class="sxs-lookup"><span data-stu-id="57ce3-122">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [<span data-ttu-id="57ce3-123">Универсальные типы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="57ce3-123">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="57ce3-124">Типы значений и ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="57ce3-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="57ce3-125">Преобразования типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="57ce3-125">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="57ce3-126">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="57ce3-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="57ce3-127">Знаки типов</span><span class="sxs-lookup"><span data-stu-id="57ce3-127">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
