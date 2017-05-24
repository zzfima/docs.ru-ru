---
title: "Приведение и преобразование типов (руководство по программированию на C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- type conversion [C#]
- data type conversion [C#]
- numeric conversions [C#]
- conversions [C#], type
- casting [C#]
- converting types [C#]
ms.assetid: 568df58a-d292-4b55-93ba-601578722878
caps.latest.revision: 52
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 7e33ed084c560470a486ebbb25035a59ddc18565
ms.openlocfilehash: d421f0115642efa73dbeb893dba912b96d5f4dc6
ms.contentlocale: ru-ru
ms.lasthandoff: 03/31/2017

---
# <a name="casting-and-type-conversions-c-programming-guide"></a>Приведение и преобразование типов (Руководство по программированию на C#)
Поскольку код C# является статически типизированным во время компиляции, после объявления переменной ее нельзя объявить повторно или использовать для хранения значений другого типа, если этот тип не преобразуется в тип переменной. Например, отсутствует преобразование из целого числа в произвольную строку. Поэтому после объявления `i` как целого числа нельзя назначить ей строку "Hello", как показано в следующем коде.  
  
```csharp  
int i;  
i = "Hello"; // Error: "Cannot implicitly convert type 'string' to 'int'"  
```  
  
 Тем не менее иногда может потребоваться скопировать значение в переменную или параметр метода другого типа. Например, может потребоваться передать целочисленную переменную в метод, параметр которого имеет тип `double`. Или может понадобиться присвоить переменную класса переменной типа интерфейса. Такого рода операции называются *преобразованиями типа*. В C# можно выполнять следующие виды преобразований.  
  
-   **Неявные преобразования**: никакой специальный синтаксис не требуется, поскольку преобразование является строго типизированным и данные не будут потеряны. Примеры включают преобразования из меньших в большие целочисленные типы и преобразования из производных классов в базовые классы.  
  
-   **Явные преобразования (приведения)**: явные преобразования требуют оператора приведения. Приведение требуется, если в ходе преобразования данные могут быть утрачены или преобразование может завершиться сбоем по другим причинам.  Типичными примерами являются числовое преобразование в тип с меньшей точностью или меньшим диапазоном и преобразование экземпляра базового класса в производный класс.  
  
-   **Заданные пользователем преобразования**: пользовательские преобразования выполняются специальными методами, которые можно определить для включения явных и неявных преобразований между пользовательскими типами, не имеющими отношения "базовый класс-производный класс". Дополнительные сведения см. в разделе [Операторы преобразования](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md).  
  
-   **Преобразования с помощью вспомогательных классов**: для выполнения преобразований несовместимых типов, таких как целые числа и объекты <xref:System.DateTime?displayProperty=fullName> или шестнадцатеричные строки и массивы байтов, можно использовать класс <xref:System.BitConverter?displayProperty=fullName>, класс <xref:System.Convert?displayProperty=fullName> и методы `Parse` встроенных числовых типов, таких как <xref:System.Int32.Parse%2A?displayProperty=fullName>. Дополнительные сведения см. в разделе [Практическое руководство. Преобразование массива байтов в значение типа int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [Практическое руководство. Преобразование строки в число](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md) и [Практическое руководство. Преобразование из шестнадцатеричных строк в числовые типы](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).  
  
## <a name="implicit-conversions"></a>Неявные преобразования  
 Для встроенных числовых типов неявное преобразование можно выполнить, если сохраняемое значение может уместиться в переменной без усечения или округления. Например, переменная типа [long](../../../csharp/language-reference/keywords/long.md) (8-байтное целое число) может хранить любое значение, которое может хранить переменная [int](../../../csharp/language-reference/keywords/int.md) (4 байта в 32-разрядных системах). В следующем примере компилятор неявно преобразует значение справа в тип `long` перед назначением его `bigNum`.  
  
 [!code-cs[csProgGuideTypes#34](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_1.cs)]  
  
 Полный список всех неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
 Для ссылочных типов неявное преобразование всегда предусмотрено из класса в любой из его прямых или косвенных базовых классов или интерфейсов. Никакой специальный синтаксис не требуется, поскольку производный класс всегда содержит все члены базового класса.  
  
```  
Derived d = new Derived();  
Base b = d; // Always OK.  
```  
  
## <a name="explicit-conversions"></a>Явные преобразования  
 Тем не менее если преобразование нельзя выполнить без риска потери данных, компилятор требует выполнения явного преобразования, которое называется *приведением*. Приведение — это способ явно указать компилятору, что необходимо выполнить преобразование и что вам известно, что может произойти потеря данных. Чтобы выполнить приведение, укажите тип, в который производится приведение, в круглых скобках перед преобразуемым значением или переменной. В следующей программе выполняется приведение типа [double](../../../csharp/language-reference/keywords/double.md) в [int](../../../csharp/language-reference/keywords/int.md). Программа не будет компилироваться без приведения.  
  
 [!code-cs[csProgGuideTypes#2](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_2.cs)]  
  
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
  
 [!code-cs[csProgGuideTypes#41](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_3.cs)]  
  
 C# предоставляет операторы [is](../../../csharp/language-reference/keywords/is.md) и [as](../../../csharp/language-reference/keywords/as.md), чтобы можно было проверить совместимость перед фактическим выполнением приведения. Дополнительные сведения см. в разделе [Практическое руководство. Безопасное приведение с помощью операторов as и is](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md).  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  

## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Типы](../../../csharp/programming-guide/types/index.md)   
 [Оператор ()](../../../csharp/language-reference/operators/invocation-operator.md)   
 [explicit](../../../csharp/language-reference/keywords/explicit.md)   
 [implicit](../../../csharp/language-reference/keywords/implicit.md)   
 [Операторы преобразования](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)   
 [Обобщенное преобразование типов](http://msdn.microsoft.com/library/49253ae6-7657-4810-82ab-1176a6feeada)   
 [Преобразование экспортированного типа](http://msdn.microsoft.com/en-us/1dfe55f4-07a2-4b61-aabf-a8cf65783a6b)   
 [Практическое руководство. Преобразование строки в число](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)
