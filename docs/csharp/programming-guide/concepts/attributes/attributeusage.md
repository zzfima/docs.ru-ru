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
ms.openlocfilehash: e9351ee10b523145ace1249bf17388da0cdba277
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2017
---
# <a name="attributeusage-c"></a>AttributeUsage (C#)
Определяет, как можно использовать пользовательский класс атрибутов. Атрибут `AttributeUsage` можно применять к пользовательским определениям атрибутов, чтобы контролировать применение нового атрибута. При явном применении параметры по умолчанию выглядят следующим образом:  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.All,  
                   AllowMultiple = false,  
                   Inherited = true)]  
class NewAttribute : System.Attribute { }  
```  
  
 В этом примере класс `NewAttribute` можно применить к любой сущности кода с атрибутами, но только один раз к каждой сущности. Он наследуется производными классами при применении к базовому классу.  
  
 Аргументы `AllowMultiple` и `Inherited` являются необязательными, так что этот код имеет тот же результат:  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.All)]  
class NewAttribute : System.Attribute { }  
```  
  
 Первый аргумент `AttributeUsage` должен состоять из одного или нескольких элементов перечисления <xref:System.AttributeTargets>. Несколько целевых типов можно связать с помощью оператора OR следующим образом:  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Property | AttributeTargets.Field)]  
class NewPropertyOrFieldAttribute : Attribute { }  
```  
  
 Если аргументу `AllowMultiple` присвоено значение `true`, то результирующий атрибут можно применить несколько раз к одной сущности следующим образом:  
  
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
  
 В этом случае `MultiUseAttr` можно применять несколько раз, так как `AllowMultiple` имеет значение `true`. Для применения нескольких атрибутов допускаются оба показанных формата.  
  
 Если `Inherited` имеет значение `false`, то атрибут не наследуется классами, производными от класса с атрибутами. Пример:  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Class, Inherited = false)]  
class Attr1 : Attribute { }  
  
[Attr1]  
class BClass { }  
  
class DClass : BClass { }  
```  
  
 В этом случае `Attr1` не применяется к `DClass` путем наследования.  
  
## <a name="remarks"></a>Примечания  
 Атрибут `AttributeUsage` можно использовать только один раз — его нельзя повторно применять к одному и тому же классу. `AttributeUsage` является псевдонимом для <xref:System.AttributeUsageAttribute>.  
  
 Дополнительные сведения см. в разделе [Обращение к атрибутам с помощью отражения (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере демонстрируется действие аргументов `Inherited` и `AllowMultiple` по отношению к атрибуту `AttributeUsage`, а также способ перечисления настраиваемых атрибутов, примененных к классу.  
  
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
  
## <a name="sample-output"></a>Пример результатов выполнения  
  
```  
Attributes on Base Class:  
A1  
A2  
Attributes on Derived Class:  
A3  
A3  
A2  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Attribute>  
 <xref:System.Reflection>  
 [Руководство по программированию на C#](../../../../csharp/programming-guide/index.md)  
 [Атрибуты](../../../../../docs/standard/attributes/index.md)  
 [Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md) (Отражение (C#))  
 [Атрибуты](../../../../csharp/programming-guide/concepts/attributes/index.md)  
 [Создание настраиваемых атрибутов (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [Обращение к атрибутам с помощью отражения (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
