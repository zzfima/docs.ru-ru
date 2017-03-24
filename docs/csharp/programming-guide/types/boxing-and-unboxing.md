---
title: "Упаковка-преобразование и распаковка-преобразование (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cs.boxing"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "язык C#, упаковка"
  - "язык C#, распаковка"
  - "распаковка-преобразование [C#]"
  - "упаковка-преобразование [C#]"
ms.assetid: 8da9bbf4-bce9-4b08-b2e5-f64c11c56514
caps.latest.revision: 34
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 34
---
# Упаковка-преобразование и распаковка-преобразование (Руководство по программированию на C#)
Упаковка представляет собой процесс преобразования [типа значения](../../../csharp/language-reference/keywords/value-types.md) в тип `object` или в любой другой тип интерфейса, реализуемый этим типом значения.  Когда тип значения упаковывается средой CLR, она создает оболочку значения внутри System.Object и сохраняет ее в управляемой куче.  Операция распаковки извлекает тип значения из объекта.  Упаковка является неявной; распаковка является явной.  Понятия упаковки и распаковки лежат в основе единой системы типов C\#, в которой значение любого типа можно рассматривать как объект.  
  
 В следующем примере выполнена операция *упаковки* целочисленной переменой `i`, которая присвоена объекту `o`.  
  
 [!code-cs[csProgGuideTypes#14](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_1.cs)]  
  
 Затем можно выполнить операцию распаковки объекта `o` и присвоить его целочисленной переменной `i`:  
  
 [!code-cs[csProgGuideTypes#15](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_2.cs)]  
  
 Следующий пример иллюстрирует использование упаковки в C\#.  
  
 [!code-cs[csProgGuideTypes#47](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_3.cs)]  
  
## Производительность  
 По сравнению с простыми операциями присваивания операции упаковки и распаковки являются весьма затратными процессами с точки зрения вычислений.  При выполнении упаковки типа значения необходимо создать и разместить новый объект.  Объем вычислений при выполнении операции распаковки, хотя и в меньшей степени, но тоже весьма значителен.  Дополнительные сведения см. в разделе [Производительность](../Topic/.NET%20Performance%20Tips.md).  
  
## Упаковка  
 Упаковка используется для хранения типов значений в куче со сбором мусора.  Упаковка представляет собой неявное преобразование [типа значения](../../../csharp/language-reference/keywords/value-types.md) в тип `object` или в любой другой тип интерфейса, реализуемый этим типом значения.  При упаковке типа значения в куче выделяется экземпляр объекта и выполняется копирование значения в этот новый объект.  
  
 Рассмотрим следующее объявление переменной типа значения.  
  
 [!code-cs[csProgGuideTypes#17](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_4.cs)]  
  
 Следующий оператор неявно применяет операцию упаковки к переменной `i`.  
  
 [!code-cs[csProgGuideTypes#18](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_5.cs)]  
  
 Результат этого оператора создает ссылку на объект `o` в стеке, которая ссылается на значение типа `int` в куче.  Это значение является копией значения типа значения, присвоенного переменной `i`.  Разница между двумя этими переменными, `i` и `o`, продемонстрирована на рисунке ниже.  
  
 ![График BoxingConversion](../../../csharp/programming-guide/types/media/vcboxingconversion.gif "vcBoxingConversion")  
Упаковка\-преобразование  
  
 Можно также выполнять упаковку явным образом, как в следующем примере, однако явная упаковка не является обязательной.  
  
 [!code-cs[csProgGuideTypes#19](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_6.cs)]  
  
## Описание  
 В этом примере целочисленная переменная `i` преобразуется в объект `o` при помощи упаковки.  Затем значение, хранимое переменной `i`, меняется с `123` на `456`.  В примере показано, что исходный тип значения и упакованный объект используют отдельные ячейки памяти, а значит могут хранить разные значения.  
  
## Пример  
 [!code-cs[csProgGuideTypes#16](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_7.cs)]  
  
## Распаковка  
 Распаковка является явным преобразованием из типа `object` в [тип значения](../../../csharp/language-reference/keywords/value-types.md) или из типа интерфейса в тип значения, реализующего этот интерфейс.  Операция распаковки состоит из следующих действий:  
  
-   проверка экземпляра объекта на то, что он является упакованным значением заданного типа значения;  
  
-   копирование значения из экземпляра в переменную типа значения.  
  
 В следующем коде показаны операции по упаковке и распаковке.  
  
 [!code-cs[csProgGuideTypes#21](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_8.cs)]  
  
 На следующем рисунке представлен результат выполнения этого кода.  
  
 ![График преобразования UnBoxing](../../../csharp/programming-guide/types/media/vcunboxingconversion.gif "vcUnBoxingConversion")  
Распаковка\-преобразование  
  
 Для успешной распаковки типов значений во время выполнения необходимо, чтобы экземпляр, который распаковывается, был ссылкой на объект, предварительно созданный с помощью упаковки экземпляра этого типа значения.  Попытка распаковать `null` создает исключение <xref:System.NullReferenceException>.  Попытка распаковать ссылку на несовместимый тип значения создает исключение <xref:System.InvalidCastException>.  
  
## Пример  
 В следующем примере показан случай недопустимой распаковки, в результате чего создается исключение `InvalidCastException`.  В случае использования `try` и `catch` при возникновении ошибки выводится сообщение.  
  
 [!code-cs[csProgGuideTypes#20](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_9.cs)]  
  
 При выполнении этой программы выводится следующий результат:  
  
 `Specified cast is not valid.  Error: Incorrect unboxing.`  
  
 При изменении оператора:  
  
```  
int j = (short) o;  
```  
  
 на:  
  
```  
int j = (int) o;  
```  
  
 будет выполнено преобразование со следующим результатом:  
  
 `Unboxing OK.`  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Связанные разделы  
 Дополнительные сведения:  
  
-   [Ссылочные типы](../../../csharp/language-reference/keywords/reference-types.md)  
  
-   [Типы значений](../../../csharp/language-reference/keywords/value-types.md)  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)