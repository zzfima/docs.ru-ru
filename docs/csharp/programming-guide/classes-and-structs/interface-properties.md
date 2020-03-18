---
title: Руководство по программированию на C#. Свойства интерфейса
ms.date: 01/31/2020
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: 5798b80526f34e923e2eaab43847b98f6c64e14b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77626624"
---
# <a name="interface-properties-c-programming-guide"></a><span data-ttu-id="6197a-102">Свойства интерфейса (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="6197a-102">Interface Properties (C# Programming Guide)</span></span>

<span data-ttu-id="6197a-103">Свойства можно объявлять для [интерфейса](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="6197a-103">Properties can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="6197a-104">Следующий пример объявляет метод доступа к свойству интерфейса:</span><span class="sxs-lookup"><span data-stu-id="6197a-104">The following example declares an interface property accessor:</span></span>

[!code-csharp[DeclareProperties](~/samples/snippets/csharp/interfaces/properties.cs#DeclareInterfaceProperties)]

<span data-ttu-id="6197a-105">Свойства интерфейса обычно не имеют тела.</span><span class="sxs-lookup"><span data-stu-id="6197a-105">Interface properties typically don't have a body.</span></span> <span data-ttu-id="6197a-106">Методы доступа указывают, доступно ли свойство для чтения и записи, только для чтения или только для записи.</span><span class="sxs-lookup"><span data-stu-id="6197a-106">The accessors indicate whether the property is read-write, read-only, or write-only.</span></span> <span data-ttu-id="6197a-107">В отличие от классов и структур, объявление методов доступа без тела не приводит к объявлению [автоматически реализуемого свойства](auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="6197a-107">Unlike in classes and structs, declaring the accessors without a body doesn't declare an [auto-implemented property](auto-implemented-properties.md).</span></span> <span data-ttu-id="6197a-108">Начиная с C# 8.0 интерфейс может определять реализацию по умолчанию для членов, включая свойства.</span><span class="sxs-lookup"><span data-stu-id="6197a-108">Beginning with C# 8.0, an interface may define a default implementation for members, including properties.</span></span> <span data-ttu-id="6197a-109">Определение реализации по умолчанию для свойства в интерфейсе используется редко, так как интерфейсы могут не определять поля данных экземпляра.</span><span class="sxs-lookup"><span data-stu-id="6197a-109">Defining a default implementation for a property in an interface is rare because interfaces may not define instance data fields.</span></span>

## <a name="example"></a><span data-ttu-id="6197a-110">Пример</span><span class="sxs-lookup"><span data-stu-id="6197a-110">Example</span></span>

<span data-ttu-id="6197a-111">В этом примере интерфейс `IEmployee` содержит доступное для чтения и записи свойство `Name`, а также свойство `Counter`, предназначенное только для чтения.</span><span class="sxs-lookup"><span data-stu-id="6197a-111">In this example, the interface `IEmployee` has a read-write property, `Name`, and a read-only property, `Counter`.</span></span> <span data-ttu-id="6197a-112">Класс `Employee` реализует интерфейс `IEmployee` и использует эти два свойства.</span><span class="sxs-lookup"><span data-stu-id="6197a-112">The class `Employee` implements the `IEmployee` interface and uses these two properties.</span></span> <span data-ttu-id="6197a-113">Программа считывает имя нового сотрудника и текущее число сотрудников, после чего отображает имя сотрудника и его рассчитанный номер.</span><span class="sxs-lookup"><span data-stu-id="6197a-113">The program reads the name of a new employee and the current number of employees and displays the employee name and the computed employee number.</span></span>

<span data-ttu-id="6197a-114">Вы можете использовать полное имя свойства, которое ссылается на интерфейс, где был объявлен член.</span><span class="sxs-lookup"><span data-stu-id="6197a-114">You could use the fully qualified name of the property, which references the interface in which the member is declared.</span></span> <span data-ttu-id="6197a-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="6197a-115">For example:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

<span data-ttu-id="6197a-116">В предыдущем примере показана [явная реализация интерфейса](../interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="6197a-116">The preceding example demonstrates [Explicit Interface Implementation](../interfaces/explicit-interface-implementation.md).</span></span> <span data-ttu-id="6197a-117">Например, если класс `Employee` реализует два интерфейса (`ICitizen` и `IEmployee`), оба из которых содержат свойство `Name`, потребуется явная реализация члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6197a-117">For example, if the class `Employee` is implementing two interfaces `ICitizen` and `IEmployee` and both interfaces have the `Name` property, the explicit interface member implementation will be necessary.</span></span> <span data-ttu-id="6197a-118">Это значит, что потребуется следующее объявление свойства:</span><span class="sxs-lookup"><span data-stu-id="6197a-118">That is, the following property declaration:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

<span data-ttu-id="6197a-119">реализует свойство `Name` в интерфейсе `IEmployee`, тогда как следующее объявление:</span><span class="sxs-lookup"><span data-stu-id="6197a-119">implements the `Name` property on the `IEmployee` interface, while the following declaration:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#CitizenImplementation)]

<span data-ttu-id="6197a-120">реализует свойство `Name` в интерфейсе `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="6197a-120">implements the `Name` property on the `ICitizen` interface.</span></span>

[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#PropertyExample)]
[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#UseProperty)]

**`210 Hazem Abolrous`**

## <a name="sample-output"></a><span data-ttu-id="6197a-121">Пример полученных результатов</span><span class="sxs-lookup"><span data-stu-id="6197a-121">Sample output</span></span>

```console
Enter number of employees: 210
Enter the name of the new employee: Hazem Abolrous
The employee information:
Employee number: 211
Employee name: Hazem Abolrous
```

## <a name="see-also"></a><span data-ttu-id="6197a-122">См. также</span><span class="sxs-lookup"><span data-stu-id="6197a-122">See also</span></span>

- [<span data-ttu-id="6197a-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6197a-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6197a-124">Свойства</span><span class="sxs-lookup"><span data-stu-id="6197a-124">Properties</span></span>](./properties.md)
- [<span data-ttu-id="6197a-125">Использование свойств</span><span class="sxs-lookup"><span data-stu-id="6197a-125">Using Properties</span></span>](./using-properties.md)
- [<span data-ttu-id="6197a-126">Сравнение свойств и индексаторов</span><span class="sxs-lookup"><span data-stu-id="6197a-126">Comparison Between Properties and Indexers</span></span>](../indexers/comparison-between-properties-and-indexers.md)
- [<span data-ttu-id="6197a-127">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="6197a-127">Indexers</span></span>](../indexers/index.md)
- [<span data-ttu-id="6197a-128">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="6197a-128">Interfaces</span></span>](../interfaces/index.md)
