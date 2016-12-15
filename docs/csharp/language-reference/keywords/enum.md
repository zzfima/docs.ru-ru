---
title: "enum (Справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "enum"
  - "enum_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "enum - ключевое слово [C#]"
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
caps.latest.revision: 36
caps.handback.revision: 36
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# enum (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ключевое слово `enum` используется для объявления перечисления — отдельного типа, который состоит из набора именованных констант, называемого списком перечислителей.  
  
 Обычно лучше всего определять перечисление непосредственно в пространстве имен, чтобы всем классам в пространстве имен было одинаково удобно обращаться к нему. Однако перечисление также может быть вложенным в классе или структуре.  
  
 По умолчанию первый перечислитель имеет значение 0, и значение каждого последующего перечислителя увеличивается на 1. Например, в следующем перечислении `Sat` — `0`, `Sun` — `1`, `Mon` — `2` и т. д.  
  
```  
  
enum Days {Sat, Sun, Mon, Tue, Wed, Thu, Fri};  
```  
  
 Перечисления могут использовать инициализаторы для переопределения значений по умолчанию, как показано в следующем примере.  
  
```  
  
enum Days {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};  
```  
  
 В этом перечислении последовательность элементов принудительно начинается с `1` вместо `0`. Тем не менее рекомендуется, включая константу, которая имеет значение “0”. Для получения дополнительной информации см. [Типы перечислений](../../../csharp/programming-guide/enumeration-types.md).  
  
 Каждый тип перечисления имеет базовый тип, который может быть любым целочисленным типом за исключением [char](../../../csharp/language-reference/keywords/char.md). Базовым типом перечисления элементов по умолчанию является [int](../../../csharp/language-reference/keywords/int.md). Чтобы объявить перечисление другого целого типа, например [byte](../../../csharp/language-reference/keywords/byte.md), используется двоеточие после идентификатора, за которым следует тип, как показано в следующем примере.  
  
```  
  
enum Days : byte {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};  
```  
  
 Утвержденные типы для перечисления: `byte`, [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) и [ulong](../../../csharp/language-reference/keywords/ulong.md).  
  
 Переменной типа `Days` может быть присвоено любое значение в диапазоне базового типа; значения не ограничиваются именованными константами.  
  
 Значение по умолчанию `enum E` является значением, полученным с помощью выражения `(E)0`.  
  
> [!NOTE]
>  Перечислитель не может содержать пробелы в имени.  
  
 Базовый тип указывает, какой объем хранилища выделяется для каждого перечислителя. Тем не менее необходимо явное приведение, чтобы преобразовывать из типа `enum` в целочисленный тип. Например, следующий оператор назначает перечислитель `Sun` для переменной типа [int](../../../csharp/language-reference/keywords/int.md) с помощью приведения, чтобы преобразовать `enum` в `int`.  
  
```  
  
int x = (int)Days.Sun;  
```  
  
 При применении <xref:System.FlagsAttribute?displayProperty=fullName> к перечислению, содержащему элементы, которые могут быть объединены с помощью побитовой операции `OR`, атрибут влияет на поведение `enum` при использовании с некоторыми средствами. Эти изменения можно заметить при использовании таких средств, как методы класса <xref:System.Console> и вычислитель выражений. \(См. третий пример.\)  
  
## Отказоустойчивость  
 Как и в случае с любой другой константой, все ссылки на отдельные значения перечисления преобразуются в числовые литералы во время компиляции. Это может создать потенциальные проблемы с управлением версиями, как описано в [Константы](../../../csharp/programming-guide/classes-and-structs/constants.md).  
  
 Назначение дополнительных значений для новых версий перечислений или изменение значений элементов перечислений в новой версии может вызвать проблемы в зависимом исходном коде. Значения перечислений часто используются в инструкциях [switсh](../../../csharp/language-reference/keywords/switch.md). Если были добавлены дополнительные элементы для типа `enum`, раздел по умолчанию инструкции switch может быть выбран неожиданным образом.  
  
 Если другие разработчики используют ваш код, необходимо предоставить рекомендации о том, как их код должен реагировать при добавлении новых элементов к любому типу `enum`.  
  
## Пример  
 В следующем примере объявлено перечисление `Days`. Два перечислителя явно преобразуются в целое число и назначаются для целочисленных переменных.  
  
 [!code-cs[csrefKeywordsTypes#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_1.cs)]  
  
## Пример  
 В следующем примере используется параметр базового типа для объявления `enum`, члены которого имеют тип `long`. Обратите внимание, что, даже если базовый тип перечисления является `long`, члены перечисления по\-прежнему должны быть явно преобразованы в тип `long` с помощью приведения.  
  
 [!code-cs[csrefKeywordsTypes#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_2.cs)]  
  
## Пример  
 В следующем примере кода показано использование и влияние атрибута <xref:System.FlagsAttribute?displayProperty=fullName> на объявление `enum`.  
  
 [!code-cs[csrefKeywordsTypes#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_3.cs)]  
  
## Комментарии  
 Если удалить `Flags`, в примере будут показаны следующие значения.  
  
 `5`  
  
 `5`  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Типы перечислений](../../../csharp/programming-guide/enumeration-types.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)