---
title: "Структуры (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
caps.latest.revision: 31
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
ms.openlocfilehash: ce12f402c0748ea6729c82e3f188c0a58f63d628
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="60110-102">Структуры (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="60110-102">Structs (C# Programming Guide)</span></span>
<span data-ttu-id="60110-103">Структуры определяются с помощью ключевого слова [struct](../../../csharp/language-reference/keywords/struct.md), например:</span><span class="sxs-lookup"><span data-stu-id="60110-103">Structs are defined by using the [struct](../../../csharp/language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
 <span data-ttu-id="60110-104">[!code-cs[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="60110-104">[!code-cs[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]</span></span>  
  
 <span data-ttu-id="60110-105">Структуры используют большую часть того же синтаксиса, что и классы, однако они более ограничены по сравнению с ними.</span><span class="sxs-lookup"><span data-stu-id="60110-105">Structs share most of the same syntax as classes, although structs are more limited than classes:</span></span>  
  
-   <span data-ttu-id="60110-106">В объявлении структуры поля не могут быть инициализированы до тех пор, пока они будут объявлены как const или static.</span><span class="sxs-lookup"><span data-stu-id="60110-106">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
  
-   <span data-ttu-id="60110-107">Структура не может объявлять используемый по умолчанию конструктор (конструктор без параметров) или метод завершения.</span><span class="sxs-lookup"><span data-stu-id="60110-107">A struct cannot declare a default constructor (a constructor without parameters) or a finalizer.</span></span>  
  
-   <span data-ttu-id="60110-108">Структуры копируются при присваивании.</span><span class="sxs-lookup"><span data-stu-id="60110-108">Structs are copied on assignment.</span></span> <span data-ttu-id="60110-109">При присваивании структуры к новой переменной выполняется копирование всех данных, а любое изменение новой копии не влияет на данные в исходной копии.</span><span class="sxs-lookup"><span data-stu-id="60110-109">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="60110-110">Это важно помнить при работе с коллекциями типов значений, такими как Dictionary\<string, myStruct>.</span><span class="sxs-lookup"><span data-stu-id="60110-110">This is important to remember when working with collections of value types such as Dictionary\<string, myStruct>.</span></span>  
  
-   <span data-ttu-id="60110-111">Структуры являются типами значений, а классы — ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="60110-111">Structs are value types and classes are reference types.</span></span>  
  
-   <span data-ttu-id="60110-112">В отличие от классов структуры можно создавать без использования оператора `new`.</span><span class="sxs-lookup"><span data-stu-id="60110-112">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
  
-   <span data-ttu-id="60110-113">Структуры могут объявлять конструкторы, имеющие параметры.</span><span class="sxs-lookup"><span data-stu-id="60110-113">Structs can declare constructors that have parameters.</span></span>  
  
-   <span data-ttu-id="60110-114">Структура не может наследовать от другой структуры или класса и не может быть базовой для класса.</span><span class="sxs-lookup"><span data-stu-id="60110-114">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="60110-115">Все структуры наследуют непосредственно от `System.ValueType`, который наследует от `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="60110-115">All structs inherit directly from `System.ValueType`, which inherits from `System.Object`.</span></span>  
  
-   <span data-ttu-id="60110-116">Структуры могут реализовывать интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="60110-116">A struct can implement interfaces.</span></span>  
  
-   <span data-ttu-id="60110-117">Структура может использоваться как тип, допускающий значение NULL, и ей можно назначить значение NULL.</span><span class="sxs-lookup"><span data-stu-id="60110-117">A struct can be used as a nullable type and can be assigned a null value.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="60110-118">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="60110-118">Related Sections</span></span>  
 <span data-ttu-id="60110-119">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="60110-119">For more information:</span></span>  
  
-   [<span data-ttu-id="60110-120">Использование структур</span><span class="sxs-lookup"><span data-stu-id="60110-120">Using Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [<span data-ttu-id="60110-121">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="60110-121">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [<span data-ttu-id="60110-122">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="60110-122">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [<span data-ttu-id="60110-123">Практическое руководство. Определение различия между передачей структуры и ссылки класса в метод</span><span class="sxs-lookup"><span data-stu-id="60110-123">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [<span data-ttu-id="60110-124">Практическое руководство. Реализация определенных пользователем преобразований между структурами</span><span class="sxs-lookup"><span data-stu-id="60110-124">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
## <a name="see-also"></a><span data-ttu-id="60110-125">См. также</span><span class="sxs-lookup"><span data-stu-id="60110-125">See Also</span></span>  
 <span data-ttu-id="60110-126">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="60110-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="60110-127">[Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="60110-127">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 [<span data-ttu-id="60110-128">Классы</span><span class="sxs-lookup"><span data-stu-id="60110-128">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)

