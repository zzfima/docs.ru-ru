---
title: "Модификатор new (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- new modifier keyword [C#]
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f763b9a1d2f146b8ebb475a01bd12f1a4238050a
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="new-modifier-c-reference"></a><span data-ttu-id="27271-102">Модификатор new (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="27271-102">new Modifier (C# Reference)</span></span>
<span data-ttu-id="27271-103">При использовании в качестве модификатора объявления ключевое слово `new` явным образом скрывает члены, унаследованные от базового класса.</span><span class="sxs-lookup"><span data-stu-id="27271-103">When used as a declaration modifier, the `new` keyword explicitly hides a member that is inherited from a base class.</span></span> <span data-ttu-id="27271-104">При скрытии унаследованного члена его производная версия заменяет версию базового класса.</span><span class="sxs-lookup"><span data-stu-id="27271-104">When you hide an inherited member, the derived version of the member replaces the base class version.</span></span> <span data-ttu-id="27271-105">Хотя члены можно скрывать без использования модификатора `new`, в этом случае появляется предупреждение компилятора.</span><span class="sxs-lookup"><span data-stu-id="27271-105">Although you can hide members without using the `new` modifier, you get a compiler warning.</span></span> <span data-ttu-id="27271-106">При использовании `new` для явного скрытия члена, предупреждение не появляется.</span><span class="sxs-lookup"><span data-stu-id="27271-106">If you use `new` to explicitly hide a member, it suppresses this warning.</span></span>  
  
 <span data-ttu-id="27271-107">Чтобы скрыть унаследованный член, объявите его в производном классе с использованием такого же имени члена и измените с помощью ключевого слова `new`.</span><span class="sxs-lookup"><span data-stu-id="27271-107">To hide an inherited member, declare it in the derived class by using the same member name, and modify it with the `new` keyword.</span></span> <span data-ttu-id="27271-108">Пример:</span><span class="sxs-lookup"><span data-stu-id="27271-108">For example:</span></span>  
  
 <span data-ttu-id="27271-109">[!code-cs[csrefKeywordsOperator#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="27271-109">[!code-cs[csrefKeywordsOperator#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_1.cs)]</span></span>  
  
 <span data-ttu-id="27271-110">В этом примере `BaseC.Invoke` скрывается с помощью `DerivedC.Invoke`.</span><span class="sxs-lookup"><span data-stu-id="27271-110">In this example, `BaseC.Invoke` is hidden by `DerivedC.Invoke`.</span></span> <span data-ttu-id="27271-111">Поле `x` не затрагивается, поскольку оно не скрыто таким же именем.</span><span class="sxs-lookup"><span data-stu-id="27271-111">The field `x` is not affected because it is not hidden by a similar name.</span></span>  
  
 <span data-ttu-id="27271-112">Скрытие имен через наследование принимает одну из следующих форм.</span><span class="sxs-lookup"><span data-stu-id="27271-112">Name hiding through inheritance takes one of the following forms:</span></span>  
  
-   <span data-ttu-id="27271-113">Как правило, константы, поля, свойства и типы, которые вводятся в классе или структуре, скрывают все члены базового класса с таким же именем.</span><span class="sxs-lookup"><span data-stu-id="27271-113">Generally, a constant, field, property, or type that is introduced in a class or struct hides all base class members that share its name.</span></span>  <span data-ttu-id="27271-114">Однако существуют особые случаи.</span><span class="sxs-lookup"><span data-stu-id="27271-114">There are special cases.</span></span>  <span data-ttu-id="27271-115">Например, если объявить новое поле с именем `N`, чтобы сделать тип невызываемым, в то время как в базовом типе был объявлен метод `N`, новое поле не скрывает базовое объявление в синтаксисе вызова.</span><span class="sxs-lookup"><span data-stu-id="27271-115">For example, if you declare a new field with name `N` to have a type that is not invocable, and a base type declares `N` to be a method, the new field does not hide the base declaration in invocation syntax.</span></span>  <span data-ttu-id="27271-116">Подробные сведения см. в разделе [Спецификация языка C#](http://go.microsoft.com/fwlink/?LinkId=199552) (подраздел "Поиск члена" в разделе "Выражения").</span><span class="sxs-lookup"><span data-stu-id="27271-116">See the [C# language specification](http://go.microsoft.com/fwlink/?LinkId=199552) for details (see section "Member Lookup" in section "Expressions").</span></span>  
  
-   <span data-ttu-id="27271-117">Метод, введенный в классе или структуре, скрывает свойства, поля и типы с тем же именем в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="27271-117">A method introduced in a class or struct hides properties, fields, and types that share that name in the base class.</span></span> <span data-ttu-id="27271-118">Кроме того, он также скрывает все методы базового класса, имеющие такую же сигнатуру.</span><span class="sxs-lookup"><span data-stu-id="27271-118">It also hides all base class methods that have the same signature.</span></span>  
  
-   <span data-ttu-id="27271-119">Индексатор, представленный в классе или структуре, скрывает все индексаторы базового класса, имеющие одинаковую сигнатуру.</span><span class="sxs-lookup"><span data-stu-id="27271-119">An indexer introduced in a class or struct hides all base class indexers that have the same signature.</span></span>  
  
 <span data-ttu-id="27271-120">Совместное использование модификаторов `new` и [override](../../../csharp/language-reference/keywords/override.md) в одном члене является недопустимым, так как эти два модификатора имеют взаимоисключающие значения.</span><span class="sxs-lookup"><span data-stu-id="27271-120">It is an error to use both `new` and [override](../../../csharp/language-reference/keywords/override.md) on the same member, because the two modifiers have mutually exclusive meanings.</span></span> <span data-ttu-id="27271-121">Модификатор `new` создает новый член с таким же именем и приводит к скрытию исходного члена.</span><span class="sxs-lookup"><span data-stu-id="27271-121">The `new` modifier creates a new member with the same name and causes the original member to become hidden.</span></span> <span data-ttu-id="27271-122">Модификатор `override` расширяет реализацию для наследуемого члена.</span><span class="sxs-lookup"><span data-stu-id="27271-122">The `override` modifier extends the implementation for an inherited member.</span></span>  
  
 <span data-ttu-id="27271-123">При использовании модификатора `new` в объявлении, которое не скрывает наследуемый член, возникает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="27271-123">Using the `new` modifier in a declaration that does not hide an inherited member generates a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27271-124">Пример</span><span class="sxs-lookup"><span data-stu-id="27271-124">Example</span></span>  
 <span data-ttu-id="27271-125">В этом примере базовый класс `BaseC` и производный класс `DerivedC` используют одно и то же имя поля `x`, которое скрывает значение унаследованного поля.</span><span class="sxs-lookup"><span data-stu-id="27271-125">In this example, a base class, `BaseC`, and a derived class, `DerivedC`, use the same field name `x`, which hides the value of the inherited field.</span></span> <span data-ttu-id="27271-126">В примере показано использование модификатора `new`.</span><span class="sxs-lookup"><span data-stu-id="27271-126">The example demonstrates the use of the `new` modifier.</span></span> <span data-ttu-id="27271-127">Здесь также показано обращение к скрытым членам базового класса с помощью их полных имен.</span><span class="sxs-lookup"><span data-stu-id="27271-127">It also demonstrates how to access the hidden members of the base class by using their fully qualified names.</span></span>  
  
 <span data-ttu-id="27271-128">[!code-cs[csrefKeywordsOperator#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="27271-128">[!code-cs[csrefKeywordsOperator#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="27271-129">Пример</span><span class="sxs-lookup"><span data-stu-id="27271-129">Example</span></span>  
 <span data-ttu-id="27271-130">В этом примере вложенный класс скрывает класс, имеющий такое же имя в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="27271-130">In this example, a nested class hides a class that has the same name in the base class.</span></span> <span data-ttu-id="27271-131">Здесь показано использование модификатора `new` для исключения предупреждений, а также обращение к членам скрытого класса с помощью их полных имен.</span><span class="sxs-lookup"><span data-stu-id="27271-131">The example demonstrates how to use the `new` modifier to eliminate the warning message and how to access the hidden class members by using their fully qualified names.</span></span>  
  
 <span data-ttu-id="27271-132">[!code-cs[csrefKeywordsOperator#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="27271-132">[!code-cs[csrefKeywordsOperator#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_3.cs)]</span></span>  
  
 <span data-ttu-id="27271-133">В случае удаления модификатора `new` программа продолжит компиляцию и выполнение, однако появится следующее предупреждение.</span><span class="sxs-lookup"><span data-stu-id="27271-133">If you remove the `new` modifier, the program will still compile and run, but you will get the following warning:</span></span>  
  
```  
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="27271-134">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="27271-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="27271-135">См. также</span><span class="sxs-lookup"><span data-stu-id="27271-135">See Also</span></span>  
 <span data-ttu-id="27271-136">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="27271-136">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="27271-137">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="27271-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="27271-138">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="27271-138">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="27271-139">[Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="27271-139">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md) </span></span>  
 <span data-ttu-id="27271-140">[Модификаторы](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="27271-140">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="27271-141">[Управление версиями с помощью ключевых слов Override и New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="27271-141">[Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) </span></span>  
 [<span data-ttu-id="27271-142">Использование ключевых слов Override и New</span><span class="sxs-lookup"><span data-stu-id="27271-142">Knowing When to Use Override and New Keywords</span></span>](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)

