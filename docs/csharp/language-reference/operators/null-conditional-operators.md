---
title: Справочник по C#. Условные операции со значением "null"
ms.custom: seodec18
ms.date: 04/03/2015
helpviewer_keywords:
- null-conditional operators [C#]
- ?. operator [C#]
- ?[] operator [C#]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
ms.openlocfilehash: 38298cded904cbfedeaf3c6b66c74d610d714902
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333243"
---
# <a name="-and--null-conditional-operators-c-and-visual-basic"></a><span data-ttu-id="f1f99-102">?.</span><span class="sxs-lookup"><span data-stu-id="f1f99-102">?.</span></span> <span data-ttu-id="f1f99-103">Условные операции со значением "null" (and ?[]) в C# и Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f1f99-103">and ?[] null-conditional operators (C# and Visual Basic)</span></span>

<span data-ttu-id="f1f99-104">Проверяет значение левого операнда на наличие значения NULL перед выполнением операции доступа к элементу (`?.`) или индексу (`?[]`). Возвращает `null`, если левый операнд имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="f1f99-104">Tests the value of the left-hand operand for null before performing a member access (`?.`) or index (`?[]`) operation; returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="f1f99-105">Эти операторы позволяют писать меньше кода для проверок значений null, особенно если речь идет о внедрении в структуры данных.</span><span class="sxs-lookup"><span data-stu-id="f1f99-105">These operators help you write less code to handle null checks, especially for descending into data structures.</span></span>

```csharp
int? length = customers?.Length; // null if customers is null
Customer first = customers?[0];  // null if customers is null
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null
```

<span data-ttu-id="f1f99-106">Операторы с условием NULL предусматривают сокращенную обработку.</span><span class="sxs-lookup"><span data-stu-id="f1f99-106">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="f1f99-107">Если одна из операций в цепочке условных операций доступа к члену и операций индексирования возвращает значение NULL, то выполнение остальной части цепочки прекращается.</span><span class="sxs-lookup"><span data-stu-id="f1f99-107">If one operation in a chain of conditional member access and index operations returns null, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="f1f99-108">В приведенном ниже примере `E` не выполняется, если `A`, `B` или `C` имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="f1f99-108">In the following example, `E` doesn't execute if `A`, `B`, or `C` evaluates to null.</span></span>

```csharp
A?.B?.C?.Do(E);
A?.B?.C?[E];
```

<span data-ttu-id="f1f99-109">Другим примером использования для доступа к элементам с условием NULL является вызов делегатов в потокобезопасном режиме с существенно меньшим объемом кода.</span><span class="sxs-lookup"><span data-stu-id="f1f99-109">Another use for the null-conditional member access is invoking delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="f1f99-110">Для старого способа требуется примерно следующий код:</span><span class="sxs-lookup"><span data-stu-id="f1f99-110">The old way requires code like the following:</span></span>

```csharp
var handler = this.PropertyChanged;
if (handler != null)
    handler(…);
```

<span data-ttu-id="f1f99-111">Новый способ гораздо проще:</span><span class="sxs-lookup"><span data-stu-id="f1f99-111">The new way is much simpler:</span></span>

```csharp
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="f1f99-112">Новый способ является потокобезопасным, так как компилятор создает код для вычисления `PropertyChanged` только один раз, запоминая результат во временной переменной.</span><span class="sxs-lookup"><span data-stu-id="f1f99-112">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="f1f99-113">Необходимо явно вызывать метод `Invoke`, так как отсутствует синтаксис `PropertyChanged?(e)` для вызова делегатов с условием NULL.</span><span class="sxs-lookup"><span data-stu-id="f1f99-113">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>

## <a name="language-specifications"></a><span data-ttu-id="f1f99-114">Спецификации языков</span><span class="sxs-lookup"><span data-stu-id="f1f99-114">Language specifications</span></span>

<span data-ttu-id="f1f99-115">Дополнительные сведения см. в разделе об [операторах с условием NULL](~/_csharplang/spec/expressions.md#null-conditional-operator) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="f1f99-115">For more information, see [Null-conditional operator](~/_csharplang/spec/expressions.md#null-conditional-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="f1f99-116">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="f1f99-116">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1f99-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f1f99-117">See also</span></span>

- [<span data-ttu-id="f1f99-118">Оператор ?? (оператор объединения со значением NULL)</span><span class="sxs-lookup"><span data-stu-id="f1f99-118">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="f1f99-119">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f1f99-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f1f99-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f1f99-120">C# Programming Guide</span></span>](../../programming-guide/index.md)