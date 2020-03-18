---
title: Отражение (C#)
ms.date: 07/20/2015
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
ms.openlocfilehash: a56fb24b63e4d80dbb67b079466b67cd11672023
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "74711663"
---
# <a name="reflection-c"></a><span data-ttu-id="50c53-102">Отражение (C#)</span><span class="sxs-lookup"><span data-stu-id="50c53-102">Reflection (C#)</span></span>

<span data-ttu-id="50c53-103">Механизм отражения позволяет получать объекты (типа <xref:System.Type>), которые описывают сборки, модули и типы.</span><span class="sxs-lookup"><span data-stu-id="50c53-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules, and types.</span></span> <span data-ttu-id="50c53-104">Отражение можно использовать для динамического создания экземпляра типа, привязки типа к существующему объекту, а также получения типа из существующего объекта и вызова его методов или доступа к его полям и свойствам.</span><span class="sxs-lookup"><span data-stu-id="50c53-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="50c53-105">Если в коде используются атрибуты, отражение обеспечивает доступ к ним.</span><span class="sxs-lookup"><span data-stu-id="50c53-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="50c53-106">Дополнительные сведения см. в разделе [Атрибуты](../../../standard/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="50c53-106">For more information, see [Attributes](../../../standard/attributes/index.md).</span></span>

<span data-ttu-id="50c53-107">Вот простой пример отражения, в котором для получения типа переменной используется метод <xref:System.Object.GetType>, наследуемый всеми типами от базового класса `Object`:</span><span class="sxs-lookup"><span data-stu-id="50c53-107">Here's a simple example of reflection using the <xref:System.Object.GetType> method - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>

> [!NOTE]
> <span data-ttu-id="50c53-108">Убедитесь, что вы добавили `using System;` и `using System.Reflection;` в верхней части файла *.cs*.</span><span class="sxs-lookup"><span data-stu-id="50c53-108">Make sure you add `using System;` and `using System.Reflection;` at the top of your *.cs* file.</span></span>

```csharp
// Using GetType to obtain type information:
int i = 42;
Type type = i.GetType();
Console.WriteLine(type);
```

<span data-ttu-id="50c53-109">Выходные данные: `System.Int32`.</span><span class="sxs-lookup"><span data-stu-id="50c53-109">The output is: `System.Int32`.</span></span>

<span data-ttu-id="50c53-110">В этом примере отражение используется для получения полного имени загруженной сборки.</span><span class="sxs-lookup"><span data-stu-id="50c53-110">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>

```csharp
// Using Reflection to get information of an Assembly:
Assembly info = typeof(int).Assembly;
Console.WriteLine(info);
```

<span data-ttu-id="50c53-111">Выходные данные: `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e`.</span><span class="sxs-lookup"><span data-stu-id="50c53-111">The output is: `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e`.</span></span>

> [!NOTE]
> <span data-ttu-id="50c53-112">Ключевые слова C# `protected` и `internal` не имеют никакого значения в промежуточном языке и не используются в интерфейсах API отражения.</span><span class="sxs-lookup"><span data-stu-id="50c53-112">The C# keywords `protected` and `internal` have no meaning in IL and are not used in the reflection APIs.</span></span> <span data-ttu-id="50c53-113">Соответствующими терминами в промежуточном языке являются *Family* и *Assembly*.</span><span class="sxs-lookup"><span data-stu-id="50c53-113">The corresponding terms in IL are *Family* and *Assembly*.</span></span> <span data-ttu-id="50c53-114">Для идентификации метода `internal` с помощью отражения используйте свойство <xref:System.Reflection.MethodBase.IsAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="50c53-114">To identify an `internal` method using reflection, use the <xref:System.Reflection.MethodBase.IsAssembly%2A> property.</span></span> <span data-ttu-id="50c53-115">Для идентификации метода `protected internal` используйте <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="50c53-115">To identify a `protected internal` method, use the <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span></span>

## <a name="reflection-overview"></a><span data-ttu-id="50c53-116">Общие сведения об отражении</span><span class="sxs-lookup"><span data-stu-id="50c53-116">Reflection overview</span></span>

<span data-ttu-id="50c53-117">Отражение удобно использовать в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="50c53-117">Reflection is useful in the following situations:</span></span>

- <span data-ttu-id="50c53-118">При необходимости доступа к атрибутам в метаданных программы.</span><span class="sxs-lookup"><span data-stu-id="50c53-118">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="50c53-119">Дополнительные сведения см. в разделе [Извлечение информации, сохраненной в атрибуте](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="50c53-119">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>
- <span data-ttu-id="50c53-120">Для проверки и создания экземпляров типов в сборке.</span><span class="sxs-lookup"><span data-stu-id="50c53-120">For examining and instantiating types in an assembly.</span></span>
- <span data-ttu-id="50c53-121">Для создания типов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="50c53-121">For building new types at runtime.</span></span> <span data-ttu-id="50c53-122">Используйте классы в <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="50c53-122">Use classes in <xref:System.Reflection.Emit>.</span></span>
- <span data-ttu-id="50c53-123">Для выполнения позднего связывания, которое обеспечивает доступ к методам в типах, созданных во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="50c53-123">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="50c53-124">См. раздел [Динамическая загрузка и использование типов](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span><span class="sxs-lookup"><span data-stu-id="50c53-124">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>

## <a name="related-sections"></a><span data-ttu-id="50c53-125">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="50c53-125">Related sections</span></span>

<span data-ttu-id="50c53-126">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="50c53-126">For more information:</span></span>

- [<span data-ttu-id="50c53-127">Отражение</span><span class="sxs-lookup"><span data-stu-id="50c53-127">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
- [<span data-ttu-id="50c53-128">Просмотр сведений о типах</span><span class="sxs-lookup"><span data-stu-id="50c53-128">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)
- [<span data-ttu-id="50c53-129">Отражение и универсальные типы</span><span class="sxs-lookup"><span data-stu-id="50c53-129">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)
- <xref:System.Reflection.Emit>
- [<span data-ttu-id="50c53-130">Извлечение информации, сохраненной в атрибуте</span><span class="sxs-lookup"><span data-stu-id="50c53-130">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)

## <a name="see-also"></a><span data-ttu-id="50c53-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="50c53-131">See also</span></span>

- [<span data-ttu-id="50c53-132">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="50c53-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="50c53-133">Сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="50c53-133">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
