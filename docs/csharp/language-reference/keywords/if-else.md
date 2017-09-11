---
title: "if-else (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- if_CSharpKeyword
- else
- else_CSharpKeyword
- if
dev_langs:
- CSharp
helpviewer_keywords:
- else keyword [C#]
- if keyword [C#]
ms.assetid: d9a1d562-8cf5-4bd4-9ba7-8ad970cd25b2
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 694761a9b03fadf2dff97e61e37c0af52658f9e4
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="if-else-c-reference"></a><span data-ttu-id="5f965-102">if-else (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5f965-102">if-else (C# Reference)</span></span>
<span data-ttu-id="5f965-103">Оператор `if` определяет, какой оператор будет выполняться при выполнения условия, заданного выражением `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="5f965-103">An `if` statement identifies which statement to run based on the value of a `Boolean` expression.</span></span> <span data-ttu-id="5f965-104">В приведенном ниже примере переменной `Boolean` типа `result` присваивается значение `true` , а затем она проверяется оператором `if` .</span><span class="sxs-lookup"><span data-stu-id="5f965-104">In the following example, the `Boolean` variable `result` is set to `true` and then checked in the `if` statement.</span></span> <span data-ttu-id="5f965-105">В результате получается `The condition is true`.</span><span class="sxs-lookup"><span data-stu-id="5f965-105">The output is `The condition is true`.</span></span>  
  
 <span data-ttu-id="5f965-106">[!code-cs[csrefKeywordsSelection#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5f965-106">[!code-cs[csrefKeywordsSelection#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_1.cs)]</span></span>  
  
 <span data-ttu-id="5f965-107">Примеры в этом разделе можно выполнить, разместив их в методе `Main` консольного приложения.</span><span class="sxs-lookup"><span data-stu-id="5f965-107">You can run the examples in this topic by placing them in the `Main` method of a console app.</span></span>  
  
 <span data-ttu-id="5f965-108">Оператор `if` в С# может иметь две формы, как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="5f965-108">An `if` statement in C# can take two forms, as the following example shows.</span></span>  
  
```csharp  
// if-else statement  
if (condition)  
{  
    then-statement;  
}  
else  
{  
    else-statement;  
}  
// Next statement in the program.  
  
// if statement without an else  
if (condition)  
{  
    then-statement;  
}  
// Next statement in the program.  
```  
  
 <span data-ttu-id="5f965-109">В операторе `if-else` , если `condition` имеет значение true, выполняется `then-statement` .</span><span class="sxs-lookup"><span data-stu-id="5f965-109">In an `if-else` statement, if `condition` evaluates to true, the `then-statement` runs.</span></span> <span data-ttu-id="5f965-110">Если `condition` имеет значение false, выполняется `else-statement` .</span><span class="sxs-lookup"><span data-stu-id="5f965-110">If `condition` is false, the `else-statement` runs.</span></span> <span data-ttu-id="5f965-111">Так как `condition` не может одновременно иметь значения true и false, `then-statement` и `else-statement` оператора `if-else` не могут выполняться оба.</span><span class="sxs-lookup"><span data-stu-id="5f965-111">Because `condition` can’t be simultaneously true and false, the `then-statement` and the `else-statement` of an `if-else` statement can never both run.</span></span> <span data-ttu-id="5f965-112">После выполнения `then-statement` или `else-statement` управление передается следующему оператору после оператора `if` .</span><span class="sxs-lookup"><span data-stu-id="5f965-112">After the `then-statement` or the `else-statement` runs, control is transferred to the next statement after the `if` statement.</span></span>  
  
 <span data-ttu-id="5f965-113">В операторе `if` , не включающем оператор `else` , если `condition` имеет значение true, выполняется `then-statement` .</span><span class="sxs-lookup"><span data-stu-id="5f965-113">In an `if` statement that doesn’t include an `else` statement, if `condition` is true, the `then-statement` runs.</span></span> <span data-ttu-id="5f965-114">Если `condition` имеет значение false, то управление передается следующему оператору после оператора `if` .</span><span class="sxs-lookup"><span data-stu-id="5f965-114">If `condition` is false, control is transferred to the next statement after the `if` statement.</span></span>  
  
 <span data-ttu-id="5f965-115">`then-statement` и `else-statement` могут состоять из одного или нескольких операторов, заключенных в фигурные скобки (`{}`).</span><span class="sxs-lookup"><span data-stu-id="5f965-115">Both the `then-statement` and the `else-statement` can consist of a single statement or multiple statements that are enclosed in braces (`{}`).</span></span> <span data-ttu-id="5f965-116">Для одного оператора скобки необязательны, но рекомендуются.</span><span class="sxs-lookup"><span data-stu-id="5f965-116">For a single statement, the braces are optional but recommended.</span></span>  
  
 <span data-ttu-id="5f965-117">Оператор или операторы в `then-statement` и `else-statement` могут быть любого типа, включая другой оператор `if` , вложенный в исходный оператор `if` .</span><span class="sxs-lookup"><span data-stu-id="5f965-117">The statement or statements in the `then-statement` and the `else-statement` can be of any kind, including another `if` statement nested inside the original `if` statement.</span></span> <span data-ttu-id="5f965-118">Во вложенных операторах `if` каждое предложение `else` относится к последнему оператору `if` , у которого нет соответствующего объекта `else`.</span><span class="sxs-lookup"><span data-stu-id="5f965-118">In nested `if` statements, each `else` clause belongs to the last `if` that doesn’t have a corresponding `else`.</span></span> <span data-ttu-id="5f965-119">В приведенном ниже примере `Result1` получается, если оба выражения `m > 10` и `n > 20` имеют значение true.</span><span class="sxs-lookup"><span data-stu-id="5f965-119">In the following example, `Result1` appears if both `m > 10` and `n > 20` evaluate to true.</span></span> <span data-ttu-id="5f965-120">Если `m > 10` имеет значение true, но `n > 20` — значение false, то получается `Result2` .</span><span class="sxs-lookup"><span data-stu-id="5f965-120">If `m > 10` is true but `n > 20` is false, `Result2` appears.</span></span>  
  
 <span data-ttu-id="5f965-121">[!code-cs[csrefKeywordsSelection#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="5f965-121">[!code-cs[csrefKeywordsSelection#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_2.cs)]</span></span>  
  
 <span data-ttu-id="5f965-122">Если вместо этого нужно, чтобы `Result2` получался, когда значение `(m > 10)` равно false, можно указать такую связь с помощью фигурных скобок для задания начала и конца вложенного оператора `if` , как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="5f965-122">If, instead, you want `Result2` to appear when `(m > 10)` is false, you can specify that association by using braces to establish the start and end of the nested `if` statement, as the following example shows.</span></span>  
  
 <span data-ttu-id="5f965-123">[!code-cs[csrefKeywordsSelection#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="5f965-123">[!code-cs[csrefKeywordsSelection#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_3.cs)]</span></span>  
  
 <span data-ttu-id="5f965-124">`Result2` получается, если условие `(m > 10)` имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="5f965-124">`Result2` appears if the condition `(m > 10)` evaluates to false.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f965-125">Пример</span><span class="sxs-lookup"><span data-stu-id="5f965-125">Example</span></span>  
 <span data-ttu-id="5f965-126">В приведенном ниже примере вы вводите символ с помощью клавиатуры, а программа использует вложенный оператор `if` для определения того, является ли введенный символ буквой.</span><span class="sxs-lookup"><span data-stu-id="5f965-126">In the following example, you enter a character from the keyboard, and the program uses a nested `if` statement to determine whether the input character is an alphabetic character.</span></span> <span data-ttu-id="5f965-127">Если введенный символ является буквой, программа определяет его регистр.</span><span class="sxs-lookup"><span data-stu-id="5f965-127">If the input character is an alphabetic character, the program checks whether the input character is lowercase or uppercase.</span></span> <span data-ttu-id="5f965-128">Для каждого случая предусмотрено отдельное сообщение.</span><span class="sxs-lookup"><span data-stu-id="5f965-128">A message appears for each case.</span></span>  
  
 <span data-ttu-id="5f965-129">[!code-cs[csrefKeywordsSelection#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="5f965-129">[!code-cs[csrefKeywordsSelection#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_4.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f965-130">Пример</span><span class="sxs-lookup"><span data-stu-id="5f965-130">Example</span></span>  
 <span data-ttu-id="5f965-131">Также можно поместить оператор `if` в блок else, как показано в части кода, приведенной ниже.</span><span class="sxs-lookup"><span data-stu-id="5f965-131">You also can nest an `if` statement inside an else block, as the following partial code shows.</span></span> <span data-ttu-id="5f965-132">В примере операторы `if` помещаются в два блока else и один блок then.</span><span class="sxs-lookup"><span data-stu-id="5f965-132">The example nests `if` statements inside two else blocks and one then block.</span></span> <span data-ttu-id="5f965-133">Комментарии определяют какие условия выполняются в каждом из блоков.</span><span class="sxs-lookup"><span data-stu-id="5f965-133">The comments specify which conditions are true or false in each block.</span></span>  
  
 <span data-ttu-id="5f965-134">[!code-cs[csrefKeywordsSelection#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="5f965-134">[!code-cs[csrefKeywordsSelection#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_5.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f965-135">Пример</span><span class="sxs-lookup"><span data-stu-id="5f965-135">Example</span></span>  
 <span data-ttu-id="5f965-136">В приведенном ниже примере определяется, является ли введенный символ строчной буквой, прописной буквой или цифрой.</span><span class="sxs-lookup"><span data-stu-id="5f965-136">The following example determines whether an input character is a lowercase letter, an uppercase letter, or a number.</span></span> <span data-ttu-id="5f965-137">Если все три условия имеют значение false, то символ не является алфавитно-цифровым.</span><span class="sxs-lookup"><span data-stu-id="5f965-137">If all three conditions are false, the character isn’t an alphanumeric character.</span></span> <span data-ttu-id="5f965-138">Для каждого случая выводится сообщение.</span><span class="sxs-lookup"><span data-stu-id="5f965-138">The example displays a message for each case.</span></span>  
  
 <span data-ttu-id="5f965-139">[!code-cs[csrefKeywordsSelection#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="5f965-139">[!code-cs[csrefKeywordsSelection#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_6.cs)]</span></span>  
  
 <span data-ttu-id="5f965-140">Точно так же как оператор в блоке else или блоке then может быть любым допустимым оператором, в качестве условия можно использовать любое допустимое логическое выражение.</span><span class="sxs-lookup"><span data-stu-id="5f965-140">Just as a statement in the else block or the then block can be any valid statement, you can use any valid Boolean expression for the condition.</span></span> <span data-ttu-id="5f965-141">Можно использовать такие логические операторы, как [&&](../../../csharp/language-reference/operators/conditional-and-operator.md), [&](../../../csharp/language-reference/operators/and-operator.md), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md), [&#124;](../../../csharp/language-reference/operators/or-operator.md) и [!](../../../csharp/language-reference/operators/logical-negation-operator.md)</span><span class="sxs-lookup"><span data-stu-id="5f965-141">You can use logical operators such as [&&](../../../csharp/language-reference/operators/conditional-and-operator.md), [&](../../../csharp/language-reference/operators/and-operator.md), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md), [&#124;](../../../csharp/language-reference/operators/or-operator.md) and [!](../../../csharp/language-reference/operators/logical-negation-operator.md)</span></span> <span data-ttu-id="5f965-142">, для формирования составных условий.</span><span class="sxs-lookup"><span data-stu-id="5f965-142">to make compound conditions.</span></span> <span data-ttu-id="5f965-143">В коде ниже приведены примеры.</span><span class="sxs-lookup"><span data-stu-id="5f965-143">The following code shows examples.</span></span>  
  
```csharp  
// NOT  
bool result = true;  
if (!result)  
{  
    Console.WriteLine("The condition is true (result is false).");  
}  
else  
{  
    Console.WriteLine("The condition is false (result is true).");  
}  
  
// Short-circuit AND  
int m = 9;  
int n = 7;  
int p = 5;  
if (m >= n && m >= p)  
{  
    Console.WriteLine("Nothing is larger than m.");  
}  
  
// AND and NOT  
if (m >= n && !(p > m))  
{  
    Console.WriteLine("Nothing is larger than m.");  
}  
  
// Short-circuit OR  
if (m > n || m > p)  
{  
    Console.WriteLine("m isn't the smallest.");  
}  
  
// NOT and OR  
m = 4;  
if (!(m >= n || m >= p))  
{  
    Console.WriteLine("Now m is the smallest.");  
}  
// Output:  
// The condition is false (result is true).  
// Nothing is larger than m.  
// Nothing is larger than m.  
// m isn't the smallest.  
// Now m is the smallest.  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="5f965-144">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="5f965-144">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5f965-145">См. также</span><span class="sxs-lookup"><span data-stu-id="5f965-145">See Also</span></span>  
 <span data-ttu-id="5f965-146">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="5f965-146">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="5f965-147">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5f965-147">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5f965-148">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="5f965-148">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="5f965-149">[Оператор ?:](../../../csharp/language-reference/operators/conditional-operator.md) </span><span class="sxs-lookup"><span data-stu-id="5f965-149">[?: Operator](../../../csharp/language-reference/operators/conditional-operator.md) </span></span>  
 <span data-ttu-id="5f965-150">[Оператор if-else (C++)](/cpp/cpp/if-else-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="5f965-150">[if-else Statement (C++)](/cpp/cpp/if-else-statement-cpp) </span></span>  
 [<span data-ttu-id="5f965-151">switch</span><span class="sxs-lookup"><span data-stu-id="5f965-151">switch</span></span>](../../../csharp/language-reference/keywords/switch.md)

