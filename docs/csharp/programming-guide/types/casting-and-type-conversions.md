---
title: Руководство по программированию на C#. Приведение и преобразование типов
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- type conversion [C#]
- data type conversion [C#]
- numeric conversions [C#]
- conversions [C#], type
- casting [C#]
- converting types [C#]
ms.assetid: 568df58a-d292-4b55-93ba-601578722878
ms.openlocfilehash: 33195ef77e2f51e52cd9ed69a11b12bed8d9ead1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73969616"
---
# <a name="casting-and-type-conversions-c-programming-guide"></a>Руководство по программированию на C#. Приведение и преобразование типов

Поскольку код C# является статически типизированным во время компиляции, после объявления переменной ее нельзя объявить повторно или назначить ей значения другого типа, если этот тип невозможно неявно преобразовать в тип переменной. Например, `string` невозможно неявно преобразовать в `int`. Поэтому после объявления `i` как `int` нельзя назначить ей строку "Hello", как показано в следующем коде:
  
```csharp  
int i;  
i = "Hello"; // error CS0029: Cannot implicitly convert type 'string' to 'int'
```  
  
 Тем не менее иногда может потребоваться скопировать значение в переменную или параметр метода другого типа. Например, может потребоваться передать целочисленную переменную в метод, параметр которого имеет тип `double`. Или может понадобиться присвоить переменную класса переменной типа интерфейса. Такого рода операции называются *преобразованиями типа*. В C# можно выполнять следующие виды преобразований.  
  
- **Неявные преобразования**. Специальный синтаксис не требуется, так как преобразование является строго типизированным и данные не будут потеряны. Примеры включают преобразования из меньших в большие целочисленные типы и преобразования из производных классов в базовые классы.  
  
- **Явные преобразования (приведения)** . Для явных преобразований требуется [оператор приведения `()`](../../language-reference/operators/type-testing-and-cast.md#cast-operator-). Приведение требуется, если в ходе преобразования данные могут быть утрачены или преобразование может завершиться сбоем по другим причинам. Типичными примерами являются числовое преобразование в тип с меньшей точностью или меньшим диапазоном и преобразование экземпляра базового класса в производный класс.  
  
- **Пользовательские преобразования**. Такие преобразования выполняются специальными методами, которые можно определить для включения явных и неявных преобразований между пользовательскими типами без связи "базовый класс — производный класс". Дополнительные сведения см. в разделе [Операторы пользовательского преобразования](../../language-reference/operators/user-defined-conversion-operators.md).  
  
- **Преобразования с использованием вспомогательных классов**. Чтобы выполнить преобразование между несовместимыми типами, например целыми числами и объектами <xref:System.DateTime?displayProperty=nameWithType> или шестнадцатеричными строками и массивами байтов, можно использовать классы <xref:System.BitConverter?displayProperty=nameWithType> и <xref:System.Convert?displayProperty=nameWithType>, а также методы `Parse` встроенных числовых типов, такие как <xref:System.Int32.Parse%2A?displayProperty=nameWithType>. Дополнительные сведения см. в разделе [Практическое руководство. преобразованию массива байтов в значение типа int](./how-to-convert-a-byte-array-to-an-int.md), [ преобразованию строки в число](./how-to-convert-a-string-to-a-number.md) и [ преобразованию из шестнадцатеричных строк в числовые типы](./how-to-convert-between-hexadecimal-strings-and-numeric-types.md).  
  
## <a name="implicit-conversions"></a>Неявные преобразования

 Для встроенных числовых типов неявное преобразование можно выполнить, если сохраняемое значение может уместиться в переменной без усечения или округления. При использовании целочисленных типов это означает, что диапазон исходного типа является надлежащим подмножеством диапазона для целевого типа. Например, переменная типа [long](../../language-reference/builtin-types/integral-numeric-types.md) (64-разрядное целое число) может хранить любое значение, которое может хранить переменная [int](../../language-reference/builtin-types/integral-numeric-types.md) (32-разрядное целое число). В следующем примере компилятор неявно преобразует значение `num` справа в тип `long` перед назначением `bigNum`.  
  
 [!code-csharp[csProgGuideTypes#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#34)]  
  
 Полный список всех неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../language-reference/builtin-types/numeric-conversions.md#implicit-numeric-conversions) в статье [Встроенные числовые преобразования](../../language-reference/builtin-types/numeric-conversions.md).
  
 Для ссылочных типов неявное преобразование всегда предусмотрено из класса в любой из его прямых или косвенных базовых классов или интерфейсов. Никакой специальный синтаксис не требуется, поскольку производный класс всегда содержит все члены базового класса.  
  
```csharp
Derived d = new Derived();  
Base b = d; // Always OK.  
```  
  
## <a name="explicit-conversions"></a>Явные преобразования

 Тем не менее если преобразование нельзя выполнить без риска потери данных, компилятор требует выполнения явного преобразования, которое называется *приведением*. Приведение — это способ явно указать компилятору, что необходимо выполнить преобразование и что вам известно, что может произойти потеря данных. Чтобы выполнить приведение, укажите тип, в который производится приведение, в круглых скобках перед преобразуемым значением или переменной. В следующей программе выполняется приведение типа [double](../../language-reference/builtin-types/floating-point-numeric-types.md) в [int](../../language-reference/builtin-types/integral-numeric-types.md). Программа не будет компилироваться без приведения.  
  
 [!code-csharp[csProgGuideTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#2)]  
  
 Полный список всех поддерживаемых явных числовых преобразований см. в разделе [Таблица явных числовых преобразований](../../language-reference/builtin-types/numeric-conversions.md#explicit-numeric-conversions) в статье [Встроенные числовые преобразования](../../language-reference/builtin-types/numeric-conversions.md).
  
 Для ссылочных типов явное приведение является обязательным, если необходимо преобразовать базовый тип в производный тип:  
  
```csharp  
// Create a new derived type.  
Giraffe g = new Giraffe();  
  
// Implicit conversion to base type is safe.  
Animal a = g;  
  
// Explicit conversion is required to cast back  
// to derived type. Note: This will compile but will  
// throw an exception at run time if the right-side  
// object is not in fact a Giraffe.  
Giraffe g2 = (Giraffe) a;  
```  
  
 Операция приведения между ссылочными типами не меняет тип времени выполнения базового объекта; изменяется только тип значения, который используется в качестве ссылки на этот объект. Дополнительные сведения см. в разделе [Полиморфизм](../classes-and-structs/polymorphism.md).  
  
## <a name="type-conversion-exceptions-at-run-time"></a>Исключения преобразования типов во время выполнения

 В некоторых преобразованиях ссылочных типов компилятор не может определить, будет ли приведение допустимым. Есть вероятность, что правильно скомпилированная операция приведения завершится сбоем во время выполнения. Как показано в следующем примере, приведение типа, завершившееся сбоем во время выполнения, вызывает исключение <xref:System.InvalidCastException>.  
  
 [!code-csharp[csProgGuideTypes#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#41)]  
  
 C# предоставляет оператор [is](../../language-reference/operators/type-testing-and-cast.md#is-operator), чтобы можно было проверить совместимость перед фактическим выполнением приведения. Дополнительные сведения см. в статье [Практическое руководство. Безопасное приведение с помощью сопоставления шаблонов, а также операторов is и as](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md).  
  
## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Преобразования](~/_csharplang/spec/conversions.md) [спецификация языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Типы](./index.md)
- [Оператор приведения ()](../../language-reference/operators/type-testing-and-cast.md#cast-operator-)
- [Операторы пользовательского преобразования](../../language-reference/operators/user-defined-conversion-operators.md)
- [Обобщенное преобразование типов](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/yy580hbd(v=vs.120))
- [Практическое руководство. Преобразование строки в число](./how-to-convert-a-string-to-a-number.md)
