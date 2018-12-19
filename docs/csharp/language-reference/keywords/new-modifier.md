---
title: Справочник по C#. Модификатор new
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- new modifier keyword [C#]
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
ms.openlocfilehash: 07986ac0c49387422aa334711b6997b159151e79
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244971"
---
# <a name="new-modifier-c-reference"></a><span data-ttu-id="e6092-102">Модификатор new (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e6092-102">new modifier (C# Reference)</span></span>

<span data-ttu-id="e6092-103">При использовании в качестве модификатора объявления ключевое слово `new` явным образом скрывает члены, унаследованные от базового класса.</span><span class="sxs-lookup"><span data-stu-id="e6092-103">When used as a declaration modifier, the `new` keyword explicitly hides a member that is inherited from a base class.</span></span> <span data-ttu-id="e6092-104">При скрытии унаследованного члена его производная версия заменяет версию базового класса.</span><span class="sxs-lookup"><span data-stu-id="e6092-104">When you hide an inherited member, the derived version of the member replaces the base class version.</span></span> <span data-ttu-id="e6092-105">Хотя члены можно скрывать без использования модификатора `new`, в этом случае появляется предупреждение компилятора.</span><span class="sxs-lookup"><span data-stu-id="e6092-105">Although you can hide members without using the `new` modifier, you get a compiler warning.</span></span> <span data-ttu-id="e6092-106">При использовании `new` для явного скрытия члена, предупреждение не появляется.</span><span class="sxs-lookup"><span data-stu-id="e6092-106">If you use `new` to explicitly hide a member, it suppresses this warning.</span></span>

<span data-ttu-id="e6092-107">Чтобы скрыть унаследованный член, объявите его в производном классе с использованием такого же имени члена и измените с помощью ключевого слова `new`.</span><span class="sxs-lookup"><span data-stu-id="e6092-107">To hide an inherited member, declare it in the derived class by using the same member name, and modify it with the `new` keyword.</span></span> <span data-ttu-id="e6092-108">Например:</span><span class="sxs-lookup"><span data-stu-id="e6092-108">For example:</span></span>

[!code-csharp[csrefKeywordsOperator#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#8)]

<span data-ttu-id="e6092-109">В этом примере `BaseC.Invoke` скрывается с помощью `DerivedC.Invoke`.</span><span class="sxs-lookup"><span data-stu-id="e6092-109">In this example, `BaseC.Invoke` is hidden by `DerivedC.Invoke`.</span></span> <span data-ttu-id="e6092-110">Поле `x` не затрагивается, поскольку оно не скрыто таким же именем.</span><span class="sxs-lookup"><span data-stu-id="e6092-110">The field `x` is not affected because it is not hidden by a similar name.</span></span>

<span data-ttu-id="e6092-111">Скрытие имен через наследование принимает одну из следующих форм.</span><span class="sxs-lookup"><span data-stu-id="e6092-111">Name hiding through inheritance takes one of the following forms:</span></span>

<span data-ttu-id="e6092-112">Как правило, константы, поля, свойства и типы, которые вводятся в классе или структуре, скрывают все члены базового класса с таким же именем.</span><span class="sxs-lookup"><span data-stu-id="e6092-112">Generally, a constant, field, property, or type that is introduced in a class or struct hides all base class members that share its name.</span></span>  <span data-ttu-id="e6092-113">Однако существуют особые случаи.</span><span class="sxs-lookup"><span data-stu-id="e6092-113">There are special cases.</span></span>  <span data-ttu-id="e6092-114">Например, если объявить новое поле с именем `N`, чтобы сделать тип невызываемым, в то время как в базовом типе был объявлен метод `N`, новое поле не скрывает базовое объявление в синтаксисе вызова.</span><span class="sxs-lookup"><span data-stu-id="e6092-114">For example, if you declare a new field with name `N` to have a type that is not invocable, and a base type declares `N` to be a method, the new field does not hide the base declaration in invocation syntax.</span></span>  <span data-ttu-id="e6092-115">Подробные сведения см. в разделе [Спецификация языка C# 5.0](https://www.microsoft.com/download/details.aspx?id=7029) (подраздел "Поиск элемента" в разделе "Выражения").</span><span class="sxs-lookup"><span data-stu-id="e6092-115">See the [C# 5.0 language specification](https://www.microsoft.com/download/details.aspx?id=7029) for details (see section "Member Lookup" in section "Expressions").</span></span>

<span data-ttu-id="e6092-116">Метод, введенный в классе или структуре, скрывает свойства, поля и типы с тем же именем в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="e6092-116">A method introduced in a class or struct hides properties, fields, and types that share that name in the base class.</span></span> <span data-ttu-id="e6092-117">Кроме того, он также скрывает все методы базового класса, имеющие такую же сигнатуру.</span><span class="sxs-lookup"><span data-stu-id="e6092-117">It also hides all base class methods that have the same signature.</span></span>

<span data-ttu-id="e6092-118">Индексатор, представленный в классе или структуре, скрывает все индексаторы базового класса, имеющие одинаковую сигнатуру.</span><span class="sxs-lookup"><span data-stu-id="e6092-118">An indexer introduced in a class or struct hides all base class indexers that have the same signature.</span></span>

<span data-ttu-id="e6092-119">Совместное использование модификаторов `new` и [override](override.md) в одном члене является недопустимым, так как эти два модификатора имеют взаимоисключающие значения.</span><span class="sxs-lookup"><span data-stu-id="e6092-119">It is an error to use both `new` and [override](override.md) on the same member, because the two modifiers have mutually exclusive meanings.</span></span> <span data-ttu-id="e6092-120">Модификатор `new` создает новый член с таким же именем и приводит к скрытию исходного члена.</span><span class="sxs-lookup"><span data-stu-id="e6092-120">The `new` modifier creates a new member with the same name and causes the original member to become hidden.</span></span> <span data-ttu-id="e6092-121">Модификатор `override` расширяет реализацию для наследуемого члена.</span><span class="sxs-lookup"><span data-stu-id="e6092-121">The `override` modifier extends the implementation for an inherited member.</span></span>

<span data-ttu-id="e6092-122">При использовании модификатора `new` в объявлении, которое не скрывает наследуемый член, возникает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="e6092-122">Using the `new` modifier in a declaration that does not hide an inherited member generates a warning.</span></span>

## <a name="example"></a><span data-ttu-id="e6092-123">Пример</span><span class="sxs-lookup"><span data-stu-id="e6092-123">Example</span></span>

<span data-ttu-id="e6092-124">В этом примере базовый класс `BaseC` и производный класс `DerivedC` используют одно и то же имя поля `x`, которое скрывает значение унаследованного поля.</span><span class="sxs-lookup"><span data-stu-id="e6092-124">In this example, a base class, `BaseC`, and a derived class, `DerivedC`, use the same field name `x`, which hides the value of the inherited field.</span></span> <span data-ttu-id="e6092-125">В примере показано использование модификатора `new`.</span><span class="sxs-lookup"><span data-stu-id="e6092-125">The example demonstrates the use of the `new` modifier.</span></span> <span data-ttu-id="e6092-126">Здесь также показано обращение к скрытым членам базового класса с помощью их полных имен.</span><span class="sxs-lookup"><span data-stu-id="e6092-126">It also demonstrates how to access the hidden members of the base class by using their fully qualified names.</span></span>

[!code-csharp[csrefKeywordsOperator#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#9)]

## <a name="example"></a><span data-ttu-id="e6092-127">Пример</span><span class="sxs-lookup"><span data-stu-id="e6092-127">Example</span></span>

<span data-ttu-id="e6092-128">В этом примере вложенный класс скрывает класс, имеющий такое же имя в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="e6092-128">In this example, a nested class hides a class that has the same name in the base class.</span></span> <span data-ttu-id="e6092-129">Здесь показано использование модификатора `new` для исключения предупреждений, а также обращение к членам скрытого класса с помощью их полных имен.</span><span class="sxs-lookup"><span data-stu-id="e6092-129">The example demonstrates how to use the `new` modifier to eliminate the warning message and how to access the hidden class members by using their fully qualified names.</span></span>

[!code-csharp[csrefKeywordsOperator#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#10)]

<span data-ttu-id="e6092-130">В случае удаления модификатора `new` программа продолжит компиляцию и выполнение, однако появится следующее предупреждение.</span><span class="sxs-lookup"><span data-stu-id="e6092-130">If you remove the `new` modifier, the program will still compile and run, but you will get the following warning:</span></span>

```
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.
```

## <a name="c-language-specification"></a><span data-ttu-id="e6092-131">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="e6092-131">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="e6092-132">См. также</span><span class="sxs-lookup"><span data-stu-id="e6092-132">See also</span></span>

- [<span data-ttu-id="e6092-133">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="e6092-133">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="e6092-134">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e6092-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e6092-135">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="e6092-135">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="e6092-136">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="e6092-136">Operator Keywords</span></span>](operator-keywords.md)
- [<span data-ttu-id="e6092-137">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="e6092-137">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="e6092-138">Управление версиями с помощью ключевых слов Override и New</span><span class="sxs-lookup"><span data-stu-id="e6092-138">Versioning with the Override and New Keywords</span></span>](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)
- [<span data-ttu-id="e6092-139">Использование ключевых слов Override и New</span><span class="sxs-lookup"><span data-stu-id="e6092-139">Knowing When to Use Override and New Keywords</span></span>](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)
