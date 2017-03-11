---
title: "Оператор DirectCast (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.directCast"
  - "directCast"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DirectCast - ключевое слово"
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# Оператор DirectCast (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Представляет тип операции преобразования на основе наследования или реализации.  
  
## Заметки  
 `DirectCast` не использует процедуру поддержки времени выполнения Visual Basic для преобразования, поэтому она обеспечивает отчасти более высокую производительность, чем `CType` при прямом и обратном преобразовании типа данных к `Object`.  
  
 Ключевое слово `DirectCast` используется аналогично ключевым словам [Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md) и [Оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md).  В качестве первого аргумента указывается выражение, а в качестве второго — тип, в который надо преобразовать.  `DirectCast` требует реализации или связи наследования между типами данных двух аргументов.  Это означает, что один тип должен наследовать или реализовывать другой.  
  
## Ошибки и сбои  
 `DirectCast` создает ошибку компилятора, если она обнаруживает, что связи наследования или реализации не существует.  Однако отсутствие ошибки компилятора не гарантирует успешное преобразование.  Если необходимое преобразование является сужающим, то возможен сбой во время выполнения.  В этом случае среда выполнения создает ошибку <xref:System.InvalidCastException>.  
  
## Ключевые слова преобразований  
 Ниже представлено сравнение зарезервированных слов преобразований типа.  
  
|||||  
|-|-|-|-|  
|Ключевое слово|Типы данных|Отношение аргументов|Ошибка во время выполнения|  
|[Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md)|Все типы данных|Между двумя типами данных необходимо определить расширяющее или сужающее преобразование.|Вызывает <xref:System.InvalidCastException>|  
|`DirectCast`|Все типы данных|Один тип должен наследовать или реализовывать другой|Вызывает <xref:System.InvalidCastException>|  
|[Оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md)|Только ссылочные типы|Один тип должен наследовать или реализовывать другой|Возвращает [Nothing](../../../visual-basic/language-reference/nothing.md)|  
  
## Пример  
 Далее показано два примера использования типа `DirectCast`. В первом примере во время его выполнения создается ошибка, а во втором он завершается успешно.  
  
 [!code-vb[VbVbalrKeywords#1](../../../visual-basic/language-reference/codesnippet/visualbasic/directcast-operator_1.vb)]  
  
 В предыдущем примере типом времени выполнения `q` является `Double`.  `CType` выполняется успешно, поскольку `Double` можно преобразовать в `Integer`.  Однако первый `DirectCast` во время выполнения создает ошибку, так как тип времени выполнения `Double` не имеет отношения наследования с `Integer`, даже если существует преобразование.  Второй `DirectCast` завершается успешно, так как он преобразует из типа <xref:System.Windows.Forms.Form> в тип <xref:System.Windows.Forms.Control>, от которого наследуется <xref:System.Windows.Forms.Form>.  
  
## См. также  
 <xref:System.Convert.ChangeType%2A?displayProperty=fullName>   
 [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)