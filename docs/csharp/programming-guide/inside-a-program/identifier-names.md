---
title: Имена идентификаторов
description: Дополнительные сведения о правилах для допустимых имен идентификаторов в языке C#.
ms.date: 08/21/2018
ms.openlocfilehash: f8a27ddae0437ed037b59f76d60dc7e420ddc2eb
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589352"
---
# <a name="identifier-names"></a><span data-ttu-id="b1a0b-103">Имена идентификаторов</span><span class="sxs-lookup"><span data-stu-id="b1a0b-103">Identifier names</span></span>

<span data-ttu-id="b1a0b-104">**Идентификатор** — это имя, которое вы присваиваете типу (классу, интерфейсу, структуре, делегату или перечислению), члену, переменной или пространству имен.</span><span class="sxs-lookup"><span data-stu-id="b1a0b-104">An **identifier** is the name you assign to a type (class, interface, struct, delegate, or enum), member, variable, or namespace.</span></span> <span data-ttu-id="b1a0b-105">Допустимые идентификаторы должны соответствовать следующим правилам.</span><span class="sxs-lookup"><span data-stu-id="b1a0b-105">Valid identifiers must follow these rules:</span></span>

- <span data-ttu-id="b1a0b-106">Идентификатор должен начинаться с буквы или `_`.</span><span class="sxs-lookup"><span data-stu-id="b1a0b-106">Identifiers must start with a letter, or `_`.</span></span>
- <span data-ttu-id="b1a0b-107">Идентификаторы могут содержать буквенные символы Юникода, десятичные числа, символы соединения Юникода, несамостоятельные знаки Юникода или символы форматирования Юникода.</span><span class="sxs-lookup"><span data-stu-id="b1a0b-107">Identifiers may contain Unicode letter characters, decimal digit characters, Unicode connecting characters, Unicode combining characters, or Unicode formatting characters.</span></span> <span data-ttu-id="b1a0b-108">Дополнительные сведения о категориях Юникода см. в разделе [База данных категорий Юникода](https://www.unicode.org/reports/tr44/).</span><span class="sxs-lookup"><span data-stu-id="b1a0b-108">For more information on Unicode categories, see the [Unicode Category Database](https://www.unicode.org/reports/tr44/).</span></span>
<span data-ttu-id="b1a0b-109">Вы можете объявить идентификаторы, соответствующие ключевым словам C#, с помощью префикса идентификатора `@`.</span><span class="sxs-lookup"><span data-stu-id="b1a0b-109">You can declare identifiers that match C# keywords by using the `@` prefix on the identifier.</span></span> <span data-ttu-id="b1a0b-110">`@` не является частью имени идентификатора.</span><span class="sxs-lookup"><span data-stu-id="b1a0b-110">The `@` is not part of the identifier name.</span></span> <span data-ttu-id="b1a0b-111">Например, `@if` объявляет идентификатор с именем `if`.</span><span class="sxs-lookup"><span data-stu-id="b1a0b-111">For example, `@if` declares an identifier named `if`.</span></span> <span data-ttu-id="b1a0b-112">Эти [буквальные идентификаторы](../../language-reference/tokens/verbatim.md) предназначены главным образом для взаимодействия с идентификаторами, объявленными в других языках.</span><span class="sxs-lookup"><span data-stu-id="b1a0b-112">These [verbatim identifiers](../../language-reference/tokens/verbatim.md) are primarily for interoperability with identifiers declared in other languages.</span></span>

<span data-ttu-id="b1a0b-113">Полное определение допустимых идентификаторов см. в разделе [об идентификаторах в спецификации языка C#](../../../../_csharplang/spec/lexical-structure.md#identifiers).</span><span class="sxs-lookup"><span data-stu-id="b1a0b-113">For a complete definition of valid identifiers, see the [Identifiers topic in the C# Language Specification](../../../../_csharplang/spec/lexical-structure.md#identifiers).</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="b1a0b-114">Соглашения об именах</span><span class="sxs-lookup"><span data-stu-id="b1a0b-114">Naming conventions</span></span>

<span data-ttu-id="b1a0b-115">В дополнение к правилам для идентификаторов существует ряд [соглашений об именовании](../../../standard/design-guidelines/naming-guidelines.md), используемых в API-интерфейсах .NET.</span><span class="sxs-lookup"><span data-stu-id="b1a0b-115">In addition to the rules, there are a number of identifier [naming conventions](../../../standard/design-guidelines/naming-guidelines.md) used throughout the .NET APIs.</span></span> <span data-ttu-id="b1a0b-116">По соглашению программы C# используют `PascalCase` для имен типов, пространства имен и всех открытых членов.</span><span class="sxs-lookup"><span data-stu-id="b1a0b-116">By convention, C# programs use `PascalCase` for type names, namespaces, and all public members.</span></span> <span data-ttu-id="b1a0b-117">Кроме того, часто используются следующие соглашения.</span><span class="sxs-lookup"><span data-stu-id="b1a0b-117">In addition, the following conventions are common:</span></span>

- <span data-ttu-id="b1a0b-118">Имена интерфейсов начинаются с заглавной буквы `I`.</span><span class="sxs-lookup"><span data-stu-id="b1a0b-118">Interface names start with a capital `I`.</span></span>
- <span data-ttu-id="b1a0b-119">Типы атрибутов заканчиваются словом `Attribute`.</span><span class="sxs-lookup"><span data-stu-id="b1a0b-119">Attribute types end with the word `Attribute`.</span></span>
- <span data-ttu-id="b1a0b-120">Типы перечисления используют единственное число для объектов, не являющихся флагами, и множественное число для флагов.</span><span class="sxs-lookup"><span data-stu-id="b1a0b-120">Enum types use a singular noun for non-flags, and a plural noun for flags.</span></span>
- <span data-ttu-id="b1a0b-121">Идентификаторы не должны содержать два последовательных символа `_`.</span><span class="sxs-lookup"><span data-stu-id="b1a0b-121">Identifiers should not contain two consecutive `_` characters.</span></span> <span data-ttu-id="b1a0b-122">Эти имена зарезервированы для идентификаторов, созданных компилятором.</span><span class="sxs-lookup"><span data-stu-id="b1a0b-122">Those names are reserved for compiler generated identifiers.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b1a0b-123">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="b1a0b-123">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b1a0b-124">См. также</span><span class="sxs-lookup"><span data-stu-id="b1a0b-124">See also</span></span>

- [<span data-ttu-id="b1a0b-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b1a0b-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b1a0b-126">Структура программы C#</span><span class="sxs-lookup"><span data-stu-id="b1a0b-126">Inside a C# Program</span></span>](./index.md)
- [<span data-ttu-id="b1a0b-127">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b1a0b-127">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="b1a0b-128">Классы</span><span class="sxs-lookup"><span data-stu-id="b1a0b-128">Classes</span></span>](../classes-and-structs/classes.md)
- [<span data-ttu-id="b1a0b-129">Структуры</span><span class="sxs-lookup"><span data-stu-id="b1a0b-129">Structs</span></span>](../classes-and-structs/structs.md)
- [<span data-ttu-id="b1a0b-130">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="b1a0b-130">Namespaces</span></span>](../namespaces/index.md)
- [<span data-ttu-id="b1a0b-131">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="b1a0b-131">Interfaces</span></span>](../interfaces/index.md)
- [<span data-ttu-id="b1a0b-132">Делегаты</span><span class="sxs-lookup"><span data-stu-id="b1a0b-132">Delegates</span></span>](../delegates/index.md)
