---
title: "readonly (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 175eebf6e49e79db1ff86689599416a10827a792
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
# <a name="readonly-c-reference"></a><span data-ttu-id="abea2-102">readonly (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="abea2-102">readonly (C# Reference)</span></span>
<span data-ttu-id="abea2-103">Ключевое слово `readonly` — это модификатор, который можно использовать для полей.</span><span class="sxs-lookup"><span data-stu-id="abea2-103">The `readonly` keyword is a modifier that you can use on fields.</span></span> <span data-ttu-id="abea2-104">Если объявление поля содержит модификатор `readonly`, присвоение значений таким полям может происходить только как часть объявления или в конструкторе в том же классе.</span><span class="sxs-lookup"><span data-stu-id="abea2-104">When a field declaration includes a `readonly` modifier, assignments to the fields introduced by the declaration can only occur as part of the declaration or in a constructor in the same class.</span></span>  
  
## <a name="readonly-field-example"></a><span data-ttu-id="abea2-105">Пример поля только для чтения</span><span class="sxs-lookup"><span data-stu-id="abea2-105">Readonly field example</span></span>  
 <span data-ttu-id="abea2-106">В этом примере значение поля `year` нельзя изменить в методе `ChangeYear`, несмотря на то, что в конструкторе класса ему присваивается значение:</span><span class="sxs-lookup"><span data-stu-id="abea2-106">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]  
  
 <span data-ttu-id="abea2-107">Можно присвоить значение полю `readonly` только в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="abea2-107">You can assign a value to a `readonly` field only in the following contexts:</span></span>  
  
-   <span data-ttu-id="abea2-108">Когда переменная инициализируется в объявлении, например:</span><span class="sxs-lookup"><span data-stu-id="abea2-108">When the variable is initialized in the declaration, for example:</span></span>  
  
    ```  
    public readonly int y = 5;  
    ```  
  
-   <span data-ttu-id="abea2-109">Для поля экземпляра — в конструкторах экземпляров класса, содержащего объявление поля, или, для статического поля, — в статическом конструкторе класса, содержащего объявление поля.</span><span class="sxs-lookup"><span data-stu-id="abea2-109">For an instance field, in the instance constructors of the class that contains the field declaration, or for a static field, in the static constructor of the class that contains the field declaration.</span></span> <span data-ttu-id="abea2-110">Это единственно возможные контексты, в которых можно передавать поле `readonly` в качестве параметра [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) или [ref](../../../csharp/language-reference/keywords/ref.md).</span><span class="sxs-lookup"><span data-stu-id="abea2-110">These are also the only contexts in which it is valid to pass a `readonly` field as an [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) or [ref](../../../csharp/language-reference/keywords/ref.md) parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abea2-111">Ключевое слово `readonly` отличается от ключевого слова [const](../../../csharp/language-reference/keywords/const.md).</span><span class="sxs-lookup"><span data-stu-id="abea2-111">The `readonly` keyword is different from the [const](../../../csharp/language-reference/keywords/const.md) keyword.</span></span> <span data-ttu-id="abea2-112">Поле `const` может быть инициализировано только при объявлении поля.</span><span class="sxs-lookup"><span data-stu-id="abea2-112">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="abea2-113">Поле `readonly` может быть инициализировано при объявлении или в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="abea2-113">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="abea2-114">Таким образом, поля `readonly` могут иметь разные значения в зависимости от использованного конструктора.</span><span class="sxs-lookup"><span data-stu-id="abea2-114">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="abea2-115">К тому же, в то время как поле `const` является константой во время компиляции, поле `readonly` можно использовать для констант во время выполнения, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="abea2-115">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>  
  
```  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## <a name="comparing-readonly-and-non-readonly-instance-fields"></a><span data-ttu-id="abea2-116">Сравнение полей экземпляров, доступных только для чтения и не только для чтения</span><span class="sxs-lookup"><span data-stu-id="abea2-116">Comparing readonly and non-readonly instance fields</span></span>  
 [!code-csharp[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]  
  
 <span data-ttu-id="abea2-117">В предыдущем примере при использовании такого оператора:</span><span class="sxs-lookup"><span data-stu-id="abea2-117">In the preceding example, if you use a statement like this:</span></span>  
  
 `p2.y = 66;        // Error`  
  
 <span data-ttu-id="abea2-118">будет отображено сообщение об ошибке компилятора:</span><span class="sxs-lookup"><span data-stu-id="abea2-118">you will get the compiler error message:</span></span>  
  
 `The left-hand side of an assignment must be an l-value`  
  
 <span data-ttu-id="abea2-119">Это такая же ошибка, которая возникает при попытке присвоить значение константе.</span><span class="sxs-lookup"><span data-stu-id="abea2-119">which is the same error you get when you attempt to assign a value to a constant.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="abea2-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="abea2-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="abea2-121">См. также</span><span class="sxs-lookup"><span data-stu-id="abea2-121">See Also</span></span>  
 [<span data-ttu-id="abea2-122">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="abea2-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="abea2-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="abea2-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="abea2-124">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="abea2-124">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="abea2-125">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="abea2-125">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="abea2-126">const</span><span class="sxs-lookup"><span data-stu-id="abea2-126">const</span></span>](../../../csharp/language-reference/keywords/const.md)  
 [<span data-ttu-id="abea2-127">Поля</span><span class="sxs-lookup"><span data-stu-id="abea2-127">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)
