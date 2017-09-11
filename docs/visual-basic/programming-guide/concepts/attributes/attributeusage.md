---
title: "AttributeUsage (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 48757216-c21d-4051-86d5-8a3e03c39d2c
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
ms.openlocfilehash: c91f2686a03d2590e1aaf166d27c49744bb13c9b
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="attributeusage-visual-basic"></a><span data-ttu-id="6fa9f-102">AttributeUsage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6fa9f-102">AttributeUsage (Visual Basic)</span></span>
<span data-ttu-id="6fa9f-103">Определяет, как можно использовать класс настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="6fa9f-103">Determines how a custom attribute class can be used.</span></span> <span data-ttu-id="6fa9f-104">`AttributeUsage`— Это атрибут, который может применяться к определениям настраиваемого атрибута для управления применения нового атрибута.</span><span class="sxs-lookup"><span data-stu-id="6fa9f-104">`AttributeUsage` is an attribute that can be applied to custom attribute definitions to control how the new attribute can be applied.</span></span> <span data-ttu-id="6fa9f-105">При применении явно, по умолчанию выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6fa9f-105">The default settings look like this when applied explicitly:</span></span>  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.All,   
                   AllowMultiple:=False,   
                   Inherited:=True)>   
Class NewAttribute  
    Inherits System.Attribute  
End Class  
```  
  
 <span data-ttu-id="6fa9f-106">В этом примере `NewAttribute` класс может быть применен к любой сущности кода, но может применяться только один раз для каждой сущности.</span><span class="sxs-lookup"><span data-stu-id="6fa9f-106">In this example, the `NewAttribute` class can be applied to any attribute-able code entity, but can be applied only once to each entity.</span></span> <span data-ttu-id="6fa9f-107">Он наследуется производными классами при применении к базовому классу.</span><span class="sxs-lookup"><span data-stu-id="6fa9f-107">It is inherited by derived classes when applied to a base class.</span></span>  
  
 <span data-ttu-id="6fa9f-108">`AllowMultiple` И `Inherited` аргументы являются необязательными, поэтому этот код имеет тот же эффект:</span><span class="sxs-lookup"><span data-stu-id="6fa9f-108">The `AllowMultiple` and `Inherited` arguments are optional, so this code has the same effect:</span></span>  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.All)>   
Class NewAttribute  
    Inherits System.Attribute  
End Class  
```  
  
 <span data-ttu-id="6fa9f-109">Первый `AttributeUsage` аргумент должен быть один или несколько элементов <xref:System.AttributeTargets>перечисления.</xref:System.AttributeTargets></span><span class="sxs-lookup"><span data-stu-id="6fa9f-109">The first `AttributeUsage` argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="6fa9f-110">Несколько целевых типов можно связать вместе с оператором OR следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6fa9f-110">Multiple target types can be linked together with the OR operator, like this:</span></span>  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Property Or AttributeTargets.Field)>   
Class NewPropertyOrFieldAttribute  
    Inherits Attribute  
End Class  
```  
  
 <span data-ttu-id="6fa9f-111">Если `AllowMultiple` аргумент имеет значение `true`, а затем полученный атрибут может применяться несколько раз к одной сущности следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6fa9f-111">If the `AllowMultiple` argument is set to `true`, then the resulting attribute can be applied more than once to a single entity, like this:</span></span>  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Class, AllowMultiple:=True)>   
Class MultiUseAttr  
    Inherits Attribute  
End Class  
  
<MultiUseAttr(), MultiUseAttr()>   
Class Class1  
End Class  
```  
  
 <span data-ttu-id="6fa9f-112">В этом случае `MultiUseAttr` может применяться несколько раз, так как `AllowMultiple` равен `true`.</span><span class="sxs-lookup"><span data-stu-id="6fa9f-112">In this case `MultiUseAttr` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="6fa9f-113">Оба формата для применения нескольких атрибутов являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="6fa9f-113">Both formats shown for applying multiple attributes are valid.</span></span>  
  
 <span data-ttu-id="6fa9f-114">Если `Inherited` равен `false`, то атрибут не наследуется классами, производными от класса, который имеет атрибуты.</span><span class="sxs-lookup"><span data-stu-id="6fa9f-114">If `Inherited` is set to `false`, then the attribute is not inherited by classes that are derived from a class that is attributed.</span></span> <span data-ttu-id="6fa9f-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="6fa9f-115">For example:</span></span>  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Class, Inherited:=False)>   
Class Attr1  
    Inherits Attribute  
End Class  
  
<Attr1()>   
Class BClass  
  
End Class    
  
Class DClass  
    Inherits BClass  
