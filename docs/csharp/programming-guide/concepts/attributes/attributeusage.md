---
title: AttributeUsage (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 22c45568-9a6a-4c2f-8480-f38c1caa0a99
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 81e7440279a2d7dfa801394ee0e9af6181da3c13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="attributeusage-c"></a><span data-ttu-id="ac1f1-102">AttributeUsage (C#)</span><span class="sxs-lookup"><span data-stu-id="ac1f1-102">AttributeUsage (C#)</span></span>
<span data-ttu-id="ac1f1-103">Определяет, как можно использовать пользовательский класс атрибутов.</span><span class="sxs-lookup"><span data-stu-id="ac1f1-103">Determines how a custom attribute class can be used.</span></span> <span data-ttu-id="ac1f1-104">Атрибут `AttributeUsage` можно применять к пользовательским определениям атрибутов, чтобы контролировать применение нового атрибута.</span><span class="sxs-lookup"><span data-stu-id="ac1f1-104">`AttributeUsage` is an attribute that can be applied to custom attribute definitions to control how the new attribute can be applied.</span></span> <span data-ttu-id="ac1f1-105">При явном применении параметры по умолчанию выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ac1f1-105">The default settings look like this when applied explicitly:</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.All,  
                   AllowMultiple = false,  
                   Inherited = true)]  
class NewAttribute : System.Attribute { }  
```  
  
 <span data-ttu-id="ac1f1-106">В этом примере класс `NewAttribute` можно применить к любой сущности кода с атрибутами, но только один раз к каждой сущности.</span><span class="sxs-lookup"><span data-stu-id="ac1f1-106">In this example, the `NewAttribute` class can be applied to any attribute-able code entity, but can be applied only once to each entity.</span></span> <span data-ttu-id="ac1f1-107">Он наследуется производными классами при применении к базовому классу.</span><span class="sxs-lookup"><span data-stu-id="ac1f1-107">It is inherited by derived classes when applied to a base class.</span></span>  
  
 <span data-ttu-id="ac1f1-108">Аргументы `AllowMultiple` и `Inherited` являются необязательными, так что этот код имеет тот же результат:</span><span class="sxs-lookup"><span data-stu-id="ac1f1-108">The `AllowMultiple` and `Inherited` arguments are optional, so this code has the same effect:</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.All)]  
class NewAttribute : System.Attribute { }  
```  
  
 <span data-ttu-id="ac1f1-109">Первый аргумент `AttributeUsage` должен состоять из одного или нескольких элементов перечисления <xref:System.AttributeTargets>.</span><span class="sxs-lookup"><span data-stu-id="ac1f1-109">The first `AttributeUsage` argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="ac1f1-110">Несколько целевых типов можно связать с помощью оператора OR следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ac1f1-110">Multiple target types can be linked together with the OR operator, like this:</span></span>  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Property | AttributeTargets.Field)]  
class NewPropertyOrFieldAttribute : Attribute { }  
```  
  
 <span data-ttu-id="ac1f1-111">Если аргументу `AllowMultiple` присвоено значение `true`, то результирующий атрибут можно применить несколько раз к одной сущности следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ac1f1-111">If the `AllowMultiple` argument is set to `true`, then the resulting attribute can be applied more than once to a single entity, like this:</span></span>  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Class, AllowMultiple = true)]  
class MultiUseAttr : Attribute { }  
  
[MultiUseAttr]  
[MultiUseAttr]  
class Class1 { }  
  
[MultiUseAttr, MultiUseAttr]  
class Class2 { }  
```  
  
 <span data-ttu-id="ac1f1-112">В этом случае `MultiUseAttr` можно применять несколько раз, так как `AllowMultiple` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="ac1f1-112">In this case `MultiUseAttr` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="ac1f1-113">Для применения нескольких атрибутов допускаются оба показанных формата.</span><span class="sxs-lookup"><span data-stu-id="ac1f1-113">Both formats shown for applying multiple attributes are valid.</span></span>  
  
 <span data-ttu-id="ac1f1-114">Если `Inherited` имеет значение `false`, то атрибут не наследуется классами, производными от класса с атрибутами.</span><span class="sxs-lookup"><span data-stu-id="ac1f1-114">If `Inherited` is set to `false`, then the attribute is not inherited by classes that are derived from a class that is attributed.</span></span> <span data-ttu-id="ac1f1-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="ac1f1-115">For example:</span></span>  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Class, Inherited = false)]  
class Attr1 : Attribute { }  
  
