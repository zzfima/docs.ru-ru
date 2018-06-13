---
title: enum (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- enum
- enum_CSharpKeyword
helpviewer_keywords:
- enum keyword [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
ms.openlocfilehash: 9714277f87095b709e37b582cd3435374d9a1555
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172232"
---
# <a name="enum-c-reference"></a>enum (Справочник по C#)
Ключевое слово `enum` используется для объявления перечисления — отдельного типа, который состоит из набора именованных констант, называемого списком перечислителей.  
  
 Обычно лучше всего определять перечисление непосредственно в пространстве имен, чтобы всем классам в пространстве имен было одинаково удобно обращаться к нему. Однако перечисление также может быть вложенным в классе или структуре.  
  
 По умолчанию первый перечислитель имеет значение 0, и значение каждого последующего перечислителя увеличивается на 1. Например, в следующем перечислении `Sat` — `0`, `Sun` — `1`, `Mon` — `2`и т. д.  
  
```csharp  
enum Day {Sat, Sun, Mon, Tue, Wed, Thu, Fri};  
```  
  
 Перечисления могут использовать инициализаторы для переопределения значений по умолчанию, как показано в следующем примере.  
  
```csharp  
enum Day {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};  
```  
  
 В этом перечислении последовательность элементов принудительно начинается с `1` вместо `0`. Тем не менее рекомендуется, включая константу, которая имеет значение “0”. Дополнительные сведения см. в разделе [Типы перечислений](../../../csharp/programming-guide/enumeration-types.md).  
  
 Каждый тип перечисления имеет базовый тип, который может быть любым целочисленным типом за исключением [char](../../../csharp/language-reference/keywords/char.md). Базовым типом перечисления элементов по умолчанию является [int](../../../csharp/language-reference/keywords/int.md). Чтобы объявить перечисление другого целого типа, например [byte](../../../csharp/language-reference/keywords/byte.md), используется двоеточие после идентификатора, за которым следует тип, как показано в следующем примере.  
  
```csharp  
enum Day : byte {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};  
```  
  
 Утвержденные типы для перечисления: [byte](../../../csharp/language-reference/keywords/byte.md), [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) и [ulong](../../../csharp/language-reference/keywords/ulong.md).  
  
 Переменной типа `Day` может быть присвоено любое значение в диапазоне базового типа; значения не ограничиваются именованными константами.  
  
 Значение по умолчанию `enum E` является значением, полученным с помощью выражения `(E)0`.  
  
> [!NOTE]
>  Перечислитель не может содержать пробелы в имени.  
  
 Базовый тип указывает, какой объем хранилища выделяется для каждого перечислителя. Тем не менее необходимо явное приведение, чтобы преобразовывать из типа `enum` в целочисленный тип. Например, следующий оператор назначает перечислитель `Sun` для переменной типа [int](../../../csharp/language-reference/keywords/int.md) с помощью приведения, чтобы преобразовать `enum` в `int`.  
  
```csharp  
int x = (int)Day.Sun;  
```  
  
 При применении <xref:System.FlagsAttribute?displayProperty=nameWithType> к перечислению, содержащему элементы, которые могут быть объединены с помощью побитовой операции `OR` , атрибут влияет на поведение `enum` при использовании с некоторыми средствами. Эти изменения можно заметить при использовании таких средств, как методы класса <xref:System.Console> и вычислитель выражений. (См. третий пример.)  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Как и в случае с любой другой константой, все ссылки на отдельные значения перечисления преобразуются в числовые литералы во время компиляции. Это может создать потенциальные проблемы с управлением версиями, как описано в разделе [Константы](../../../csharp/programming-guide/classes-and-structs/constants.md).  
  
 Назначение дополнительных значений для новых версий перечислений или изменение значений элементов перечислений в новой версии может вызвать проблемы в зависимом исходном коде. Значения перечислений часто используются в инструкциях [switсh](../../../csharp/language-reference/keywords/switch.md) . Если были добавлены дополнительные элементы для типа `enum` , раздел по умолчанию инструкции switch может быть выбран неожиданным образом.  
  
 Если другие разработчики используют ваш код, необходимо предоставить рекомендации о том, как их код должен реагировать при добавлении новых элементов к любому типу `enum` .  
  
## <a name="example"></a>Пример  
 В следующем примере объявлено перечисление `Day`. Два перечислителя явно преобразуются в целое число и назначаются для целочисленных переменных.  
  
 [!code-csharp[csrefKeywordsTypes#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_1.cs)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется параметр базового типа для объявления `enum` , члены которого имеют тип `long`. Обратите внимание, что, даже если базовый тип перечисления является `long`, члены перечисления по-прежнему должны быть явно преобразованы в тип `long` с помощью приведения.  
  
 [!code-csharp[csrefKeywordsTypes#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_2.cs)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано использование и влияние атрибута <xref:System.FlagsAttribute?displayProperty=nameWithType> на объявление `enum` .  
  
 [!code-csharp[csrefKeywordsTypes#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_3.cs)]  
  
## <a name="comments"></a>Комментарии  
 Если удалить `Flags`, в примере будут показаны следующие значения.  
  
 `5`  
  
 `5`  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Типы перечисления](../../../csharp/programming-guide/enumeration-types.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
 [Соглашения об именовании перечислений](https://docs.microsoft.com/en-us/dotnet/standard/design-guidelines/names-of-classes-structs-and-interfaces#naming-enumerations)
