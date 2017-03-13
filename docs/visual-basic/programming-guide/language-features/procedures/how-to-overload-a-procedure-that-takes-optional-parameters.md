---
title: "Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "перегрузка процедур, необязательные параметры"
  - "параметры процедуры"
  - "процедуры, определение"
  - "процедуры, несколько версий"
  - "процедуры, перегрузка"
  - "процедуры, параметры"
  - "код Visual Basic, процедуры"
ms.assetid: 825f9d56-4cde-43fd-993a-b9171717e2eb
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Если процедура имеет один или несколько параметров [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), нельзя определить перегруженную версию, соответствующую любой из ее неявных перегрузок.  Дополнительные сведения содержатся в разделе "Неявные перегрузки для опциональных параметров" в [Вопросы, связанные с перегрузкой процедур](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md).  
  
## Один необязательный параметр  
  
#### Чтобы перегрузить процедуру, которая принимает один опциональный параметр  
  
1.  Напишите объявление инструкции `Sub` или `Function`, которая содержит опциональный параметр в списке параметров.  Не используйте ключевое слово `Optional` в данной перегруженной версии.  
  
2.  Переместите ключевое слово `Sub` или `Function` так, чтобы оно предшествовало ключевому слову [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md).  
  
3.  Напишите код процедуры, который должен выполняться, когда код вызова предоставляет опциональный аргумент.  
  
4.  Завершите процедуру подходящим оператором `End Sub` либо `End Function`.  
  
5.  Запишите вторую инструкцию объявления, идентичную первому объявлению, за исключением того, что она не включает опциональный параметр в списке параметров.  
  
6.  Напишите код процедуры, который должен выполняться, когда код вызова не предоставляет необязательный аргумент.  Завершите процедуру подходящим оператором `End Sub` либо `End Function`.  
  
     В следующем примере процедура определена с необязательным параметром, эквивалент набору из двух перегруженных процедур и в конце примеры допустимых и недопустимых перегруженных версий процедуры.  
  
     [!code-vb[VbVbcnProcedures#59](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_2.vb)]  
  
     [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_3.vb)]  
  
## Несколько опциональных параметров  
 Обычно необходимо более двух перегруженных версий процедуры, если она имеет более одного опционального параметра.  Например, если существуют два опциональных параметра и код вызова может использовать или опустить каждый из них независимо друг от друга, необходимо четыре перегруженных версии, по одной для каждой возможной комбинации предоставленных аргументов.  
  
 Такой подход становится более сложным с увеличением числа необязательных параметров.  Кроме неприемлемых комбинаций переданных аргументов, для N необязательных параметров необходимо 2 ^ N перегруженных версий.  Из характера процедуры ясно, что требуются лишние усилия для определения всех перегруженных версий.  
  
#### Чтобы перегрузить процедуру, которая принимает больше одного необязательного параметра  
  
1.  Определите какие комбинации предоставленных опциональных аргументов допустимы для логики процедуры.  Недопустимое сочетание может возникнуть, если один дополнительный параметр зависит от другого.  Например, если один параметр принимает имя супруга, а другой принимает возраст супруга, учитывать аргументы возраста, но опустить имя является недопустимым.  
  
2.  Для каждой допустимой комбинации предоставленных опциональных аргументов напишите инструкции объявления `Sub` или `Function`, определяющие соответствующий список параметров.  Не используйте ключевое слово `Optional`.  
  
3.  В каждом объявлении ключевому слову `Sub` или `Function` должно предшествовать ключевое слово [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md).  
  
4.  После каждого объявления напишите код процедуры, который должен выполняться, когда вызывающий код предоставит список аргументов, соответствующий элементам списка параметров в объявлении.  
  
5.  Завершите выполнение каждой процедуры оператором `End Sub` или `End Function` .  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Необязательные параметры](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Массивы параметров](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Перегрузка процедур](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Устранение неполадок в процедурах](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [Практическое руководство. Определение различных версий процедуры](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-multiple-versions-of-a-procedure.md)   
 [Практическое руководство. Вызов перегруженной процедуры](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-overloaded-procedure.md)   
 [Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Разрешение перегрузки](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)