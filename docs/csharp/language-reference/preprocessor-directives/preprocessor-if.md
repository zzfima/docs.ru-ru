---
title: '#Справочник по C#. Директива препроцессора if'
ms.date: 10/27/2019
f1_keywords:
- '#if'
helpviewer_keywords:
- '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
ms.openlocfilehash: d047b88f202341a795834809d0b601706c30fcb4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75899856"
---
# <a name="if-c-reference"></a>Справочник по C#. #if

Когда компилятор C# встречает директиву `#if`, за которой следует директива [#endif](preprocessor-endif.md), код между этими директивами он компилирует, только когда определен указанный символ. В отличие от С и С++ здесь нельзя назначить символу числовое значение. Оператор `#if` в C# является логическим. Он проверяет только одно условие — определен ли указанный символ. Пример:

```csharp
#if DEBUG
    Console.WriteLine("Debug version");
#endif
```

Операторы [==](../operators/equality-operators.md#equality-operator-) (равенство) и [!=](../operators/equality-operators.md#inequality-operator-) (неравенство) можно использовать только для проверки значений [bool](../builtin-types/bool.md)`true` или `false`. Значение `true` означает, что символ определен. Инструкция `#if DEBUG` имеет то же значение, что и `#if (DEBUG == true)`. Вы можете использовать операторы [&& (и)](../operators/boolean-logical-operators.md#conditional-logical-and-operator-), [&#124;&#124; (или)](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) и [! (не)](../operators/boolean-logical-operators.md#logical-negation-operator-), чтобы узнать, определено ли несколько символов. Можно также группировать символы и операторы при помощи скобок.

## <a name="remarks"></a>Remarks

`#if`, как и директивы [#else](preprocessor-else.md), [#elif](preprocessor-elif.md), [#endif](preprocessor-endif.md), [#define](preprocessor-define.md) и [#undef](preprocessor-undef.md), позволяет включить или исключить код в зависимости от существования одного или нескольких символов. Это может быть полезно при компиляции кода для отладки или для определенной конфигурации.

Условные директивы, начинающиеся с директивы `#if`, должны явным образом завершаться директивой `#endif`.

`#define` позволяет определить символ, чтобы директива `#if`, которой передается этот символ, возвращала значение `true`.

Также символ можно определить с помощью параметра компилятора [-define](../compiler-options/define-compiler-option.md). Для отмены определения символа служит директива [#undef](preprocessor-undef.md).

Символ, определенный с помощью `-define` или `#define`, не конфликтует с одноименной переменной. Соответственно, имя переменной не должно передаваться директиве препроцессора, а символ может использоваться только в директиве препроцессора.

Символ, создаваемый с помощью `#define`, будет определен в пределах того файл, в котором он определен.

Система сборки также учитывает символы препроцессора, представляющие [целевые платформы](../../../standard/frameworks.md) в проектах в стиле SDK. Они полезны при создании приложений, предназначенных для нескольких реализаций или версий .NET.

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

> [!NOTE]
> Для традиционных проектов .NET Framework необходимо вручную настроить символы условной компиляции для различных целевых платформ в Visual Studio с помощью страниц свойств проекта.

Другие предопределенные символы включают константы DEBUG и TRACE. Вы можете переопределить значения для проектов с помощью `#define`. Например, символ DEBUG автоматически устанавливается в зависимости от свойств конфигурации сборки (в режиме отладки или выпуска).

## <a name="examples"></a>Примеры

В следующем примере показано, как определить символ MYTEST в файле и затем протестировать значения символов MYTEST и DEBUG. Выходные данные этого примера зависят от режима конфигурации, в котором создан проект (режим отладки или выпуска).

```csharp
#define MYTEST
using System;
public class MyClass
{
    static void Main()
    {
#if (DEBUG && !MYTEST)
        Console.WriteLine("DEBUG is defined");
#elif (!DEBUG && MYTEST)
        Console.WriteLine("MYTEST is defined");
#elif (DEBUG && MYTEST)
        Console.WriteLine("DEBUG and MYTEST are defined");  
#else
        Console.WriteLine("DEBUG and MYTEST are not defined");
#endif
    }
}
```

В следующем примере показано, как тестировать разные целевые платформы для использования более новых интерфейсов API, когда это возможно:

```csharp
public class MyClass
{
    static void Main()
    {
#if NET40
        WebClient _client = new WebClient();
#else
        HttpClient _client = new HttpClient();
#endif
    }
    //...
}
```

## <a name="see-also"></a>См. также раздел

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Директивы препроцессора C#](index.md)
- [Практическое руководство. Условная компиляция с использованием атрибутов Trace и Debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)
