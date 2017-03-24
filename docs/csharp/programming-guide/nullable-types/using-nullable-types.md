---
title: "Использование допускающих значение NULL типов (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "типы, допускающие значения NULL [C#], о типах, допускающих значения NULL"
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
caps.latest.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 31
---
# Использование допускающих значение NULL типов (Руководство по программированию на C#)
Допускающие значение NULL типы могут представлять все значения лежащего в их основе типа, а также значение [NULL](../../../csharp/language-reference/keywords/null.md).  Допускающие значение NULL типы объявляются одним из следующих способов:  
  
 `System.Nullable<T> variable`  
  
 \-или\-  
  
 `T?  variable`  
  
 Свойство `T` является базовым типом для типа, допускающего значение null.  `T` может быть любым типом значения, включая `struct`; он не может быть ссылочным типом.  
  
 Примером случая, когда может использоваться допускающий значение NULL тип, может служить обычная переменная логического типа, которая может иметь два значения: true и false.  Обозначающего "не определено" значения не существует.  Во многих программных приложениях, в первую очередь в операциях с базами данных, переменные могут иметь неопределенное состояние.  Например, поле базы данных может содержать значение true или false, но мажет также вообще не содержать какого\-либо значения.  Аналогично, ссылочные типы могут иметь значение `null`, обозначающее, что они не инициализированы.  
  
 Это несоответствие может создавать дополнительную работу по программированию, приводить к использованию дополнительных переменных для хранения информации о состоянии, применению специальных значений и т.д.  Модификатор типа, преобразующий тип в допускающий значения NULL, позволяет языку C\# создавать переменные типа значения, обозначающие неопределенное значение.  
  
## Примеры допускающих значение NULL типов  
 Любой тип значения может использоваться в качестве основы допускающего значение NULL типа.  Примеры.  
  
 [!code-cs[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]  
  
## Члены допускающих значение NULL типов  
 Каждый экземпляр допускающего значение NULL типа имеет два общих предназначенных только для чтения свойства:  
  
-   `HasValue`  
  
     Свойство `HasValue` имеет тип `bool`.  Это свойство имеет значение `true`, если переменная содержит определенное значение.  
  
-   `Value`  
  
     Свойство `Value` имеет тот же тип, что и у базового типа.  Если свойство `HasValue` имеет значение `true`, то свойство `Value` содержит имеющее смысл значение.  Если свойство `HasValue` имеет значение `false`, то доступ к свойству `Value` будет приводить к формированию ошибки <xref:System.InvalidOperationException>.  
  
 В этом примере член `HasValue` используется для выполнения проверки, содержит ли переменная какое\-либо значение, прежде чем пытаться его показать.  
  
 [!code-cs[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]  
  
 Проверка переменной может быть также выполнена способом, показанным в следующем примере:  
  
 [!code-cs[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]  
  
## Явные преобразования  
 Допускающий значение NULL тип может быть приведен к обычному типу либо явным образом с помощью приведения, либо с помощью свойства `Value`.  Примеры.  
  
 [!code-cs[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]  
  
 Если определенное пользователем преобразование определено между двумя типами данных, то это же преобразование может быть также использовано с допускающими значение NULL версиями этих типов данных.  
  
## Неявные преобразования  
 Переменной допускающего значение NULL типа может быть присвоено значение NULL с помощью ключевого слова `null`, как показано в следующем примере:  
  
 [!code-cs[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]  
  
 Преобразование из обычного типа в допускающий значение NULL тип является неявным.  
  
 [!code-cs[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]  
  
## Операторы  
 Существующие для типов значений предварительно определенные унарные и бинарные операторы, а также определенные пользователем операторы могут также использоваться допускающими значение NULL типами.  Эти операторы создают значение NULL, если операнды имеют значение NULL; иначе оператор использует для вычисления результата содержащееся значение.  Примеры.  
  
 [!code-cs[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]  
  
 Если при выполнении сравнения с допускающими значение NULL типами значение одного из таких типов равно NULL, а второй тип содержит другое значение, то результатом сравнения всегда является `false`, за исключением использования оператора `!=` \(не равно\).  Очень важно не предполагать, что если одна операция сравнения возвращает значение `false`, то обратная операция возвратит значение `true`.  В следующем примере число 10 не больше и не меньше значения NULL, а также не равно ему.  Значение `true` возвращается только в случае использования оператора `num1 != num2`.  
  
 [!code-cs[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]  
  
 Сравнение на равенство двух допускающих значение NULL типов, оба из которых содержат NULL, возвратит значение `true`.  
  
## ??Оператор  
 Оператор `??` определяет значение по умолчанию, возвращаемое при присвоении допускающего значение NULL типа не допускающему значение NULL типу.  
  
 [!code-cs[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]  
  
 Этот оператор может также использоваться с несколькими допускающими значение NULL типами.  Примеры.  
  
 [!code-cs[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]  
  
## Типtype  
 Допускающий значение NULL тип `bool?` может содержать три значения: [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) и [null](../../../csharp/language-reference/keywords/null.md).  Сведения о том, как выполняется приведение из bool?  в bool, см. в разделе [Практическое руководство. Безопасное приведение bool? к bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).  
  
 Допускающие значение NULL логические типы аналогичны логическим типам переменных, используемым в языке SQL.  Чтобы гарантировать, что результаты `&` и  `|` операторы согласованы с имеющим три значения логическим типом в SQL, предусмотрены следующие предварительно определенные операторы:  
  
 `bool?  operator &(bool?  x, bool?  y)`  
  
 `bool?  operator |(bool?  x, bool?  y)`  
  
 Результаты выполнения этих операторов приведены в следующей таблице:  
  
|X|y|x&y|x&#124;y|  
|-------|-------|---------|--------------|  
|true|true|true|true|  
|true|false|false|true|  
|true|null|null|true|  
|false|true|false|true|  
|false|false|false|false|  
|false|null|false|null|  
|null|true|null|true|  
|null|false|false|null|  
|null|null|null|null|  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md)   
 [Упаковка\-преобразование типов, допускающих значение NULL](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)   
 [Типы значения, допускающие Null](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)