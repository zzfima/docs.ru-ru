---
title: Структуры (Руководство по программированию на C#)
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: 27d4b0d7edf1b5e89e84ac1df5783d68ebb4efe0
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259499"
---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="e6117-102">Структуры (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="e6117-102">Structs (C# Programming Guide)</span></span>

<span data-ttu-id="e6117-103">Структуры определяются с помощью ключевого слова [struct](../../language-reference/keywords/struct.md), например:</span><span class="sxs-lookup"><span data-stu-id="e6117-103">Structs are defined by using the [struct](../../language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
[!code-csharp[csProgGuideObjects#39](./codesnippet/CSharp/structs_1.cs)]  
  
<span data-ttu-id="e6117-104">Структуры используют большую часть того же синтаксиса, что и классы.</span><span class="sxs-lookup"><span data-stu-id="e6117-104">Structs share most of the same syntax as classes.</span></span> <span data-ttu-id="e6117-105">Имя структуры должно быть допустимым [именем идентификатора](../inside-a-program/identifier-names.md) C#.</span><span class="sxs-lookup"><span data-stu-id="e6117-105">The name of the struct must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span> <span data-ttu-id="e6117-106">Структуры более ограничены по сравнению с классами по следующим причинам.</span><span class="sxs-lookup"><span data-stu-id="e6117-106">Structs are more limited than classes in the following ways:</span></span>  
  
- <span data-ttu-id="e6117-107">В объявлении структуры поля не могут быть инициализированы до тех пор, пока они будут объявлены как const или static.</span><span class="sxs-lookup"><span data-stu-id="e6117-107">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
- <span data-ttu-id="e6117-108">Структура не может объявлять используемый по умолчанию конструктор (конструктор без параметров) или метод завершения.</span><span class="sxs-lookup"><span data-stu-id="e6117-108">A struct cannot declare a default constructor (a constructor without parameters) or a finalizer.</span></span>  
- <span data-ttu-id="e6117-109">Структуры копируются при присваивании.</span><span class="sxs-lookup"><span data-stu-id="e6117-109">Structs are copied on assignment.</span></span> <span data-ttu-id="e6117-110">При присваивании структуры к новой переменной выполняется копирование всех данных, а любое изменение новой копии не влияет на данные в исходной копии.</span><span class="sxs-lookup"><span data-stu-id="e6117-110">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="e6117-111">Это важно помнить при работе с коллекциями типов значений, такими как `Dictionary<string, myStruct>`.</span><span class="sxs-lookup"><span data-stu-id="e6117-111">This is important to remember when working with collections of value types such as `Dictionary<string, myStruct>`.</span></span>  
- <span data-ttu-id="e6117-112">Структуры являются типами значений, а классы — ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="e6117-112">Structs are value types, unlike classes, which are reference types.</span></span>  
- <span data-ttu-id="e6117-113">В отличие от классов структуры можно создавать без использования оператора `new`.</span><span class="sxs-lookup"><span data-stu-id="e6117-113">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
- <span data-ttu-id="e6117-114">Структуры могут объявлять конструкторы, имеющие параметры.</span><span class="sxs-lookup"><span data-stu-id="e6117-114">Structs can declare constructors that have parameters.</span></span> 
- <span data-ttu-id="e6117-115">Структура не может наследовать от другой структуры или класса и не может быть базовой для класса.</span><span class="sxs-lookup"><span data-stu-id="e6117-115">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="e6117-116">Все структуры наследуют непосредственно от <xref:System.ValueType>, который наследует от <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="e6117-116">All structs inherit directly from <xref:System.ValueType>, which inherits from <xref:System.Object>.</span></span>  
- <span data-ttu-id="e6117-117">Структуры могут реализовывать интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="e6117-117">A struct can implement interfaces.</span></span>  
- <span data-ttu-id="e6117-118">Структура может использоваться как тип, допускающий значение NULL, и ей можно назначить значение NULL.</span><span class="sxs-lookup"><span data-stu-id="e6117-118">A struct can be used as a nullable type and can be assigned a null value.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e6117-119">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="e6117-119">Related sections</span></span>  

<span data-ttu-id="e6117-120">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="e6117-120">For more information:</span></span>  
  
- [<span data-ttu-id="e6117-121">Использование структур</span><span class="sxs-lookup"><span data-stu-id="e6117-121">Using Structs</span></span>](using-structs.md)
- [<span data-ttu-id="e6117-122">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="e6117-122">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="e6117-123">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="e6117-123">Nullable Types</span></span>](../nullable-types/index.md)
- [<span data-ttu-id="e6117-124">Практическое руководство. Определение различия между передачей структуры и ссылки класса в метод</span><span class="sxs-lookup"><span data-stu-id="e6117-124">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)
- [<span data-ttu-id="e6117-125">Практическое руководство. Реализация определенных пользователем преобразований между структурами</span><span class="sxs-lookup"><span data-stu-id="e6117-125">How to: Implement User-Defined Conversions Between Structs</span></span>](../statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)

## <a name="see-also"></a><span data-ttu-id="e6117-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e6117-126">See also</span></span>

- [<span data-ttu-id="e6117-127">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e6117-127">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e6117-128">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="e6117-128">Classes and Structs</span></span>](index.md)
- [<span data-ttu-id="e6117-129">Классы</span><span class="sxs-lookup"><span data-stu-id="e6117-129">Classes</span></span>](classes.md)
- [<span data-ttu-id="e6117-130">Имена идентификаторов</span><span class="sxs-lookup"><span data-stu-id="e6117-130">Identifier names</span></span>](../inside-a-program/identifier-names.md)
