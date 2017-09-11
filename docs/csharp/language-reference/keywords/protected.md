---
title: "protected (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- protected
- protected_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
caps.latest.revision: 20
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
ms.openlocfilehash: c3d24389f66edec313d4f5238b0aee02518e33b7
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="protected-c-reference"></a><span data-ttu-id="53ce2-102">protected (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="53ce2-102">protected (C# Reference)</span></span>
<span data-ttu-id="53ce2-103">Ключевое слово `protected` является модификатором доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="53ce2-103">The `protected` keyword is a member access modifier.</span></span> <span data-ttu-id="53ce2-104">Доступ к защищенному элементу может быть получен из соответствующего класса, а также экземплярами производных классов.</span><span class="sxs-lookup"><span data-stu-id="53ce2-104">A protected member is accessible within its class and by derived class instances.</span></span> <span data-ttu-id="53ce2-105">Сравнение модификатора `protected` с другими модификаторами доступа см. в разделе [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="53ce2-105">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="53ce2-106">Пример</span><span class="sxs-lookup"><span data-stu-id="53ce2-106">Example</span></span>  
 <span data-ttu-id="53ce2-107">Доступ к защищенному элементу базового класса может быть получен в производном классе, только если доступ осуществляется через тип производного класса.</span><span class="sxs-lookup"><span data-stu-id="53ce2-107">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="53ce2-108">Для примера рассмотрим следующий сегмент кода:</span><span class="sxs-lookup"><span data-stu-id="53ce2-108">For example, consider the following code segment:</span></span>  
  
 <span data-ttu-id="53ce2-109">[!code-cs[csrefKeywordsModifiers#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="53ce2-109">[!code-cs[csrefKeywordsModifiers#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_1.cs)]</span></span>  
  
 <span data-ttu-id="53ce2-110">Оператор `a.x = 10` вызывает ошибку, поскольку выполняется в статическом методе Main, а не в экземпляре класса Б.</span><span class="sxs-lookup"><span data-stu-id="53ce2-110">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>  
  
 <span data-ttu-id="53ce2-111">Элементы структуры защитить нельзя, поскольку структура не может наследоваться.</span><span class="sxs-lookup"><span data-stu-id="53ce2-111">Struct members cannot be protected because the struct cannot be inherited.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53ce2-112">Пример</span><span class="sxs-lookup"><span data-stu-id="53ce2-112">Example</span></span>  
 <span data-ttu-id="53ce2-113">В этом примере класс `DerivedPoint` является производным от класса `Point`.</span><span class="sxs-lookup"><span data-stu-id="53ce2-113">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="53ce2-114">В связи с этим доступ к защищенным элементам базового класса можно получить напрямую из производного класса.</span><span class="sxs-lookup"><span data-stu-id="53ce2-114">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>  
  
 <span data-ttu-id="53ce2-115">[!code-cs[csrefKeywordsModifiers#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="53ce2-115">[!code-cs[csrefKeywordsModifiers#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_2.cs)]</span></span>  
  
 <span data-ttu-id="53ce2-116">Если изменить уровни доступа `x` и `y` на [private](../../../csharp/language-reference/keywords/private.md), компилятор выдаст сообщения об ошибках:</span><span class="sxs-lookup"><span data-stu-id="53ce2-116">If you change the access levels of `x` and `y` to [private](../../../csharp/language-reference/keywords/private.md), the compiler will issue the error messages:</span></span>  
  
 `'Point.y' is inaccessible due to its protection level.`  
  
 `'Point.x' is inaccessible due to its protection level.`  
  
## <a name="c-language-specification"></a><span data-ttu-id="53ce2-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="53ce2-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="53ce2-118">См. также</span><span class="sxs-lookup"><span data-stu-id="53ce2-118">See Also</span></span>  
 <span data-ttu-id="53ce2-119">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="53ce2-119">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="53ce2-120">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="53ce2-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="53ce2-121">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="53ce2-121">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="53ce2-122">[Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="53ce2-122">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="53ce2-123">[Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="53ce2-123">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="53ce2-124">[Модификаторы](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="53ce2-124">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="53ce2-125">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="53ce2-125">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="53ce2-126">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="53ce2-126">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 [<span data-ttu-id="53ce2-127">internal</span><span class="sxs-lookup"><span data-stu-id="53ce2-127">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)

