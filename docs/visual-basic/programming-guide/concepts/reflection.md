---
title: "Отражение (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: d991bc0f-d16a-4ac5-9351-70e5c5b9891b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: acfcb519128de0d616757398c94ec70dc7de6ef1
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="reflection-visual-basic"></a><span data-ttu-id="fe0af-102">Отражение (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe0af-102">Reflection (Visual Basic)</span></span>
<span data-ttu-id="fe0af-103">Отражение предоставляет объекты (типа <xref:System.Type>), описывающие сборки, модули и типы.</xref:System.Type></span><span class="sxs-lookup"><span data-stu-id="fe0af-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules and types.</span></span> <span data-ttu-id="fe0af-104">Можно использовать отражение для динамически создать экземпляр типа, привязки типа к существующему объекту или получения типа из существующего объекта и вызова его методов или доступа к его полям и свойствам.</span><span class="sxs-lookup"><span data-stu-id="fe0af-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="fe0af-105">Если в коде используются атрибуты, отражение позволяет получить к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="fe0af-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="fe0af-106">Дополнительные сведения см. в разделе [атрибуты](https://msdn.microsoft.com/library/5x6cd29c).</span><span class="sxs-lookup"><span data-stu-id="fe0af-106">For more information, see [Attributes](https://msdn.microsoft.com/library/5x6cd29c).</span></span>  
  
 <span data-ttu-id="fe0af-107">Ниже приведен простой пример отражения с помощью статического метода `GetType` - наследуемый всеми типами из `Object` базового класса — для получения типа переменной:</span><span class="sxs-lookup"><span data-stu-id="fe0af-107">Here's a simple example of reflection using the static method `GetType` - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>  
  
```vb  
' Using GetType to obtain type information:  
Dim i As Integer = 42  
Dim type As System.Type = i.GetType()  
System.Console.WriteLine(type)  
```  
  
 <span data-ttu-id="fe0af-108">Выводится следующий результат:</span><span class="sxs-lookup"><span data-stu-id="fe0af-108">The output is:</span></span>  
  
 `System.Int32`  
  
 <span data-ttu-id="fe0af-109">В следующем примере отражение используется для получения полного имени загруженной сборки.</span><span class="sxs-lookup"><span data-stu-id="fe0af-109">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>  
  
```vb  
' Using Reflection to get information from an Assembly:  
Dim info As System.Reflection.Assembly = GetType(System.Int32).Assembly  
System.Console.WriteLine(info)  
```  
  
 <span data-ttu-id="fe0af-110">Выводится следующий результат:</span><span class="sxs-lookup"><span data-stu-id="fe0af-110">The output is:</span></span>  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
## <a name="reflection-overview"></a><span data-ttu-id="fe0af-111">Общие сведения об отражении</span><span class="sxs-lookup"><span data-stu-id="fe0af-111">Reflection Overview</span></span>  
 <span data-ttu-id="fe0af-112">Отражение полезно в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="fe0af-112">Reflection is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="fe0af-113">При наличии доступа к атрибутам в метаданных программы.</span><span class="sxs-lookup"><span data-stu-id="fe0af-113">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="fe0af-114">Дополнительные сведения см. в разделе [извлечение информации, сохраненной в атрибуте](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c).</span><span class="sxs-lookup"><span data-stu-id="fe0af-114">For more information, see [Retrieving Information Stored in Attributes](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c).</span></span>  
  
-   <span data-ttu-id="fe0af-115">Для проверки и создания экземпляров типов в сборке.</span><span class="sxs-lookup"><span data-stu-id="fe0af-115">For examining and instantiating types in an assembly.</span></span>  
  
-   <span data-ttu-id="fe0af-116">Для создания новых типов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="fe0af-116">For building new types at runtime.</span></span> <span data-ttu-id="fe0af-117">Используйте классы <xref:System.Reflection.Emit>.</xref:System.Reflection.Emit></span><span class="sxs-lookup"><span data-stu-id="fe0af-117">Use classes in <xref:System.Reflection.Emit>.</span></span>  
  
-   <span data-ttu-id="fe0af-118">Для выполнения позднего связывания, доступ к методам в типах, созданных во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="fe0af-118">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="fe0af-119">См. в разделе [динамическая загрузка и использование типов](http://msdn.microsoft.com/library/db985bec-5942-40ec-b13a-771ae98623dc).</span><span class="sxs-lookup"><span data-stu-id="fe0af-119">See the topic [Dynamically Loading and Using Types](http://msdn.microsoft.com/library/db985bec-5942-40ec-b13a-771ae98623dc).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fe0af-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="fe0af-120">Related Sections</span></span>  
 <span data-ttu-id="fe0af-121">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="fe0af-121">For more information:</span></span>  
  
-   [<span data-ttu-id="fe0af-122">Отражение</span><span class="sxs-lookup"><span data-stu-id="fe0af-122">Reflection</span></span>](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775)  
  
-   [<span data-ttu-id="fe0af-123">Просмотр сведений о типах</span><span class="sxs-lookup"><span data-stu-id="fe0af-123">Viewing Type Information</span></span>](http://msdn.microsoft.com/library/7e7303a9-4064-4738-b4e7-b75974ed70d2)  
  
-   [<span data-ttu-id="fe0af-124">Отражение и универсальные типы</span><span class="sxs-lookup"><span data-stu-id="fe0af-124">Reflection and Generic Types</span></span>](http://msdn.microsoft.com/library/f7180fc5-dd41-42d4-8a8e-1b34288e06de)  
  
-   <span data-ttu-id="fe0af-125"><xref:System.Reflection.Emit></xref:System.Reflection.Emit></span><span class="sxs-lookup"><span data-stu-id="fe0af-125"><xref:System.Reflection.Emit></span></span>  
  
-   [<span data-ttu-id="fe0af-126">Извлечение информации, сохраненной в атрибуте</span><span class="sxs-lookup"><span data-stu-id="fe0af-126">Retrieving Information Stored in Attributes</span></span>](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c)  
  
## <a name="see-also"></a><span data-ttu-id="fe0af-127">См. также</span><span class="sxs-lookup"><span data-stu-id="fe0af-127">See Also</span></span>  
 <span data-ttu-id="fe0af-128">[Руководство по программированию на Visual Basic](../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fe0af-128">[Visual Basic Programming Guide](../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="fe0af-129"> [Сборки в среде CLR](https://msdn.microsoft.com/library/k3677y81)</span><span class="sxs-lookup"><span data-stu-id="fe0af-129"> [Assemblies in the Common Language Runtime](https://msdn.microsoft.com/library/k3677y81)</span></span>
