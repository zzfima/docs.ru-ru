---
title: Справочник по C#. Ключевые слова операторов
ms.custom: seodec18
ms.date: 12/10/2018
helpviewer_keywords:
- keywords [C#], operators
- operators [C#], keywords
ms.assetid: f745c81f-f8d8-4673-86a1-0f3a85cc63c3
ms.openlocfilehash: e03e1c930b452cf5e4f2c4bb1d06d5363f20c991
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243613"
---
# <a name="operator-keywords-c-reference"></a><span data-ttu-id="17b2c-102">Ключевые слова операторов (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="17b2c-102">Operator Keywords (C# Reference)</span></span>

<span data-ttu-id="17b2c-103">Используются для выполнения различных действий, включая создание объектов, проверку типа объекта во время выполнения, получение размера типа и другие операции.</span><span class="sxs-lookup"><span data-stu-id="17b2c-103">Used to perform miscellaneous actions such as creating objects, checking the run-time type of an object, obtaining the size of a type, and other actions.</span></span> <span data-ttu-id="17b2c-104">В этом разделе описываются следующие ключевые слова:</span><span class="sxs-lookup"><span data-stu-id="17b2c-104">This section introduces the following keywords:</span></span>

- <span data-ttu-id="17b2c-105">[as](as.md): преобразует объект в совместимый тип.</span><span class="sxs-lookup"><span data-stu-id="17b2c-105">[as](as.md) Converts an object to a compatible type.</span></span>

- <span data-ttu-id="17b2c-106">[await](await.md): приостанавливает выполнение метода [async](async.md) до тех пор, пока не будет завершена ожидаемая задача.</span><span class="sxs-lookup"><span data-stu-id="17b2c-106">[await](await.md) Suspends an [async](async.md) method until an awaited task is completed.</span></span>

- <span data-ttu-id="17b2c-107">[is](is.md): проверяет типы среды выполнения объекта или (начиная с C# 7.0) проверяет выражение на соответствие шаблону.</span><span class="sxs-lookup"><span data-stu-id="17b2c-107">[is](is.md) Checks the run-time type of an object, or (starting with C# 7.0) tests an expression against a pattern.</span></span>

- [<span data-ttu-id="17b2c-108">new</span><span class="sxs-lookup"><span data-stu-id="17b2c-108">new</span></span>](new.md)

  - <span data-ttu-id="17b2c-109">[Оператор new](new-operator.md): создает объекты.</span><span class="sxs-lookup"><span data-stu-id="17b2c-109">[new Operator](new-operator.md) Creates objects.</span></span>

  - <span data-ttu-id="17b2c-110">[Модификатор new](new-modifier.md): скрывает унаследованный член.</span><span class="sxs-lookup"><span data-stu-id="17b2c-110">[new Modifier](new-modifier.md) Hides an inherited member.</span></span>

  - <span data-ttu-id="17b2c-111">[Ограничение new](new-constraint.md): определяет значение параметра типа.</span><span class="sxs-lookup"><span data-stu-id="17b2c-111">[new Constraint](new-constraint.md) Qualifies a type parameter.</span></span>

- <span data-ttu-id="17b2c-112">[nameof](nameof.md): используется для получения простого (неполного) строкового имени переменной, типа или члена.</span><span class="sxs-lookup"><span data-stu-id="17b2c-112">[nameof](nameof.md) Obtains the simple (unqualified) string name of a variable, type, or member.</span></span>

- <span data-ttu-id="17b2c-113">[sizeof](sizeof.md): получает размер неуправляемого типа.</span><span class="sxs-lookup"><span data-stu-id="17b2c-113">[sizeof](sizeof.md) Obtains the size of an unmanaged type.</span></span>  

- <span data-ttu-id="17b2c-114">[typeof](typeof.md): получает объект <xref:System.Type?displayProperty=nameWithType> для типа.</span><span class="sxs-lookup"><span data-stu-id="17b2c-114">[typeof](typeof.md) Obtains the <xref:System.Type?displayProperty=nameWithType> object for a type.</span></span>  

- [<span data-ttu-id="17b2c-115">true</span><span class="sxs-lookup"><span data-stu-id="17b2c-115">true</span></span>](true.md)  

  - <span data-ttu-id="17b2c-116">[Оператор true](true-false-operators.md) возвращает [логическое](bool.md) значение `true`, указывая, что операнд имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="17b2c-116">[true Operator](true-false-operators.md) Returns the [bool](bool.md) value `true` to indicate that the operand is definitely true.</span></span>

  - <span data-ttu-id="17b2c-117">[Литерал true](true-literal.md): представляет [логическое](bool.md) значение `true`.</span><span class="sxs-lookup"><span data-stu-id="17b2c-117">[true Literal](true-literal.md) Represents the [bool](bool.md) value `true`.</span></span>

- [<span data-ttu-id="17b2c-118">false</span><span class="sxs-lookup"><span data-stu-id="17b2c-118">false</span></span>](false.md)  

  - <span data-ttu-id="17b2c-119">[Оператор false](true-false-operators.md) возвращает [логическое](bool.md) значение `true`, указывая, что операнд имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="17b2c-119">[false Operator](true-false-operators.md) Returns the [bool](bool.md) value `true` to indicate that the operand is definitely false.</span></span>

  - <span data-ttu-id="17b2c-120">[Литерал false](false-literal.md): представляет [логическое](bool.md) значение `false`.</span><span class="sxs-lookup"><span data-stu-id="17b2c-120">[false Literal](false-literal.md) Represents the [bool](bool.md) value `false`.</span></span>

- <span data-ttu-id="17b2c-121">[stackalloc](stackalloc.md): выделяет блок памяти в стеке.</span><span class="sxs-lookup"><span data-stu-id="17b2c-121">[stackalloc](stackalloc.md) Allocates a block of memory on the stack.</span></span>  

<span data-ttu-id="17b2c-122">В разделе [Операторы](statement-keywords.md) описываются следующие ключевые слова, которые могут использоваться и как операторы, и как инструкции:</span><span class="sxs-lookup"><span data-stu-id="17b2c-122">The following keywords, which can be used as operators and as statements, are covered in the [Statements](statement-keywords.md) section:</span></span>

- <span data-ttu-id="17b2c-123">[checked](checked.md): указывает проверенный контекст.</span><span class="sxs-lookup"><span data-stu-id="17b2c-123">[checked](checked.md) Specifies checked context.</span></span>  

- <span data-ttu-id="17b2c-124">[unchecked](unchecked.md): указывает непроверенный контекст.</span><span class="sxs-lookup"><span data-stu-id="17b2c-124">[unchecked](unchecked.md) Specifies unchecked context.</span></span>  

## <a name="see-also"></a><span data-ttu-id="17b2c-125">См. также</span><span class="sxs-lookup"><span data-stu-id="17b2c-125">See also</span></span>

- [<span data-ttu-id="17b2c-126">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="17b2c-126">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="17b2c-127">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="17b2c-127">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="17b2c-128">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="17b2c-128">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="17b2c-129">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="17b2c-129">C# Operators</span></span>](../operators/index.md)
