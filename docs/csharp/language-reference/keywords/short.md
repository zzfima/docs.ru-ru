---
title: "short (справочник по C#) | Документ Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- short
- short_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- short keyword [C#]
ms.assetid: 04c10688-e51a-4a87-bfec-83f7fb42ff11
caps.latest.revision: 17
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3c14ae463021fbeed9de24610292fa7516a453fe
ms.lasthandoff: 03/13/2017

---
# <a name="short-c-reference"></a>short (справочник по C#)
Ключевое слово `short` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведены в таблице ниже.  
  
|Тип|Диапазон|Размер|Тип платформы .NET Framework|  
|----------|-----------|----------|-------------------------|  
|`short`|От -32 768 до 32 767|16-разрядное целое число со знаком|<xref:System.Int16?displayProperty=fullName>|  
  
## <a name="literals"></a>Литералы  
 Переменную типа `short` можно объявить и инициализировать, как показано в примере:  
  
```  
  
short x = 32767;  
```  
  
 В приведенном выше объявлении целочисленный литерал `32767` неявным образом преобразуется из типа [int](../../../csharp/language-reference/keywords/int.md) в тип `short`. Если целочисленный литерал не помещается в пространстве для хранения значения типа `short`, то происходит ошибка компиляции.  
  
 При вызове перегруженных методов необходимо использовать приведение типов. Рассмотрим, например, следующие перегруженные методы, в которых используются параметры типов `short` и [int](../../../csharp/language-reference/keywords/int.md):  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(short s) {}  
```  
  
 Использование приведения типа `short` гарантирует вызов метода правильного типа, например:  
  
```  
SampleMethod(5);         // Calling the method with the int parameter  
SampleMethod((short)5);  // Calling the method with the short parameter  
```  
  
## <a name="conversions"></a>Преобразования  
 Существует предопределенное неявное преобразование типа `short` в тип [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Нельзя неявно преобразовать не являющиеся литералами числовые типы большего размера при хранении в тип `short` (сведения о размере целочисленных типов при хранении см. в разделе [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)). Рассмотрим, например, следующие две переменные `x` и `y` типа `short`:  
  
```  
  
short x = 5, y = 12;  
```  
  
 Приведенный ниже оператор присваивания приведет к ошибке компиляции, потому что арифметическое выражение, расположенное справа от оператора присваивания, по умолчанию оценивается как имеющее тип [int](../../../csharp/language-reference/keywords/int.md).  
  
 `short`   `z = x + y;   // Error: no conversion from int to short`  
  
 Для устранения этой проблемы используйте приведение:  
  
 `short`   `z = (`  `short`  `)(x + y);   // OK: explicit conversion`  
  
 Тем не менее можно использовать следующие инструкции, в которых переменная назначения имеет такой же или больший размер при хранении:  
  
```  
int m = x + y;  
long n = x + y;  
```  
  
 Неявного преобразования типов с плавающей запятой в тип `short` не существует. Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:  
  
```  
  
      short x = 3.0;          // Error: no implicit conversion from double  
short y = (short)3.0;   // OK: explicit conversion  
```  
  
 Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).  
  
 Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Int16>   
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
