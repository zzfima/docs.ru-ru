---
title: "decimal (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "decimal_CSharpKeyword"
  - "decimal"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "decimal - ключевое слово [C#]"
ms.assetid: b6522132-b5ee-4be3-ad13-3adfdb7de7a1
caps.latest.revision: 32
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 32
---
# decimal (Справочник по C#)
Ключевое слово `decimal` обозначает 128\-разрядный тип данных.  По сравнению с типами данных с плавающей запятой, диапазон значений типа `decimal` меньше, а точность выше, благодаря чему этот тип подходит для финансовых расчетов.  В следующей таблице представлен приблизительный диапазон значений и точность для типа `decimal`.  
  
|Тип|Приблизительный диапазон значений|Точность|Тип платформы .NET Framework|  
|---------|---------------------------------------|--------------|----------------------------------|  
|`decimal`|\(От \-7,9 x 10<sup>28</sup> до 7,9 x 10<sup>28</sup>\) \/ \(10<sup>0–28</sup>\)|28–29 значащих цифр|<xref:System.Decimal?displayProperty=fullName>|  
  
## Литералы  
 Если требуется, чтобы числовой действительный литерал рассматривался как `decimal`, следует использовать суффикс m или M, например:  
  
```  
  
decimal myMoney = 300.5m;  
```  
  
 Если суффикс m отсутствует, число рассматривается как [double](../../../csharp/language-reference/keywords/double.md) и возникает ошибка компилятора.  
  
## Преобразования  
 Целочисленные типы неявно преобразуются в тип `decimal` и результатом является тип `decimal`.  Поэтому инициализацию десятичной переменной можно выполнить с помощью целочисленного литерала без суффикса следующим образом:  
  
```  
  
decimal myMoney = 300;  
```  
  
 Неявное преобразование между типами с плавающей запятой и типом `decimal` отсутствует, поэтому для преобразования между этими двумя типами следует использовать приведение.  Например:  
  
```  
  
        decimal myMoney = 99.9m;  
double x = (double)myMoney;  
myMoney = (decimal)x;  
```  
  
 Тип `decimal` можно использовать в одном выражении вместе с целочисленными типами числовых данных.  Однако использование типа `decimal` вместе с типами с плавающей запятой без приведения вызовет ошибку компиляции.  
  
 Дополнительные сведения о неявных числовых преобразованиях см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
 Дополнительные сведения о явных числовых преобразованиях см. в разделе [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).  
  
## Форматирование десятичных выходных данных  
 Для форматирования результатов можно воспользоваться методом `String.Format` или методом <xref:System.Console.Write%2A?displayProperty=fullName>, вызывающим метод `String.Format()`.  Формат денежных единиц задается с помощью стандартной строки формата денежных единиц "C" или "c", как показано во втором примере далее в данной статье.  Дополнительные сведения о методе `String.Format` см. в разделе <xref:System.String.Format%2A?displayProperty=fullName>.  
  
## Пример  
 В следующем примере возникает ошибка компилятора при попытке сложить переменные типа [double](../../../csharp/language-reference/keywords/double.md) и `decimal`.  
  
```c#  
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
  
 В следующем примере в одном выражении используются переменные типов `decimal` и [int](../../../csharp/language-reference/keywords/int.md).  В результате возвращается тип `decimal`.  
  
 [!code-cs[csrefKeywordsTypes#6](../../../csharp/language-reference/keywords/codesnippet/csharp/decimal_1.cs)]  
  
## Пример  
 В следующем примере для форматирования выходных данных используется строка формата денежных единиц.  Обратите внимание на округление переменной `x`, поскольку десятичные разряды превышают 0,99 долл. США.  Переменная `y`, представляющая максимально точные цифры, отображается в правильном формате.  
  
 [!code-cs[csrefKeywordsTypes#7](../../../csharp/language-reference/keywords/codesnippet/csharp/decimal_2.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 <xref:System.Decimal>   
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)   
 [Строки стандартных числовых форматов](../Topic/Standard%20Numeric%20Format%20Strings.md)