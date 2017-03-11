---
title: "Типы значения, допускающие Null (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Nullable"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "? [Visual Basic]"
  - "типы данных [Visual Basic], допускающие значения NULL"
  - "типы, допускающие значения NULL"
  - "типы, допускающие значения NULL [Visual Basic]"
  - "типы [Visual Basic], допускающие значения NULL"
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# Типы значения, допускающие Null (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Иногда пользователь работает с типом значения, который в определенных обстоятельствах не имеет заданного значения.  Например, поле в базе данных, возможно, должно будет отличать наличие присвоенного значения, имеющего смысл, и отсутствие присвоенного значения.   Типы значений могут быть расширены чтобы принимать обычные значения или значение NULL.  Такое расширение называется *тип Nullable*.  
  
 Каждый тип Nullable создается из общей структуры <xref:System.Nullable%601>.  Рассмотрим базу данных, которая отслеживает связанные с работой действия.  В следующем примере создается тип Nullable `Boolean` и объявляется переменная этого типа.  Можно написать объявление тремя способами:  
  
 [!code-vb[VbVbalrNullableValue#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/visualbasic/nullable-value-types_1.vb)]  
  
 Переменная `ridesBusToWork` может содержать значение `True`, значение `False` или не содержать значения вообще.  Его начальное значение по умолчанию не является значением вообще, и в данном случае это может означать, что данные не были еще получены для этого пользователя.  Напротив, значение `False` может означать, что данные были получены.  
  
 Можно объявлять переменные и свойства с типами Nullable, и можно также объявлять массив элементов типа nullable.  Можно объявить процедуру с типами Nullable в качестве параметров, и можно также возвращать тип nullable из процедуры `Function`.  
  
 Нельзя создать тип Nullable на ссылочном типе, таком как массив, `String` или класс.  Базовый тип должен быть типом значения.  Дополнительные сведения см. в разделе [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
## Использование переменной типа Nullable  
 Наиболее важными членами типа Nullable являются его свойства <xref:System.Nullable%601.HasValue%2A> и <xref:System.Nullable%601.Value%2A>.  При переменной типа nullable, <xref:System.Nullable%601.HasValue%2A> указывает, содержит ли переменная заданное значение.  Если <xref:System.Nullable%601.HasValue%2A> имеет значение `True`, можно прочитать значение из <xref:System.Nullable%601.Value%2A>.  Следует отметить, что и <xref:System.Nullable%601.HasValue%2A>, и <xref:System.Nullable%601.Value%2A> являются свойствами `ReadOnly`.  
  
### Значения по умолчанию  
 При объявлении переменной с типом Nullable, свойство <xref:System.Nullable%601.HasValue%2A> имеет значение `False` по умолчанию.  Это означает, что по умолчанию переменная не имеет заданного значения вместо значения по умолчанию его базового типа значения.  В следующем примере переменная `numberOfChildren` изначально не имеет заданного значения, даже если значение по умолчанию типа `Integer` равно 0.  
  
 [!code-vb[VbVbalrNullableValue#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/visualbasic/nullable-value-types_2.vb)]  
  
 Значение NULL полезно для обнаружения неопределенного или неизвестного значения.  Если бы `numberOfChildren` была объявлена как `Integer`, но тогда не существовало бы значения, которое могло бы указать, что сведения не являются доступными в данный момент.  
  
### Хранимые значения  
 Сохраните значение в переменной или свойстве типа Nullable обычным способом.  В следующем примере присваивается значение переменной `numberOfChildren`, объявленной в предыдущем примере.  
  
 [!code-vb[VbVbalrNullableValue#3](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/visualbasic/nullable-value-types_3.vb)]  
  
 Если переменная или свойство типа Nullable содержит заданное значение, можно принудительно вернуть ее к исходному состоянию отсутствия заданного значения.  Это можно сделать, задав переменную или свойство в `Nothing`, как показано в следующем примере.  
  
 [!code-vb[VbVbalrNullableValue#4](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/visualbasic/nullable-value-types_4.vb)]  
  
> [!NOTE]
>  Хотя можно присвоить значение `Nothing` для переменной nullable типа, но нельзя проверить ее на содержание значения `Nothing` с помощью знака равенства.  Сравнение, использующее знак равенства, `someVar = Nothing`, всегда равно `Nothing`.  Можно проверить свойства переменных <xref:System.Nullable%601.HasValue%2A> на `False`, или проверить с помощью `Is` или оператора `IsNot`.  
  
### Извлечение значений  
 Для извлечения значения переменной nullable типа, следует сначала проверить его свойство <xref:System.Nullable%601.HasValue%2A>, чтобы подтвердить, что оно имеет значение.  При попытке считать значение, когда <xref:System.Nullable%601.HasValue%2A> имеет значение `False`,[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] выдает исключение <xref:System.InvalidOperationException>.  В следующем примере показан рекомендуемый способ чтения переменной `numberOfChildren` из предыдущего примера.  
  
 [!code-vb[VbVbalrNullableValue#5](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/visualbasic/nullable-value-types_5.vb)]  
  
## Сравнение типов Nullable  
 При использовании Nullable переменных `Boolean` в логических выражениях, результатами могут быть значения `True`, `False` или `Nothing`.  Ниже приведена таблица истинности для `And` или `Or`.  Поскольку `b1` и `b2` теперь имеют три возможных значения, получается девять комбинаций для оценки.  
  
|b1|b2|b1 и b2|b1 или b2|  
|--------|--------|-------------|---------------|  
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|  
|`Nothing`|`True`|`Nothing`|`True`|  
|`Nothing`|`False`|`False`|`Nothing`|  
|`True`|`Nothing`|`Nothing`|`True`|  
|`True`|`True`|`True`|`True`|  
|`True`|`False`|`False`|`True`|  
|`False`|`Nothing`|`False`|`Nothing`|  
|`False`|`True`|`False`|`True`|  
|`False`|`False`|`False`|`False`|  
  
 Если значение логической переменной или выражения равно `Nothing`, это ни `true` , ни `false`.  Рассмотрим следующий пример.  
  
 [!code-vb[VbVbalrNullableValue#6](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/visualbasic/nullable-value-types_6.vb)]  
  
 В этом примере `b1 And b2` равно `Nothing`.  В результате условие `Else` выполняется в каждой инструкции `If`, и результаты выполнения выглядят следующим образом:  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
>  `AndAlso` и `OrElse`, которые используют сокращенные вычисления, должны оценивать свои вторые операнды, когда первые операнды имеют значение `Nothing`.  
  
## Передача  
 Если один или оба операнда арифметики, сравнения, сдвига или тип операции относятся к типу nullable, результатом операции также является значение nullable.  Если оба операнда имеют значения, которые не являются `Nothing`, операция выполняется на основных значениях операндов, как если бы ни одно из них не относилось к типу Nullable.  В следующем примере переменные `compare1` и `sum1` заданы неявным образом.  Если навести на них указатель мыши, видно, что компилятор выводит для них обоих типы Nullable.  
  
 [!code-vb[VbVbalrNullableValue#7](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/visualbasic/nullable-value-types_7.vb)]  
  
 Если один или оба операнда имеют значение `Nothing`, результатом будет `Nothing`.  
  
 [!code-vb[VbVbalrNullableValue#8](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/visualbasic/nullable-value-types_8.vb)]  
  
## Использование типов Nullable с данными  
 База данных является одной из наиболее важных сред, где используются типы Nullable.  Не все объекты базы данных в настоящее время поддерживают типы Nullable, но их поддерживают адаптеры таблицы, созданные в конструкторе.  См. раздел "Поддержка адаптером таблицы типов Nullable" в [Общие сведения об адаптере таблиц](/visual-studio/data-tools/tableadapter-overview).  
  
## См. также  
 <xref:System.InvalidOperationException>   
 <xref:System.Nullable%601.HasValue%2A>   
 [Использование допускающих значение NULL типов](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)   
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Общие сведения об адаптере таблиц](/visual-studio/data-tools/tableadapter-overview)   
 [Оператор If](../../../../visual-basic/language-reference/operators/if-operator.md)   
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md)   
 [Оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md)