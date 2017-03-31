---
title: "decimal (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- decimal_CSharpKeyword
- decimal
dev_langs:
- CSharp
helpviewer_keywords:
- decimal keyword [C#]
ms.assetid: b6522132-b5ee-4be3-ad13-3adfdb7de7a1
caps.latest.revision: 32
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
ms.openlocfilehash: f104657c66e067ffe657f8387fef2178e3b2e62b
ms.lasthandoff: 03/13/2017

---
# <a name="decimal-c-reference"></a>decimal (Справочник по C#)
Ключевое слово `decimal` обозначает 128-разрядный тип данных. По сравнению с типами данных с плавающей запятой, диапазон значений типа `decimal` меньше, а точность выше, благодаря чему этот тип подходит для финансовых расчетов. В следующей таблице представлен приблизительный диапазон значений и точность для типа `decimal`.  
  
|Тип|Приблизительный диапазон значений|Точность|Тип платформы .NET Framework|  
|----------|-----------------------|---------------|-------------------------|  
|`decimal`|(От -7,9 x 10<sup>28</sup> до 7,9 x 10<sup>28</sup>) / (10<sup>0–28</sup>)|28–29 значащих цифр|<xref:System.Decimal?displayProperty=fullName>|  
  
## <a name="literals"></a>Литералы  
 Если требуется, чтобы числовой действительный литерал рассматривался как `decimal`, следует использовать суффикс m или M, например:  
  
```  
  
decimal myMoney = 300.5m;  
```  
  
 Если суффикс m отсутствует, число рассматривается как [double](../../../csharp/language-reference/keywords/double.md) и возникает ошибка компилятора.  
  
## <a name="conversions"></a>Преобразования  
 Целочисленные типы неявно преобразуются в тип `decimal` и результатом является тип `decimal`. Поэтому инициализацию десятичной переменной можно выполнить с помощью целочисленного литерала без суффикса следующим образом:  
  
```  
  
decimal myMoney = 300;  
```  
  
 Неявное преобразование между типами с плавающей запятой и типом `decimal` отсутствует, поэтому для преобразования между этими двумя типами следует использовать приведение. Например:  
  
```  
  
      decimal myMoney = 99.9m;  
double x = (double)myMoney;  
myMoney = (decimal)x;  
```  
  
 Тип `decimal` можно использовать в одном выражении вместе с целочисленными типами числовых данных. Однако использование типа `decimal` вместе с типами с плавающей запятой без приведения вызовет ошибку компиляции.  
  
 Дополнительные сведения о неявных числовых преобразованиях см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
 Дополнительные сведения о явных числовых преобразованиях см. в разделе [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).  
  
## <a name="formatting-decimal-output"></a>Форматирование десятичных выходных данных  
 Результаты можно отформатировать с помощью метода `String.Format` или метода <xref:System.Console.Write%2A?displayProperty=fullName>, который вызывает `String.Format()`. Формат денежных единиц задается с помощью стандартной строки формата денежных единиц "C" или "c", как показано во втором примере далее в данной статье. Дополнительные сведения о методе `String.Format` см. в разделе <xref:System.String.Format%2A?displayProperty=fullName>.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере возникает ошибка компилятора при попытке сложить переменные типов [double](../../../csharp/language-reference/keywords/double.md) и `decimal`.  
  
```csharp  
double dub = 9;  
// The following line causes an error that reads "Operator '+' cannot be applied to   
// operands of type 'double' and 'decimal'"  
Console.WriteLine(dec + dub);   
  
// You can fix the error by using explicit casting of either operand.  
Console.WriteLine(dec + (decimal)dub);  
Console.WriteLine((double)dec + dub);  
  
```  
  
 В результате выводится следующее сообщение об ошибке:  
  
 `Operator '+' cannot be applied to operands of type 'double' and 'decimal'`  
  
 В приведенном ниже примере в одном выражении используются переменные типов `decimal` и [int](../../../csharp/language-reference/keywords/int.md). В результате возвращается тип `decimal`.  
  
 [!code-cs[csrefKeywordsTypes#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_1.cs)]  
  
## <a name="example"></a>Пример  
 В следующем примере для форматирования выходных данных используется строка формата денежных единиц. Обратите внимание на округление переменной `x`, поскольку десятичные разряды превышают 0,99 долл. США. Переменная `y`, представляющая максимально точные цифры, отображается в правильном формате.  
  
 [!code-cs[csrefKeywordsTypes#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_2.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Decimal>   
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)   
 [Строки стандартных числовых форматов](http://msdn.microsoft.com/library/580e57eb-ac47-4ffd-bccd-3a1637c2f467)
