---
title: for (Справочник по C#)
ms.date: 06/13/2018
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
ms.openlocfilehash: beac7727c8ce83d8ea20f0fc578f80ceef3053e7
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208006"
---
# <a name="for-c-reference"></a><span data-ttu-id="9cc72-102">for (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="9cc72-102">for (C# reference)</span></span>

<span data-ttu-id="9cc72-103">Оператор `for` выполняет оператор или блок операторов, пока определенное логическое выражение не примет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="9cc72-103">The `for` statement executes a statement or a block of statements while a specified boolean expression evaluates to `true`.</span></span>

<span data-ttu-id="9cc72-104">В любой момент в блоке операторов `for` вы можете прервать цикл с помощью оператора [break](break.md) или перейти к следующей итерации в цикле с помощью оператора [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="9cc72-104">At any point within the `for` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="9cc72-105">Также можно выйти из цикла `for` с помощью операторов [goto](goto.md), [return](return.md) или [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="9cc72-105">You also can exit a `for` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>
  
## <a name="structure-of-the-for-statement"></a><span data-ttu-id="9cc72-106">Структура оператора `for`</span><span class="sxs-lookup"><span data-stu-id="9cc72-106">Structure of the `for` statement</span></span>

<span data-ttu-id="9cc72-107">Оператор `for` определяет разделы *инициализатора*, *условия* и *итератора*:</span><span class="sxs-lookup"><span data-stu-id="9cc72-107">The `for` statement defines *initializer*, *condition*, and *iterator* sections:</span></span>
  
```csharp
for (initializer; condition; iterator)  
    body  
```

<span data-ttu-id="9cc72-108">Все три раздела добавляются по желанию.</span><span class="sxs-lookup"><span data-stu-id="9cc72-108">All three sections are optional.</span></span> <span data-ttu-id="9cc72-109">Тело цикла является оператором или блоком операторов.</span><span class="sxs-lookup"><span data-stu-id="9cc72-109">The body of the loop is either a statement or a block of statements.</span></span>

<span data-ttu-id="9cc72-110">В следующем примере показан оператор `for` со всеми определенными разделами:</span><span class="sxs-lookup"><span data-stu-id="9cc72-110">The following example shows the `for` statement with all of the sections defined:</span></span>

[!code-csharp-interactive[for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#5)]

### <a name="the-initializer-section"></a><span data-ttu-id="9cc72-111">Раздел *инициализатора*</span><span class="sxs-lookup"><span data-stu-id="9cc72-111">The *initializer* section</span></span>

<span data-ttu-id="9cc72-112">Операторы в разделе *инициализатора* выполняются только один раз перед входом в цикл.</span><span class="sxs-lookup"><span data-stu-id="9cc72-112">The statements in the *initializer* section are executed only once, before entering the loop.</span></span> <span data-ttu-id="9cc72-113">Раздел *инициализатора* представляет собой один из следующих объектов:</span><span class="sxs-lookup"><span data-stu-id="9cc72-113">The *initializer* section is either of the following:</span></span>

- <span data-ttu-id="9cc72-114">Объявление и инициализация локальной переменной цикла, к которой невозможно получить доступ вне цикла.</span><span class="sxs-lookup"><span data-stu-id="9cc72-114">The declaration and initialization of a local loop variable, which can't be accessed from outside the loop.</span></span>

- <span data-ttu-id="9cc72-115">Ноль или более выражений операторов из следующего списка, разделенные запятыми:</span><span class="sxs-lookup"><span data-stu-id="9cc72-115">Zero or more statement expressions from the following list, separated by commas:</span></span>

  - <span data-ttu-id="9cc72-116">оператор [присваивания](../operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="9cc72-116">[assignment](../operators/assignment-operator.md) statement</span></span>

  - <span data-ttu-id="9cc72-117">вызов метода</span><span class="sxs-lookup"><span data-stu-id="9cc72-117">invocation of a method</span></span>  

  - <span data-ttu-id="9cc72-118">префиксное или постфиксное выражение [приращения](../operators/increment-operator.md), такое как `++i` или `i++`</span><span class="sxs-lookup"><span data-stu-id="9cc72-118">prefix or postfix [increment](../operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  

  - <span data-ttu-id="9cc72-119">префиксное или постфиксное выражение [декремента](../operators/decrement-operator.md), такое как `--i` или `i--`</span><span class="sxs-lookup"><span data-stu-id="9cc72-119">prefix or postfix [decrement](../operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  

  - <span data-ttu-id="9cc72-120">создание объекта с помощью ключевого слова [new](new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="9cc72-120">creation of an object by using [new](new-operator.md) keyword</span></span>

  - <span data-ttu-id="9cc72-121">выражение [await](await.md)</span><span class="sxs-lookup"><span data-stu-id="9cc72-121">[await](await.md) expression</span></span>

<span data-ttu-id="9cc72-122">Раздел *инициализатора* в приведенном выше примере объявляет и инициализирует локальную переменную цикла `i`:</span><span class="sxs-lookup"><span data-stu-id="9cc72-122">The *initializer* section in the example above declares and initializes the local loop variable `i`:</span></span>

```csharp
int i = 0
```

### <a name="the-condition-section"></a><span data-ttu-id="9cc72-123">Раздел *условия*</span><span class="sxs-lookup"><span data-stu-id="9cc72-123">The *condition* section</span></span>

<span data-ttu-id="9cc72-124">Раздел *условия*, если он определен, должен быть логическим выражением.</span><span class="sxs-lookup"><span data-stu-id="9cc72-124">The *condition* section, if present, must be a boolean expression.</span></span> <span data-ttu-id="9cc72-125">Это выражение оценивается перед каждой итерацией цикла.</span><span class="sxs-lookup"><span data-stu-id="9cc72-125">That expression is evaluated before every loop iteration.</span></span> <span data-ttu-id="9cc72-126">Если раздел *условия* отсутствует или логическое выражение имеет значение `true`, выполняется следующая итерация цикла. В противном случае выполняется выход из цикла.</span><span class="sxs-lookup"><span data-stu-id="9cc72-126">If the *condition* section is not present or the boolean expression evaluates to `true`, the next loop iteration is executed; otherwise, the loop is exited.</span></span>

<span data-ttu-id="9cc72-127">Раздел *условия* в приведенном выше примере определяет, завершится ли цикл в зависимости от значения локальной переменной цикла:</span><span class="sxs-lookup"><span data-stu-id="9cc72-127">The *condition* section in the example above determines if the loop terminates based on the value of the local loop variable:</span></span>

```csharp
i < 5
```

### <a name="the-iterator-section"></a><span data-ttu-id="9cc72-128">Раздел *итератора*</span><span class="sxs-lookup"><span data-stu-id="9cc72-128">The *iterator* section</span></span>

<span data-ttu-id="9cc72-129">Раздел *итератора* определяет, что происходит после каждой итерации тела цикла.</span><span class="sxs-lookup"><span data-stu-id="9cc72-129">The *iterator* section defines what happens after each iteration of the body of the loop.</span></span> <span data-ttu-id="9cc72-130">Раздел *итератора* содержит ноль или более следующих выражений оператора, разделенных запятыми:</span><span class="sxs-lookup"><span data-stu-id="9cc72-130">The *iterator* section contains zero or more of the following statement expressions, separated by commas:</span></span>  

- <span data-ttu-id="9cc72-131">оператор [присваивания](../operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="9cc72-131">[assignment](../operators/assignment-operator.md) statement</span></span>

- <span data-ttu-id="9cc72-132">вызов метода</span><span class="sxs-lookup"><span data-stu-id="9cc72-132">invocation of a method</span></span>  

- <span data-ttu-id="9cc72-133">префиксное или постфиксное выражение [приращения](../operators/increment-operator.md), такое как `++i` или `i++`</span><span class="sxs-lookup"><span data-stu-id="9cc72-133">prefix or postfix [increment](../operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  

- <span data-ttu-id="9cc72-134">префиксное или постфиксное выражение [декремента](../operators/decrement-operator.md), такое как `--i` или `i--`</span><span class="sxs-lookup"><span data-stu-id="9cc72-134">prefix or postfix [decrement](../operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  

- <span data-ttu-id="9cc72-135">создание объекта с помощью ключевого слова [new](new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="9cc72-135">creation of an object by using [new](new-operator.md) keyword</span></span>

- <span data-ttu-id="9cc72-136">выражение [await](await.md)</span><span class="sxs-lookup"><span data-stu-id="9cc72-136">[await](await.md) expression</span></span>

<span data-ttu-id="9cc72-137">Раздел *итератора* в приведенном выше примере увеличивает локальную переменную цикла:</span><span class="sxs-lookup"><span data-stu-id="9cc72-137">The *iterator* section in the example above increments the local loop variable:</span></span>

```csharp
i++
```

## <a name="examples"></a><span data-ttu-id="9cc72-138">Примеры</span><span class="sxs-lookup"><span data-stu-id="9cc72-138">Examples</span></span>

<span data-ttu-id="9cc72-139">В следующем примере показано несколько менее распространенных вариантов использования разделов оператора `for`: присваивание значения внешней переменной цикла в разделе *инициализатора*, вызов метода в разделах *инициализатора* и *итератора* и изменение значения двух переменных в разделе *итератора*.</span><span class="sxs-lookup"><span data-stu-id="9cc72-139">The following example illustrates several less common usages of the `for` statement sections: assigning a value to an external loop variable in the *initializer* section, invoking a method in both the *initializer* and the *iterator* sections, and changing the values of two variables in the *iterator* section.</span></span> <span data-ttu-id="9cc72-140">Нажмите **Запустить** для выполнения примера кода.</span><span class="sxs-lookup"><span data-stu-id="9cc72-140">Select **Run** to run the example code.</span></span> <span data-ttu-id="9cc72-141">После этого можно изменить код и запустить его еще раз.</span><span class="sxs-lookup"><span data-stu-id="9cc72-141">After that you can modify the code and run it again.</span></span>
  
[!code-csharp-interactive[not typical for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#6)]
  
<span data-ttu-id="9cc72-142">В следующем примере определен бесконечный цикл `for`:</span><span class="sxs-lookup"><span data-stu-id="9cc72-142">The following example defines the infinite `for` loop:</span></span>
  
[!code-csharp[infinite for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#7)]
  
## <a name="c-language-specification"></a><span data-ttu-id="9cc72-143">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="9cc72-143">C# language specification</span></span>  

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]
  
## <a name="see-also"></a><span data-ttu-id="9cc72-144">См. также</span><span class="sxs-lookup"><span data-stu-id="9cc72-144">See also</span></span>

[<span data-ttu-id="9cc72-145">Оператор for (спецификация языка C#)</span><span class="sxs-lookup"><span data-stu-id="9cc72-145">The for statement (C# language specification)</span></span>](/dotnet/csharp/language-reference/language-specification/statements#the-for-statement)  
[<span data-ttu-id="9cc72-146">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="9cc72-146">C# Reference</span></span>](../index.md)  
[<span data-ttu-id="9cc72-147">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9cc72-147">C# Programming Guide</span></span>](../../programming-guide/index.md)  
[<span data-ttu-id="9cc72-148">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="9cc72-148">C# Keywords</span></span>](index.md)  
[<span data-ttu-id="9cc72-149">foreach, in</span><span class="sxs-lookup"><span data-stu-id="9cc72-149">foreach, in</span></span>](foreach-in.md)  
[<span data-ttu-id="9cc72-150">Оператор for (C++)</span><span class="sxs-lookup"><span data-stu-id="9cc72-150">for Statement (C++)</span></span>](/cpp/cpp/for-statement-cpp)  
[<span data-ttu-id="9cc72-151">Операторы итерации</span><span class="sxs-lookup"><span data-stu-id="9cc72-151">Iteration Statements</span></span>](iteration-statements.md)