[Attr1]  
class BClass { }  
  
class DClass : BClass { }  
```  
  
 <span data-ttu-id="ac1f1-116">В этом случае `Attr1` не применяется к `DClass` путем наследования.</span><span class="sxs-lookup"><span data-stu-id="ac1f1-116">In this case `Attr1` is not applied to `DClass` via inheritance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac1f1-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="ac1f1-117">Remarks</span></span>  
 <span data-ttu-id="ac1f1-118">Атрибут `AttributeUsage` можно использовать только один раз — его нельзя повторно применять к одному и тому же классу.</span><span class="sxs-lookup"><span data-stu-id="ac1f1-118">The `AttributeUsage` attribute is a single-use attribute--it cannot be applied more than once to the same class.</span></span> <span data-ttu-id="ac1f1-119">`AttributeUsage` является псевдонимом для <xref:System.AttributeUsageAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ac1f1-119">`AttributeUsage` is an alias for <xref:System.AttributeUsageAttribute>.</span></span>  
  
 <span data-ttu-id="ac1f1-120">Дополнительные сведения см. в разделе [Обращение к атрибутам с помощью отражения (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="ac1f1-120">For more information, see [Accessing Attributes by Using Reflection (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac1f1-121">Пример</span><span class="sxs-lookup"><span data-stu-id="ac1f1-121">Example</span></span>  
 <span data-ttu-id="ac1f1-122">В приведенном ниже примере демонстрируется действие аргументов `Inherited` и `AllowMultiple` по отношению к атрибуту `AttributeUsage`, а также способ перечисления настраиваемых атрибутов, примененных к классу.</span><span class="sxs-lookup"><span data-stu-id="ac1f1-122">The following example demonstrates the effect of the `Inherited` and `AllowMultiple` arguments to the `AttributeUsage` attribute, and how the custom attributes applied to a class can be enumerated.</span></span>  
  
```csharp  
using System;  

// Create some custom attributes:  
[AttributeUsage(System.AttributeTargets.Class, Inherited = false)]  
class A1 : System.Attribute { }  
  
[AttributeUsage(System.AttributeTargets.Class)]  
class A2 : System.Attribute { }  
  
[AttributeUsage(System.AttributeTargets.Class, AllowMultiple = true)]  
class A3 : System.Attribute { }  
  
// Apply custom attributes to classes:  
[A1, A2]  
class BaseClass { }  
  
[A3, A3]  
class DerivedClass : BaseClass { }  
  
public class TestAttributeUsage  
{  
    static void Main()  
    {  
        BaseClass b = new BaseClass();  
        DerivedClass d = new DerivedClass();  
  
        // Display custom attributes for each class.  
        Console.WriteLine("Attributes on Base Class:");  
        object[] attrs = b.GetType().GetCustomAttributes(true);  
        foreach (Attribute attr in attrs)  
        {  
            Console.WriteLine(attr);  
        }  
  
        Console.WriteLine("Attributes on Derived Class:");  
        attrs = d.GetType().GetCustomAttributes(true);  
        foreach (Attribute attr in attrs)  
        {  
            Console.WriteLine(attr);  
        }  
    }  
}  
```  
  
## <a name="sample-output"></a><span data-ttu-id="ac1f1-123">Пример результатов выполнения</span><span class="sxs-lookup"><span data-stu-id="ac1f1-123">Sample Output</span></span>  
  
```  
Attributes on Base Class:  
A1  
A2  
Attributes on Derived Class:  
A3  
A3  
A2  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac1f1-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ac1f1-124">See Also</span></span>  
 <xref:System.Attribute>  
 <xref:System.Reflection>  
 [<span data-ttu-id="ac1f1-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ac1f1-125">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ac1f1-126">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ac1f1-126">Attributes</span></span>](https://msdn.microsoft.com/library/5x6cd29c)  
 <span data-ttu-id="ac1f1-127">[Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md) (Отражение (C#))</span><span class="sxs-lookup"><span data-stu-id="ac1f1-127">[Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md)</span></span>  
 [<span data-ttu-id="ac1f1-128">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ac1f1-128">Attributes</span></span>](../../../../csharp/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="ac1f1-129">Создание настраиваемых атрибутов (C#)</span><span class="sxs-lookup"><span data-stu-id="ac1f1-129">Creating Custom Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [<span data-ttu-id="ac1f1-130">Обращение к атрибутам с помощью отражения (C#)</span><span class="sxs-lookup"><span data-stu-id="ac1f1-130">Accessing Attributes by Using Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
