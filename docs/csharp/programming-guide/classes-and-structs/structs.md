---
title: Руководство по программированию на C#. Структуры
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: 063d7e3b68fbe6c01ff0df4ae935fec5af6f6891
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743847"
---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="03518-102">Структуры (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="03518-102">Structs (C# Programming Guide)</span></span>

<span data-ttu-id="03518-103">Структуры определяются с помощью ключевого слова [struct](../../language-reference/keywords/struct.md), например:</span><span class="sxs-lookup"><span data-stu-id="03518-103">Structs are defined by using the [struct](../../language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#39)]  
  
<span data-ttu-id="03518-104">Структуры используют большую часть того же синтаксиса, что и классы.</span><span class="sxs-lookup"><span data-stu-id="03518-104">Structs share most of the same syntax as classes.</span></span> <span data-ttu-id="03518-105">Имя структуры должно быть допустимым [именем идентификатора](../inside-a-program/identifier-names.md) C#.</span><span class="sxs-lookup"><span data-stu-id="03518-105">The name of the struct must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span> <span data-ttu-id="03518-106">Структуры более ограничены по сравнению с классами по следующим причинам.</span><span class="sxs-lookup"><span data-stu-id="03518-106">Structs are more limited than classes in the following ways:</span></span>  
  
- <span data-ttu-id="03518-107">В объявлении структуры поля не могут быть инициализированы до тех пор, пока они будут объявлены как const или static.</span><span class="sxs-lookup"><span data-stu-id="03518-107">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
- <span data-ttu-id="03518-108">Структура не может объявлять конструктор без параметров или метод завершения.</span><span class="sxs-lookup"><span data-stu-id="03518-108">A struct cannot declare a parameterless constructor (a constructor without parameters) or a finalizer.</span></span>  
- <span data-ttu-id="03518-109">Структуры копируются при присваивании.</span><span class="sxs-lookup"><span data-stu-id="03518-109">Structs are copied on assignment.</span></span> <span data-ttu-id="03518-110">При присваивании структуры к новой переменной выполняется копирование всех данных, а любое изменение новой копии не влияет на данные в исходной копии.</span><span class="sxs-lookup"><span data-stu-id="03518-110">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="03518-111">Это важно помнить при работе с коллекциями типов значений, такими как `Dictionary<string, myStruct>`.</span><span class="sxs-lookup"><span data-stu-id="03518-111">This is important to remember when working with collections of value types such as `Dictionary<string, myStruct>`.</span></span>  
- <span data-ttu-id="03518-112">Структуры являются типами значений, а классы — ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="03518-112">Structs are value types, unlike classes, which are reference types.</span></span>  
- <span data-ttu-id="03518-113">В отличие от классов структуры можно создавать без использования оператора `new`.</span><span class="sxs-lookup"><span data-stu-id="03518-113">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
- <span data-ttu-id="03518-114">Структуры могут объявлять конструкторы, имеющие параметры.</span><span class="sxs-lookup"><span data-stu-id="03518-114">Structs can declare constructors that have parameters.</span></span>
- <span data-ttu-id="03518-115">Структура не может наследовать от другой структуры или класса и не может быть базовой для класса.</span><span class="sxs-lookup"><span data-stu-id="03518-115">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="03518-116">Все структуры наследуют непосредственно от <xref:System.ValueType>, который наследует от <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="03518-116">All structs inherit directly from <xref:System.ValueType>, which inherits from <xref:System.Object>.</span></span>  
- <span data-ttu-id="03518-117">Структуры могут реализовывать интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="03518-117">A struct can implement interfaces.</span></span>
- <span data-ttu-id="03518-118">Структура не может быть `null`, а переменная структуры не может быть назначена `null`, если переменная не объявлена как тип, допускающий значение null.</span><span class="sxs-lookup"><span data-stu-id="03518-118">A struct cannot be `null`, and a struct variable cannot be assigned `null` unless the variable is declared as a nullable type.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="03518-119">См. также</span><span class="sxs-lookup"><span data-stu-id="03518-119">See also</span></span>

- [<span data-ttu-id="03518-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="03518-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="03518-121">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="03518-121">Classes and Structs</span></span>](index.md)
- [<span data-ttu-id="03518-122">Классы</span><span class="sxs-lookup"><span data-stu-id="03518-122">Classes</span></span>](classes.md)
- [<span data-ttu-id="03518-123">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="03518-123">Nullable Types</span></span>](../nullable-types/index.md)
- [<span data-ttu-id="03518-124">Имена идентификаторов</span><span class="sxs-lookup"><span data-stu-id="03518-124">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="03518-125">Использование структур</span><span class="sxs-lookup"><span data-stu-id="03518-125">Using Structs</span></span>](using-structs.md)
- [<span data-ttu-id="03518-126">Практическое руководство. Определение различия между передачей структуры и ссылки класса в метод (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="03518-126">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)
