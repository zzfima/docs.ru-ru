---
title: '#Директива препроцессора if (справочник по C#)'
ms.date: 02/13/2017
f1_keywords:
- '#if'
helpviewer_keywords:
- '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
ms.openlocfilehash: 2ae0af6971dbf549b52e8168e035d8582bdab61d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="if-c-reference"></a>#if (Справочник по C#)

Когда компилятор C# встречает директиву `#if`, за которой следует директива [#endif](preprocessor-endif.md), код между этими директивами он компилирует, только когда определен указанный символ. В отличие от С и С++ здесь нельзя назначить символу числовое значение. Оператор #if в C# является логическим. Он проверяет только одно условие — определен ли указанный символ. Пример:

```csharp
#if DEBUG
    Console.WriteLine("Debug version");
#endif
```

Операторы [==](../operators/equality-comparison-operator.md) (равенство) и [! =](../operators/not-equal-operator.md) (неравенство) вы можете использовать только для проверки значений [true](../keywords/true.md) или [false](../keywords/false.md). Значение true означает, что символ определен. Инструкция `#if DEBUG` имеет то же значение, что и `#if (DEBUG == true)`. Вы можете использовать операторы [&&](../operators/conditional-and-operator.md) (логическое И), [& #124;&#124;](../operators/conditional-or-operator.md) (логическое ИЛИ) и [!](../operators/logical-negation-operator.md) (логическое НЕ) для проверки нескольких символов. Можно также группировать символы и операторы при помощи скобок.

## <a name="remarks"></a>Примечания

`#if`, как и директивы [#else](preprocessor-else.md), [#elif](preprocessor-elif.md), [#endif](preprocessor-endif.md), [#define](preprocessor-define.md) и [#undef](preprocessor-undef.md), позволяет включить или исключить код в зависимости от существования одного или нескольких символов. Это может быть полезно при компиляции кода для отладки или для определенной конфигурации.

Условные директивы, начинающиеся с директивы `#if`, должны явным образом завершаться директивой `#endif`.

`#define` позволяет определить символ, чтобы директива `#if`, которой передается этот символ, возвращала значение `true`.

Также символ можно определить с помощью параметра компилятора [/define](../compiler-options/define-compiler-option.md). Для отмены определения символа служит директива [#undef](preprocessor-undef.md).

Символ, определенный с помощью `/define` или `#define`, не конфликтует с одноименной переменной. Соответственно, имя переменной не должно передаваться директиве препроцессора, а символ может использоваться только в директиве препроцессора.

Символ, создаваемый с помощью `#define`, будет определен в пределах того файл, в котором он определен.

Система сборки также учитывает символы препроцессора, представляющие [целевые платформы](../../../standard/frameworks.md). Они полезны при создании приложений, предназначенных для нескольких реализаций или версий .NET.

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

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

## <a name="see-also"></a>См. также

[Справочник по C#](../../../csharp/language-reference/index.md)  
[Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
[Директивы препроцессора C#](index.md)  
[Практическое руководство. Условная компиляция с использованием атрибутов Trace и Debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md).
