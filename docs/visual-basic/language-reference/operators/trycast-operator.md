---
title: "Оператор TryCast (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.trycast"
  - "trycast"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "TryCast - ключевое слово"
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор TryCast (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Представляет операцию преобразования типов, которая не выдает исключение.  
  
## Заметки  
 Если попытка преобразования завершилась неудачно, то `CType` и `DirectCast` выдадут ошибку <xref:System.InvalidCastException>.  Это может отрицательно повлиять на производительность приложения.  `TryCast` возвращает [Nothing](../../../visual-basic/language-reference/nothing.md), поэтому вместо обработки возможных исключений необходимо только проверить возвращаемый результат на равенство `Nothing`.  
  
 Ключевое слово `TryCast` используется так же, как ключевые слова [Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md) и [Оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md).  В качестве первого аргумента указывается выражение, а в качестве второго — тип, в который надо преобразовать.  `TryCast` работает только со ссылочными типами, такими как классы или интерфейсы.  Она требует отношения наследования или реализации между двумя типами.  Это означает, что один тип должен наследовать или реализовывать другой.  
  
## Ошибки и сбои  
 `TryCast` создает ошибку компилятора, если она обнаруживает, что отношения наследования или реализации не существует.  Однако отсутствие ошибки компилятора не гарантирует успешное преобразование.  Если необходимое преобразование является сужающим, то возможен сбой во время выполнения.  В этом случае `TryCast` вернет [Nothing](../../../visual-basic/language-reference/nothing.md).  
  
## Ключевые слова преобразований  
 Ниже представлено сравнение зарезервированных слов преобразований типа.  
  
|||||  
|-|-|-|-|  
|Ключевое слово|Типы данных|Отношение аргументов|Ошибка во время выполнения|  
|[Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md)|Все типы данных|Между двумя типами данных необходимо определить расширяющее или сужающее преобразование.|Вызывает <xref:System.InvalidCastException>|  
|[Оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md)|Все типы данных|Один тип должен наследовать или реализовывать другой|Вызывает <xref:System.InvalidCastException>|  
|`TryCast`|Только ссылочные типы|Один тип должен наследовать или реализовывать другой|Возвращает [Nothing](../../../visual-basic/language-reference/nothing.md)|  
  
## Пример  
 В следующем примере показано использование `TryCast`.  
  
 [!code-vb[VbVbalrKeywords#6](../../../visual-basic/language-reference/codesnippet/VisualBasic/trycast-operator_1.vb)]  
  
## См. также  
 [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)