End Class  
```  
  
 <span data-ttu-id="6fa9f-116">В этом случае `Attr1` не применяется к `DClass` через наследование.</span><span class="sxs-lookup"><span data-stu-id="6fa9f-116">In this case `Attr1` is not applied to `DClass` via inheritance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fa9f-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="6fa9f-117">Remarks</span></span>  
 <span data-ttu-id="6fa9f-118">`AttributeUsage` Является атрибутом однократного использования — он не может применяться несколько раз в тот же класс.</span><span class="sxs-lookup"><span data-stu-id="6fa9f-118">The `AttributeUsage` attribute is a single-use attribute--it cannot be applied more than once to the same class.</span></span> <span data-ttu-id="6fa9f-119">`AttributeUsage`является псевдонимом для <xref:System.AttributeUsageAttribute>.</xref:System.AttributeUsageAttribute></span><span class="sxs-lookup"><span data-stu-id="6fa9f-119">`AttributeUsage` is an alias for <xref:System.AttributeUsageAttribute>.</span></span>  
  
 <span data-ttu-id="6fa9f-120">Дополнительные сведения см. в разделе [доступ к атрибутам с помощью отражения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="6fa9f-120">For more information, see [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fa9f-121">Пример</span><span class="sxs-lookup"><span data-stu-id="6fa9f-121">Example</span></span>  
 <span data-ttu-id="6fa9f-122">В следующем примере демонстрируется влияние `Inherited` и `AllowMultiple` аргументы `AttributeUsage` атрибут и как можно перечислить настраиваемых атрибутов, примененных к классу.</span><span class="sxs-lookup"><span data-stu-id="6fa9f-122">The following example demonstrates the effect of the `Inherited` and `AllowMultiple` arguments to the `AttributeUsage` attribute, and how the custom attributes applied to a class can be enumerated.</span></span>  
  
```vb  
Imports System  
```  
  
```vb  
' Create some custom attributes:  
<AttributeUsage(System.AttributeTargets.Class, Inherited:=False)>   
Class A1  
    Inherits System.Attribute  
End Class  
  
<AttributeUsage(System.AttributeTargets.Class)>   
Class A2  
    Inherits System.Attribute  
End Class      
  
<AttributeUsage(System.AttributeTargets.Class, AllowMultiple:=True)>   
Class A3  
    Inherits System.Attribute  
End Class  
  
' Apply custom attributes to classes:  
<A1(), A2()>   
Class BaseClass  
  
End Class  
  
<A3(), A3()>   
Class DerivedClass  
    Inherits BaseClass  
End Class  
  
Public Class TestAttributeUsage  
    Sub Main()  
        Dim b As New BaseClass  
        Dim d As New DerivedClass  
        ' Display custom attributes for each class.  
        Console.WriteLine("Attributes on Base Class:")  
        Dim attrs() As Object = b.GetType().GetCustomAttributes(True)  
  
        For Each attr In attrs  
            Console.WriteLine(attr)  
        Next  
  
        Console.WriteLine("Attributes on Derived Class:")  
        attrs = d.GetType().GetCustomAttributes(True)  
        For Each attr In attrs  
            Console.WriteLine(attr)  
        Next              
    End Sub  
End Class  
```  
  
## <a name="sample-output"></a><span data-ttu-id="6fa9f-123">Пример результатов выполнения</span><span class="sxs-lookup"><span data-stu-id="6fa9f-123">Sample Output</span></span>  
  
```  
Attributes on Base Class:  
A1  
A2  
Attributes on Derived Class:  
A3  
A3  
A2  
```  
  
## <a name="see-also"></a><span data-ttu-id="6fa9f-124">См. также</span><span class="sxs-lookup"><span data-stu-id="6fa9f-124">See Also</span></span>  
 <span data-ttu-id="6fa9f-125"><xref:System.Attribute></xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="6fa9f-125"><xref:System.Attribute></span></span>   
 <span data-ttu-id="6fa9f-126"><xref:System.Reflection></xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="6fa9f-126"><xref:System.Reflection></span></span>   
<span data-ttu-id="6fa9f-127"> [Руководство по программированию на Visual Basic](../../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6fa9f-127"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="6fa9f-128"> [Атрибуты](https://msdn.microsoft.com/library/5x6cd29c) </span><span class="sxs-lookup"><span data-stu-id="6fa9f-128"> [Attributes](https://msdn.microsoft.com/library/5x6cd29c) </span></span>  
<span data-ttu-id="6fa9f-129"> [Отражение (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="6fa9f-129"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span></span>  
<span data-ttu-id="6fa9f-130"> [Атрибуты (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span><span class="sxs-lookup"><span data-stu-id="6fa9f-130"> [Attributes (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span></span>  
<span data-ttu-id="6fa9f-131"> [Создание настраиваемых атрибутов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="6fa9f-131"> [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) </span></span>  
<span data-ttu-id="6fa9f-132"> [Доступ к атрибутам с помощью отражения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="6fa9f-132"> [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>
