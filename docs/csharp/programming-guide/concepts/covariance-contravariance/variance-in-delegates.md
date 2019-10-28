---
title: Вариативность в делегатах (C#)
ms.date: 07/20/2015
ms.assetid: 19de89d2-8224-4406-8964-2965b732b890
ms.openlocfilehash: a65b2fb84e2eae57eecaf5307ca76fbce412d44c
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72772041"
---
# <a name="variance-in-delegates-c"></a>Вариативность в делегатах (C#)
В платформе .NET Framework 3.5 появилась поддержка вариативности при сопоставлении сигнатур методов с типами делегатов во всех делегатах в C#. Это означает, что делегатам можно назначать не только методы, которые обладают соответствующими сигнатурами, но и методы, которые возвращают более производные типы (ковариация), или принимают параметры, которые имеют менее производные типы (контравариативность), чем указано в типе делегата. Это касается не только универсальных методов-делегатов, но и методов-делегатов, не являющихся универсальными.  
  
 Например, рассмотрим следующий код, который содержит два класса и два делегата: универсальный и неуниверсальный.  
  
```csharp  
public class First { }  
public class Second : First { }  
public delegate First SampleDelegate(Second a);  
public delegate R SampleGenericDelegate<A, R>(A a);  
```  
  
 При создании делегатов типов `SampleDelegate` или `SampleGenericDelegate<A, R>` им можно назначить любой из следующих методов.  
  
```csharp  
// Matching signature.  
public static First ASecondRFirst(Second second)  
{ return new First(); }  
  
// The return type is more derived.  
public static Second ASecondRSecond(Second second)  
{ return new Second(); }  
  
// The argument type is less derived.  
public static First AFirstRFirst(First first)  
{ return new First(); }  
  
// The return type is more derived   
// and the argument type is less derived.  
public static Second AFirstRSecond(First first)  
{ return new Second(); }  
```  
  
 В следующем примере кода показано неявное преобразование между сигнатурой метода и типом делегата.  
  
```csharp  
// Assigning a method with a matching signature   
// to a non-generic delegate. No conversion is necessary.  
SampleDelegate dNonGeneric = ASecondRFirst;  
// Assigning a method with a more derived return type   
// and less derived argument type to a non-generic delegate.  
// The implicit conversion is used.  
SampleDelegate dNonGenericConversion = AFirstRSecond;  
  
// Assigning a method with a matching signature to a generic delegate.  
// No conversion is necessary.  
SampleGenericDelegate<Second, First> dGeneric = ASecondRFirst;  
// Assigning a method with a more derived return type   
// and less derived argument type to a generic delegate.  
// The implicit conversion is used.  
SampleGenericDelegate<Second, First> dGenericConversion = AFirstRSecond;  
```  
  
 Дополнительные примеры см. в разделах [Использование вариативности в делегатах (C#)](./using-variance-in-delegates.md) и [Использование вариативности в универсальных методах-делегатах Func и Action (C#)](./using-variance-for-func-and-action-generic-delegates.md).  
  
## <a name="variance-in-generic-type-parameters"></a>Вариативность в параметрах универсального типа  
 В платформе .NET Framework 4 и более поздних версиях можно включить неявное преобразование между делегатами, которое позволит универсальным методам-делегатам, имеющим разные типы, указанные параметрами универсального типа, быть назначенными друг другу, если типы наследуются друг от друга так, как того требует вариативность.  
  
 Чтобы включить неявное преобразование, необходимо явно объявить универсальные параметры в делегате как ковариантные или контравариантные с помощью ключевого слова `in` или `out`.  
  
 В следующем примере кода показано, как создать делегат, который имеет ковариантный параметр универсального типа.  
  
```csharp  
// Type T is declared covariant by using the out keyword.  
public delegate T SampleGenericDelegate <out T>();  
  
public static void Test()  
{  
    SampleGenericDelegate <String> dString = () => " ";  
  
    // You can assign delegates to each other,  
    // because the type T is declared covariant.  
    SampleGenericDelegate <Object> dObject = dString;             
}  
```  
  
 Если поддержка вариативности используется только для сопоставления сигнатур методов с типами делегатов, а ключевые слова `in` и `out` не используются, можно создать экземпляры делегатов с одинаковыми лямбда-выражениями или методами, но нельзя назначить один делегат другому.  
  
 В следующем примере кода `SampleGenericDelegate<String>` нельзя явно преобразовать в `SampleGenericDelegate<Object>`, хотя `String` наследует `Object`. Эту проблему можно устранить, пометив универсальный параметр `T` ключевым словом `out`.  
  
```csharp  
public delegate T SampleGenericDelegate<T>();  
  
public static void Test()  
{  
    SampleGenericDelegate<String> dString = () => " ";  
  
    // You can assign the dObject delegate  
    // to the same lambda expression as dString delegate  
    // because of the variance support for   
    // matching method signatures with delegate types.  
    SampleGenericDelegate<Object> dObject = () => " ";  
  
    // The following statement generates a compiler error  
    // because the generic type T is not marked as covariant.  
    // SampleGenericDelegate <Object> dObject = dString;  
  
}  
```  
  
### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a>Универсальные методы-делегаты с вариативными параметрами типа в .NET Framework  
 В платформе .NET Framework 4 появилась поддержка вариативности для параметров универсального типа в нескольких существующих методах-делегатах.  
  
- Делегаты `Action` из пространства имен <xref:System>, например <xref:System.Action%601> и <xref:System.Action%602>  
  
- Делегаты `Func` из пространства имен <xref:System>, например <xref:System.Func%601> и <xref:System.Func%602>  
  
- Делегат <xref:System.Predicate%601>  
  
- Делегат <xref:System.Comparison%601>  
  
- Делегат <xref:System.Converter%602>  
  
 Дополнительные примеры см. в разделе [Использование вариативности в универсальных методах-делегатах Func и Action (C#)](./using-variance-for-func-and-action-generic-delegates.md).  
  
### <a name="declaring-variant-type-parameters-in-generic-delegates"></a>Объявление вариативных параметров типа в универсальных методах-делегатах  
 Если универсальный метод-делегат содержит ковариантные или контравариантные параметры универсального типа, он называется *вариативным универсальным методом-делегатом*.  
  
 Для объявления ковариантного параметра универсального типа в универсальном методе-делегате можно использовать ключевое слово `out`. Ковариантный тип можно использовать только в качестве типа значения, возвращаемого методом, и нельзя использовать в качестве типа аргументов метода. В следующем примере кода показано, как объявить ковариантный универсальный метод-делегат.  
  
```csharp  
public delegate R DCovariant<out R>();  
```  
  
 Для объявления контравариантного параметра универсального типа в универсальном методе-делегате можно использовать ключевое слово `in`. Контравариантный тип можно использовать только в качестве типа аргументов метода, и нельзя использовать в качестве типа значения, возвращаемого методом. В следующем примере кода показано, как объявить контравариантный универсальный метод-делегат.  
  
```csharp  
public delegate void DContravariant<in A>(A a);  
```  
  
> [!IMPORTANT]
> Параметры `ref`, `in` и `out` в C# невозможно пометить как вариативные.  
  
 В одном делегате можно реализовать поддержку вариативности и ковариации, но для разных параметров типа. Эти действия показаны в следующем примере.  
  
```csharp  
public delegate R DVariant<in A, out R>(A a);  
```  
  
### <a name="instantiating-and-invoking-variant-generic-delegates"></a>Создание экземпляра и вызов вариативных универсальных методов-делегатов  
 Создание экземпляра и вызов вариативных делегатов возможен только при создании экземпляра и вызове инвариантных делегатов. В следующем примере создается экземпляр делегата с помощью лямбда-выражения.  
  
```csharp  
DVariant<String, String> dvariant = (String str) => str + " ";  
dvariant("test");  
```  
  
### <a name="combining-variant-generic-delegates"></a>Объединение вариативных универсальных методов-делегатов  
 Не следует объединять вариантные делегаты. Метод <xref:System.Delegate.Combine%2A> не поддерживает преобразование вариантных делегатов и ожидает делегаты того же самого типа. Это может вызвать исключение времени выполнения при объединении делегатов с помощью метода <xref:System.Delegate.Combine%2A> или оператора `+`, как показано в следующем примере кода.  
  
```csharp  
Action<object> actObj = x => Console.WriteLine("object: {0}", x);  
Action<string> actStr = x => Console.WriteLine("string: {0}", x);  
// All of the following statements throw exceptions at run time.  
// Action<string> actCombine = actStr + actObj;  
// actStr += actObj;  
// Delegate.Combine(actStr, actObj);  
```  
  
## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a>Вариативность в параметрах универсального типа для значения и ссылочных типов  
 Вариативность для параметров универсального типа поддерживается только для ссылочных типов. Например, `DVariant<int>` нельзя неявно преобразовать в `DVariant<Object>` или `DVariant<long>`, поскольку integer является типом значения.  
  
 В следующем примере показано, что вариативность в параметрах универсального типа не поддерживается для типов значения.  
  
```csharp  
// The type T is covariant.  
public delegate T DVariant<out T>();  
  
// The type T is invariant.  
public delegate T DInvariant<T>();  
  
public static void Test()  
{  
    int i = 0;  
    DInvariant<int> dInt = () => i;  
    DVariant<int> dVariantInt = () => i;  
  
    // All of the following statements generate a compiler error  
    // because type variance in generic parameters is not supported  
    // for value types, even if generic type parameters are declared variant.  
    // DInvariant<Object> dObject = dInt;  
    // DInvariant<long> dLong = dInt;  
    // DVariant<Object> dVariantObject = dVariantInt;  
    // DVariant<long> dVariantLong = dVariantInt;              
}  
```  
  
## <a name="see-also"></a>См. также

- [Универсальные шаблоны](../../../../standard/generics/index.md)
- [Использование вариативности в универсальных методах-делегатах Func и Action (C#)](./using-variance-for-func-and-action-generic-delegates.md)
- [Практическое руководство. Объединение делегатов (многоадресные делегаты)](../../delegates/how-to-combine-delegates-multicast-delegates.md)
