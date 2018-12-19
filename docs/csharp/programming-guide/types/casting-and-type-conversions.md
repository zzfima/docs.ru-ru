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
ms.openlocfilehash: c7200f9d99eea8364d290b54efc514217f2b2dad
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245471"
---
# <a name="casting-and-type-conversions-c-programming-guide"></a>Приведение и преобразование типов (Руководство по программированию на C#)

Поскольку код C# является статически типизированным во время компиляции, после объявления переменной ее нельзя объявить повторно или назначить ей значения другого типа, если этот тип невозможно неявно преобразовать в тип переменной. Например, `string` невозможно неявно преобразовать в `int`. Поэтому после объявления `i` как `int` нельзя назначить ей строку "Hello", как показано в следующем коде:
  
```csharp  
int i;  
i = "Hello"; // error CS0029: Cannot implicitly convert type 'string' to 'int'
```  
  
 Тем не менее иногда может потребоваться скопировать значение в переменную или параметр метода другого типа. Например, может потребоваться передать целочисленную переменную в метод, параметр которого имеет тип `double`. Или может понадобиться присвоить переменную класса переменной типа интерфейса. Такого рода операции называются *преобразованиями типа*. В C# можно выполнять следующие виды преобразований.  
  
-   **Неявные преобразования**. Специальный синтаксис не требуется, так как преобразование является строго типизированным и данные не будут потеряны. Примеры включают преобразования из меньших в большие целочисленные типы и преобразования из производных классов в базовые классы.  
  
-   **Явные преобразования (приведения)**. Для явных преобразований требуется оператор приведения. Приведение требуется, если в ходе преобразования данные могут быть утрачены или преобразование может завершиться сбоем по другим причинам.  Типичными примерами являются числовое преобразование в тип с меньшей точностью или меньшим диапазоном и преобразование экземпляра базового класса в производный класс.  
  
-   **Пользовательские преобразования**. Такие преобразования выполняются специальными методами, которые можно определить для включения явных и неявных преобразований между пользовательскими типами без связи "базовый класс — производный класс". Дополнительные сведения см. в разделе [Операторы преобразования](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md).  
  
-   **Преобразования с использованием вспомогательных классов**. Чтобы выполнить преобразование между несовместимыми типами, например целыми числами и объектами <xref:System.DateTime?displayProperty=nameWithType> или шестнадцатеричными строками и массивами байтов, можно использовать классы <xref:System.BitConverter?displayProperty=nameWithType> и <xref:System.Convert?displayProperty=nameWithType>, а также методы `Parse` встроенных числовых типов, такие как <xref:System.Int32.Parse%2A?displayProperty=nameWithType>. Дополнительные сведения см. в руководстве по [ преобразованию массива байтов в значение типа int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [ преобразованию строки в число](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md) и [ преобразованию из шестнадцатеричных строк в числовые типы](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).  
  
## <a name="implicit-conversions"></a>Неявные преобразования  
 Для встроенных числовых типов неявное преобразование можно выполнить, если сохраняемое значение может уместиться в переменной без усечения или округления. Например, переменная типа [long](../../../csharp/language-reference/keywords/long.md) (64-разрядное целое число) может хранить любое значение, которое может хранить переменная [int](../../../csharp/language-reference/keywords/int.md) (32-разрядное целое число). В следующем примере компилятор неявно преобразует значение `num` справа в тип `long` перед назначением `bigNum`.  
  
 [!code-csharp[csProgGuideTypes#34](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_1.cs)]  
  
 Полный список всех неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
 Для ссылочных типов неявное преобразование всегда предусмотрено из класса в любой из его прямых или косвенных базовых классов или интерфейсов. Никакой специальный синтаксис не требуется, поскольку производный класс всегда содержит все члены базового класса.  
  
```  
Derived d = new Derived();  
Base b = d; // Always OK.  
```  
  
## <a name="explicit-conversions"></a>Явные преобразования  
 Тем не менее если преобразование нельзя выполнить без риска потери данных, компилятор требует выполнения явного преобразования, которое называется *приведением*. Приведение — это способ явно указать компилятору, что необходимо выполнить преобразование и что вам известно, что может произойти потеря данных. Чтобы выполнить приведение, укажите тип, в который производится приведение, в круглых скобках перед преобразуемым значением или переменной. В следующей программе выполняется приведение типа [double](../../../csharp/language-reference/keywords/double.md) в [int](../../../csharp/language-reference/keywords/int.md). Программа не будет компилироваться без приведения.  
  
 [!code-csharp[csProgGuideTypes#2](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_2.cs)]  
  
 Список разрешенных явных числовых преобразований см. в разделе [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).  
  
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
  
 Операция приведения между ссылочными типами не меняет тип времени выполнения базового объекта; изменяется только тип значения, который используется в качестве ссылки на этот объект. Дополнительные сведения см. в разделе [Полиморфизм](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).  
  
## <a name="type-conversion-exceptions-at-run-time"></a>Исключения преобразования типов во время выполнения  
 В некоторых преобразованиях ссылочных типов компилятор не может определить, будет ли приведение допустимым. Есть вероятность, что правильно скомпилированная операция приведения завершится сбоем во время выполнения. Как показано в следующем примере, приведение типа, завершившееся сбоем во время выполнения, вызывает исключение <xref:System.InvalidCastException>.  
  
 [!code-csharp[csProgGuideTypes#41](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_3.cs)]  
  
 C# предоставляет операторы [is](../../../csharp/language-reference/keywords/is.md) и [as](../../../csharp/language-reference/keywords/as.md), чтобы можно было проверить совместимость перед фактическим выполнением приведения. Дополнительные сведения см. в руководстве по [ безопасному приведению с помощью сопоставления шаблонов, а также операторов as и is](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md).  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Типы](../../../csharp/programming-guide/types/index.md)  
- [Оператор ()](../../../csharp/language-reference/operators/invocation-operator.md)  
- [explicit](../../../csharp/language-reference/keywords/explicit.md)  
- [implicit](../../../csharp/language-reference/keywords/implicit.md)  
- [Операторы преобразования](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)  
- [Обобщенное преобразование типов](https://msdn.microsoft.com/library/49253ae6-7657-4810-82ab-1176a6feeada)  
- [Преобразование экспортированного типа](https://msdn.microsoft.com/library/1dfe55f4-07a2-4b61-aabf-a8cf65783a6b)  
- [Практическое руководство. Преобразование строки в число](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)
