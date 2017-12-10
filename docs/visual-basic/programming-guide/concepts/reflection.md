---
title: "Отражение (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: d991bc0f-d16a-4ac5-9351-70e5c5b9891b
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8c2ae87eae971129059a7e84b36971c13a5fe71b
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2017
---
# <a name="reflection-visual-basic"></a><span data-ttu-id="560c3-102">Отражение (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="560c3-102">Reflection (Visual Basic)</span></span>
<span data-ttu-id="560c3-103">Механизм отражения позволяет получать объекты (типа <xref:System.Type>), которые описывают сборки, модули и типы.</span><span class="sxs-lookup"><span data-stu-id="560c3-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules and types.</span></span> <span data-ttu-id="560c3-104">Отражение можно использовать для динамического создания экземпляра типа, привязки типа к существующему объекту, а также получения типа из существующего объекта и вызова его методов или доступа к его полям и свойствам.</span><span class="sxs-lookup"><span data-stu-id="560c3-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="560c3-105">Если в коде используются атрибуты, отражение обеспечивает доступ к ним.</span><span class="sxs-lookup"><span data-stu-id="560c3-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="560c3-106">Дополнительные сведения см. в разделе [Атрибуты](../../../../docs/standard/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="560c3-106">For more information, see [Attributes](../../../../docs/standard/attributes/index.md).</span></span>  
  
 <span data-ttu-id="560c3-107">Вот простой пример отражения, в котором для получения типа переменной используется статический метод `GetType`, наследуемый всеми типами от базового класса `Object`.</span><span class="sxs-lookup"><span data-stu-id="560c3-107">Here's a simple example of reflection using the static method `GetType` - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>  
  
```vb  
' Using GetType to obtain type information:  
Dim i As Integer = 42  
Dim type As System.Type = i.GetType()  
System.Console.WriteLine(type)  
```  
  
 <span data-ttu-id="560c3-108">Результат.</span><span class="sxs-lookup"><span data-stu-id="560c3-108">The output is:</span></span>  
  
 `System.Int32`  
  
 <span data-ttu-id="560c3-109">В этом примере отражение используется для получения полного имени загруженной сборки.</span><span class="sxs-lookup"><span data-stu-id="560c3-109">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>  
  
```vb  
' Using Reflection to get information from an Assembly:  
Dim info As System.Reflection.Assembly = GetType(System.Int32).Assembly  
System.Console.WriteLine(info)  
```  
  
 <span data-ttu-id="560c3-110">Результат.</span><span class="sxs-lookup"><span data-stu-id="560c3-110">The output is:</span></span>  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
## <a name="reflection-overview"></a><span data-ttu-id="560c3-111">Общие сведения об отражении</span><span class="sxs-lookup"><span data-stu-id="560c3-111">Reflection Overview</span></span>  
 <span data-ttu-id="560c3-112">Отражение удобно использовать в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="560c3-112">Reflection is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="560c3-113">При необходимости доступа к атрибутам в метаданных программы.</span><span class="sxs-lookup"><span data-stu-id="560c3-113">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="560c3-114">Дополнительные сведения см. в разделе [Извлечение информации, сохраненной в атрибуте](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="560c3-114">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>  
  
-   <span data-ttu-id="560c3-115">Для проверки и создания экземпляров типов в сборке.</span><span class="sxs-lookup"><span data-stu-id="560c3-115">For examining and instantiating types in an assembly.</span></span>  
  
-   <span data-ttu-id="560c3-116">Для создания типов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="560c3-116">For building new types at runtime.</span></span> <span data-ttu-id="560c3-117">Используйте классы в <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="560c3-117">Use classes in <xref:System.Reflection.Emit>.</span></span>  
  
-   <span data-ttu-id="560c3-118">Для выполнения позднего связывания, которое обеспечивает доступ к методам в типах, созданных во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="560c3-118">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="560c3-119">См. раздел [Динамическая загрузка и использование типов](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span><span class="sxs-lookup"><span data-stu-id="560c3-119">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="560c3-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="560c3-120">Related Sections</span></span>  
 <span data-ttu-id="560c3-121">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="560c3-121">For more information:</span></span>  
  
-   [<span data-ttu-id="560c3-122">Отражение</span><span class="sxs-lookup"><span data-stu-id="560c3-122">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
  
-   [<span data-ttu-id="560c3-123">Просмотр сведений о типах</span><span class="sxs-lookup"><span data-stu-id="560c3-123">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)  
  
-   [<span data-ttu-id="560c3-124">Отражение и универсальные типы</span><span class="sxs-lookup"><span data-stu-id="560c3-124">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)  
  
-   <xref:System.Reflection.Emit>  
  
-   [<span data-ttu-id="560c3-125">Извлечение информации, сохраненной в атрибуте</span><span class="sxs-lookup"><span data-stu-id="560c3-125">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)  
  
## <a name="see-also"></a><span data-ttu-id="560c3-126">См. также</span><span class="sxs-lookup"><span data-stu-id="560c3-126">See Also</span></span>  
 [<span data-ttu-id="560c3-127">Руководство по программированию на Visual Basic</span><span class="sxs-lookup"><span data-stu-id="560c3-127">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)  
 [<span data-ttu-id="560c3-128">Сборки в среде CLR</span><span class="sxs-lookup"><span data-stu-id="560c3-128">Assemblies in the Common Language Runtime</span></span>](../../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
