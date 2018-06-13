---
title: Структуры (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: ffb5b8da6c72056620cf890f38af4e7a8116ab3e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322992"
---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="f40a9-102">Структуры (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f40a9-102">Structs (C# Programming Guide)</span></span>
<span data-ttu-id="f40a9-103">Структуры определяются с помощью ключевого слова [struct](../../../csharp/language-reference/keywords/struct.md), например:</span><span class="sxs-lookup"><span data-stu-id="f40a9-103">Structs are defined by using the [struct](../../../csharp/language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]  
  
 <span data-ttu-id="f40a9-104">Структуры используют большую часть того же синтаксиса, что и классы, однако они более ограничены по сравнению с ними.</span><span class="sxs-lookup"><span data-stu-id="f40a9-104">Structs share most of the same syntax as classes, although structs are more limited than classes:</span></span>  
  
-   <span data-ttu-id="f40a9-105">В объявлении структуры поля не могут быть инициализированы до тех пор, пока они будут объявлены как const или static.</span><span class="sxs-lookup"><span data-stu-id="f40a9-105">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
  
-   <span data-ttu-id="f40a9-106">Структура не может объявлять используемый по умолчанию конструктор (конструктор без параметров) или метод завершения.</span><span class="sxs-lookup"><span data-stu-id="f40a9-106">A struct cannot declare a default constructor (a constructor without parameters) or a finalizer.</span></span>  
  
-   <span data-ttu-id="f40a9-107">Структуры копируются при присваивании.</span><span class="sxs-lookup"><span data-stu-id="f40a9-107">Structs are copied on assignment.</span></span> <span data-ttu-id="f40a9-108">При присваивании структуры к новой переменной выполняется копирование всех данных, а любое изменение новой копии не влияет на данные в исходной копии.</span><span class="sxs-lookup"><span data-stu-id="f40a9-108">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="f40a9-109">Это важно помнить при работе с коллекциями типов значений, такими как Dictionary\<string, myStruct>.</span><span class="sxs-lookup"><span data-stu-id="f40a9-109">This is important to remember when working with collections of value types such as Dictionary\<string, myStruct>.</span></span>  
  
-   <span data-ttu-id="f40a9-110">Структуры являются типами значений, а классы — ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="f40a9-110">Structs are value types and classes are reference types.</span></span>  
  
-   <span data-ttu-id="f40a9-111">В отличие от классов структуры можно создавать без использования оператора `new`.</span><span class="sxs-lookup"><span data-stu-id="f40a9-111">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
  
-   <span data-ttu-id="f40a9-112">Структуры могут объявлять конструкторы, имеющие параметры.</span><span class="sxs-lookup"><span data-stu-id="f40a9-112">Structs can declare constructors that have parameters.</span></span>  
  
-   <span data-ttu-id="f40a9-113">Структура не может наследовать от другой структуры или класса и не может быть базовой для класса.</span><span class="sxs-lookup"><span data-stu-id="f40a9-113">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="f40a9-114">Все структуры наследуют непосредственно от `System.ValueType`, который наследует от `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="f40a9-114">All structs inherit directly from `System.ValueType`, which inherits from `System.Object`.</span></span>  
  
-   <span data-ttu-id="f40a9-115">Структуры могут реализовывать интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="f40a9-115">A struct can implement interfaces.</span></span>  
  
-   <span data-ttu-id="f40a9-116">Структура может использоваться как тип, допускающий значение NULL, и ей можно назначить значение NULL.</span><span class="sxs-lookup"><span data-stu-id="f40a9-116">A struct can be used as a nullable type and can be assigned a null value.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f40a9-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="f40a9-117">Related Sections</span></span>  
 <span data-ttu-id="f40a9-118">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="f40a9-118">For more information:</span></span>  
  
-   [<span data-ttu-id="f40a9-119">Использование структур</span><span class="sxs-lookup"><span data-stu-id="f40a9-119">Using Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [<span data-ttu-id="f40a9-120">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="f40a9-120">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [<span data-ttu-id="f40a9-121">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="f40a9-121">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [<span data-ttu-id="f40a9-122">Практическое руководство. Определение различия между передачей структуры и ссылки класса в метод</span><span class="sxs-lookup"><span data-stu-id="f40a9-122">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [<span data-ttu-id="f40a9-123">Практическое руководство. Реализация определенных пользователем преобразований между структурами</span><span class="sxs-lookup"><span data-stu-id="f40a9-123">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
## <a name="see-also"></a><span data-ttu-id="f40a9-124">См. также</span><span class="sxs-lookup"><span data-stu-id="f40a9-124">See Also</span></span>  
 [<span data-ttu-id="f40a9-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f40a9-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f40a9-126">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="f40a9-126">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="f40a9-127">Классы</span><span class="sxs-lookup"><span data-stu-id="f40a9-127">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)
