---
title: Отражение (C#)
ms.date: 07/20/2015
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
ms.openlocfilehash: fc5c3f6af1a089d824289a55f6781e887b7cfc56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="reflection-c"></a><span data-ttu-id="d8170-102">Отражение (C#)</span><span class="sxs-lookup"><span data-stu-id="d8170-102">Reflection (C#)</span></span>
<span data-ttu-id="d8170-103">Механизм отражения позволяет получать объекты (типа <xref:System.Type>), которые описывают сборки, модули и типы.</span><span class="sxs-lookup"><span data-stu-id="d8170-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules and types.</span></span> <span data-ttu-id="d8170-104">Отражение можно использовать для динамического создания экземпляра типа, привязки типа к существующему объекту, а также получения типа из существующего объекта и вызова его методов или доступа к его полям и свойствам.</span><span class="sxs-lookup"><span data-stu-id="d8170-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="d8170-105">Если в коде используются атрибуты, отражение обеспечивает доступ к ним.</span><span class="sxs-lookup"><span data-stu-id="d8170-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="d8170-106">Дополнительные сведения см. в разделе [Атрибуты](../../../../docs/standard/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="d8170-106">For more information, see [Attributes](../../../../docs/standard/attributes/index.md).</span></span>  
  
 <span data-ttu-id="d8170-107">Вот простой пример отражения, в котором для получения типа переменной используется статический метод `GetType`, наследуемый всеми типами от базового класса `Object`.</span><span class="sxs-lookup"><span data-stu-id="d8170-107">Here's a simple example of reflection using the static method `GetType` - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>  
  
```csharp  
// Using GetType to obtain type information:  
int i = 42;  
System.Type type = i.GetType();  
System.Console.WriteLine(type);  
```  
  
 <span data-ttu-id="d8170-108">Результат.</span><span class="sxs-lookup"><span data-stu-id="d8170-108">The output is:</span></span>  
  
 `System.Int32`  
  
 <span data-ttu-id="d8170-109">В этом примере отражение используется для получения полного имени загруженной сборки.</span><span class="sxs-lookup"><span data-stu-id="d8170-109">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>  
  
```csharp  
// Using Reflection to get information from an Assembly:  
System.Reflection.Assembly info = typeof(System.Int32).Assembly;  
System.Console.WriteLine(info);  
```  
  
 <span data-ttu-id="d8170-110">Результат.</span><span class="sxs-lookup"><span data-stu-id="d8170-110">The output is:</span></span>  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
> [!NOTE]
>  <span data-ttu-id="d8170-111">Ключевые слова C# `protected` и `internal` не имеют никакого значения в промежуточном языке и не используются в интерфейсах API отражения.</span><span class="sxs-lookup"><span data-stu-id="d8170-111">The C# keywords `protected` and `internal` have no meaning in IL and are not used in the reflection APIs.</span></span> <span data-ttu-id="d8170-112">Соответствующими терминами в промежуточном языке являются *Family* и *Assembly*.</span><span class="sxs-lookup"><span data-stu-id="d8170-112">The corresponding terms in IL are *Family* and *Assembly*.</span></span> <span data-ttu-id="d8170-113">Для идентификации метода `internal` с помощью отражения используйте свойство <xref:System.Reflection.MethodBase.IsAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8170-113">To identify an `internal` method using reflection, use the <xref:System.Reflection.MethodBase.IsAssembly%2A> property.</span></span> <span data-ttu-id="d8170-114">Для идентификации метода `protected internal` используйте <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8170-114">To identify a `protected internal` method, use the <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span></span>  
  
## <a name="reflection-overview"></a><span data-ttu-id="d8170-115">Общие сведения об отражении</span><span class="sxs-lookup"><span data-stu-id="d8170-115">Reflection Overview</span></span>  
 <span data-ttu-id="d8170-116">Отражение удобно использовать в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="d8170-116">Reflection is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="d8170-117">При необходимости доступа к атрибутам в метаданных программы.</span><span class="sxs-lookup"><span data-stu-id="d8170-117">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="d8170-118">Дополнительные сведения см. в разделе [Извлечение информации, сохраненной в атрибуте](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="d8170-118">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>  
  
-   <span data-ttu-id="d8170-119">Для проверки и создания экземпляров типов в сборке.</span><span class="sxs-lookup"><span data-stu-id="d8170-119">For examining and instantiating types in an assembly.</span></span>  
  
-   <span data-ttu-id="d8170-120">Для создания типов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d8170-120">For building new types at runtime.</span></span> <span data-ttu-id="d8170-121">Используйте классы в <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="d8170-121">Use classes in <xref:System.Reflection.Emit>.</span></span>  
  
-   <span data-ttu-id="d8170-122">Для выполнения позднего связывания, которое обеспечивает доступ к методам в типах, созданных во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d8170-122">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="d8170-123">См. раздел [Динамическая загрузка и использование типов](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span><span class="sxs-lookup"><span data-stu-id="d8170-123">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d8170-124">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="d8170-124">Related Sections</span></span>  
 <span data-ttu-id="d8170-125">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="d8170-125">For more information:</span></span>  
  
-   [<span data-ttu-id="d8170-126">Отражение</span><span class="sxs-lookup"><span data-stu-id="d8170-126">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
  
-   [<span data-ttu-id="d8170-127">Просмотр сведений о типах</span><span class="sxs-lookup"><span data-stu-id="d8170-127">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)  
  
-   [<span data-ttu-id="d8170-128">Отражение и универсальные типы</span><span class="sxs-lookup"><span data-stu-id="d8170-128">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)  
  
-   <xref:System.Reflection.Emit>  
  
-   [<span data-ttu-id="d8170-129">Извлечение информации, сохраненной в атрибуте</span><span class="sxs-lookup"><span data-stu-id="d8170-129">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)  
  
## <a name="see-also"></a><span data-ttu-id="d8170-130">См. также</span><span class="sxs-lookup"><span data-stu-id="d8170-130">See Also</span></span>  
 [<span data-ttu-id="d8170-131">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d8170-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d8170-132">Сборки в среде CLR</span><span class="sxs-lookup"><span data-stu-id="d8170-132">Assemblies in the Common Language Runtime</span></span>](../../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
