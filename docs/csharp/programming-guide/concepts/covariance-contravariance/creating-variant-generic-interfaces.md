---
title: Создание вариантных универсальных интерфейсов (C#)
ms.date: 07/20/2015
ms.assetid: 30330ec4-9df2-4838-a535-6c406d0ed4df
ms.openlocfilehash: 4ba72f28cd2ddd800f169387cc2c742159d4cb1b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "69595305"
---
# <a name="creating-variant-generic-interfaces-c"></a>Создание вариантных универсальных интерфейсов (C#)

Параметры универсального типа можно объявить в интерфейсах как ковариантные или контравариантные. *Ковариация* позволяет методам интерфейса иметь тип возвращаемого значения, степень наследования которого больше, чем указано в параметрах универсального типа. *Контравариантность* позволяет методам интерфейса иметь типы аргументов, степень наследования которых меньше, чем указано в параметре универсального типа. Универсальный интерфейс, который имеет ковариантные или контравариантные параметры универсального типа, называется *вариантным*.

> [!NOTE]
> В платформе .NET Framework 4 появилась поддержка вариативности для нескольких существующих универсальных интерфейсов. Список вариантных интерфейсов в .NET Framework см. в разделе [Вариативность в универсальных интерфейсах (C#)](./variance-in-generic-interfaces.md).

## <a name="declaring-variant-generic-interfaces"></a>Объявление вариантных универсальных интерфейсов

Вариантные универсальные интерфейсы можно объявить с помощью ключевых слов `in` и `out` для параметров универсального типа.

> [!IMPORTANT]
> Параметры `ref`, `in` и `out` в C# не могут быть вариантными. Типы значений также не поддерживают вариативность.

Для объявления ковариантного параметра универсального типа можно использовать ключевое слово `out`. Ковариантный тип должен удовлетворять следующим условиям:

- Тип используется только в качестве типа значения, возвращаемого методами интерфейса, и не используется в качестве типа аргументов метода. Это показано в следующем примере, в котором тип `R` объявлен ковариантным.

    ```csharp
    interface ICovariant<out R>
    {
        R GetSomething();
        // The following statement generates a compiler error.
        // void SetSomething(R sampleArg);

    }
    ```

    Существует одно исключение из данного правила. Если в качестве параметра метода используется контравариантный универсальный делегат, этот тип можно использовать в качестве параметра универсального типа для этого делегата. Это продемонстрировано ниже на примере типа `R`. Дополнительные сведения см. в разделах [Вариативность в делегатах (C#)](./variance-in-delegates.md) и [Использование вариативности в универсальных методах-делегатах Func и Action (C#)](./using-variance-for-func-and-action-generic-delegates.md).

    ```csharp
    interface ICovariant<out R>
    {
        void DoSomething(Action<R> callback);
    }
    ```

- Тип не используется в качестве универсального ограничения для методов интерфейса. Это демонстрируется в следующем примере кода.

    ```csharp
    interface ICovariant<out R>
    {
        // The following statement generates a compiler error
        // because you can use only contravariant or invariant types
        // in generic constraints.
        // void DoSomething<T>() where T : R;
    }
    ```

Для объявления контравариантного параметра универсального типа можно использовать ключевое слово `in`. Контравариантный тип можно использовать только в качестве типа аргументов метода, но не в качестве типа значения, возвращаемого методами интерфейса. Контравариантный тип можно также использовать для универсальных ограничений. В следующем примере кода показано объявление контравариантного интерфейса и использование универсального ограничения для одного из его методов.

```csharp
interface IContravariant<in A>
{
    void SetSomething(A sampleArg);
    void DoSomething<T>() where T : A;
    // The following statement generates a compiler error.
    // A GetSomething();
}
```

Кроме того, можно реализовать поддержку ковариации и контравариации в одном интерфейсе, но для разных параметров типа, как показано в следующем примере кода.

```csharp
interface IVariant<out R, in A>
{
    R GetSomething();
    void SetSomething(A sampleArg);
    R GetSetSomethings(A sampleArg);
}
```

## <a name="implementing-variant-generic-interfaces"></a>Реализация вариантных универсальных интерфейсов

Для реализации вариантных универсальных интерфейсов в классах используется тот же синтаксис, что и для инвариантных интерфейсов. В следующем примере кода показана реализация ковариантного интерфейса в универсальном классе.

```csharp
interface ICovariant<out R>
{
    R GetSomething();
}
class SampleImplementation<R> : ICovariant<R>
{
    public R GetSomething()
    {
        // Some code.
        return default(R);
    }
}
```

Классы, которые реализуют вариантные интерфейсы, являются инвариантными. Например, рассмотрим следующий код.

```csharp
// The interface is covariant.
ICovariant<Button> ibutton = new SampleImplementation<Button>();
ICovariant<Object> iobj = ibutton;

// The class is invariant.
SampleImplementation<Button> button = new SampleImplementation<Button>();
// The following statement generates a compiler error
// because classes are invariant.
// SampleImplementation<Object> obj = button;
```

## <a name="extending-variant-generic-interfaces"></a>Расширение вариантных универсальных интерфейсов

При расширении вариантных универсальных интерфейсов необходимо использовать ключевые слова `in` и `out` для явного указания того, поддерживает ли вариативность производный интерфейс. Компилятор не подразумевает вариативность интерфейса, который расширяется. Например, рассмотрим следующие интерфейсы.

```csharp
interface ICovariant<out T> { }
interface IInvariant<T> : ICovariant<T> { }
interface IExtCovariant<out T> : ICovariant<T> { }
```

В интерфейсе `IInvariant<T>` параметр универсального типа `T` является инвариантным, тогда как в `IExtCovariant<out T>` параметр типа является ковариантным, хотя оба интерфейса расширяют один и тот же интерфейс. То же правило применяется к контравариантным параметрам универсального типа.

Можно создать интерфейс, который расширяет и интерфейс, в котором параметр универсального типа `T` является ковариантным, и интерфейс, где он является контравариантным, если в расширяемом интерфейсе параметр универсального типа `T` является инвариантным. Это показано в следующем примере кода.

```csharp
interface ICovariant<out T> { }
interface IContravariant<in T> { }
interface IInvariant<T> : ICovariant<T>, IContravariant<T> { }
```

Тем не менее, если параметр универсального типа `T` объявлен ковариантным в одном интерфейсе, его нельзя объявить контравариантным в расширенном интерфейсе и наоборот. Это показано в следующем примере кода.

```csharp
interface ICovariant<out T> { }
// The following statement generates a compiler error.
// interface ICoContraVariant<in T> : ICovariant<T> { }
```

### <a name="avoiding-ambiguity"></a>Недопущение неоднозначности

При реализации вариантных универсальных интерфейсов вариативность может приводить к неоднозначности. Этого следует избегать.

Например, если вы явно реализуете один вариантный универсальный интерфейс с разными параметрами универсального типа в одном классе, это может создавать неоднозначность. Компилятор не сообщает об ошибке в данном случае, но и не указывает, какая реализация интерфейса будет выбрана во время выполнения. Это может привести к возникновению неявных ошибок в коде. Рассмотрим следующий пример кода:

```csharp
// Simple class hierarchy.
class Animal { }
class Cat : Animal { }
class Dog : Animal { }

// This class introduces ambiguity
// because IEnumerable<out T> is covariant.
class Pets : IEnumerable<Cat>, IEnumerable<Dog>
{
    IEnumerator<Cat> IEnumerable<Cat>.GetEnumerator()
    {
        Console.WriteLine("Cat");
        // Some code.
        return null;
    }

    IEnumerator IEnumerable.GetEnumerator()
    {
        // Some code.
        return null;
    }

    IEnumerator<Dog> IEnumerable<Dog>.GetEnumerator()
    {
        Console.WriteLine("Dog");
        // Some code.
        return null;
    }
}
class Program
{
    public static void Test()
    {
        IEnumerable<Animal> pets = new Pets();
        pets.GetEnumerator();
    }
}
```

В этом примере не указано, каким образом метод `pets.GetEnumerator` делает выбор между `Cat` и `Dog`. Это может вызвать проблемы в вашем коде.

## <a name="see-also"></a>См. также раздел

- [Вариативность в универсальных интерфейсах (C#)](./variance-in-generic-interfaces.md)
- [Использование вариативности в универсальных методах-делегатах Func и Action (C#)](./using-variance-for-func-and-action-generic-delegates.md)
