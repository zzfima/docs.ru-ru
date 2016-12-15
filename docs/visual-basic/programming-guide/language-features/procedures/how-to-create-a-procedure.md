---
title: "Практическое руководство. Создание процедуры (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "объявление процедуры"
  - "процедуры, сведения о процедурах"
  - "процедуры, определение"
  - "код Visual Basic, процедуры"
  - "код Visual Basic, повторное использование"
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Создание процедуры (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Процедура заключается между начальным оператором объявления \(`Sub` или `Function`\) и конечным оператором объявления\(`End Sub` или `End Function`\).  Весь код процедуры содержится между этими операторами.  
  
 Процедура не может содержать другую процедуру, поэтому ее операторы начала и конца должны быть вне любых других процедур.  
  
 Если существует код, выполняющий одну и ту же задачу в разных местах, можно оформить задачу один раз как процедуру и затем вызывать ее из различных мест кода.  
  
### Создание процедуры, не возвращающей значения  
  
1.  Вне любых других процедур используйте оператор `Sub`, за которым следует оператор `End Sub`.  
  
2.  В операторе `Sub` введите ключевое слово `Sub` с именем процедуры, и затем список параметров в круглых скобках.  
  
3.  Поместите операторы кода процедуры между оператором `Sub` и `End Sub`.  
  
### Создание процедуры, возвращающей значение  
  
1.  Вне любых других процедур используйте оператор `Function`, за которым следует оператор `End Function`.  
  
2.  В операторе `Function` после ключевого слова `Function` укажите имя процедуры, затем список параметров в круглых скобках, а затем предложение `As`, задающее тип данных возвращаемого значения.  
  
3.  Поместите операторы кода процедуры между оператором `Function` и `End Function`.  
  
4.  Оператор `Return` используется для возврата значения в вызывающий код.  
  
### Соединение новых процедур со старыми повторяющимися блоками кода  
  
1.  Убедитесь, что новая процедура определена там, где она доступна для старого кода.  
  
2.  В старом блоке повторяющегося кода замените операторы, которые выполняют повторяющуюся задачу, одним оператором, вызывающим процедуры `Sub` или `Function`.  
  
3.  Если процедура является `Function`, которая возвращает значение, убедитесь, что вызывающий оператор выполняет действие с возвращаемым значением, такое как сохранение его в переменной, иначе значение будет потеряно.  
  
## Пример  
 Приведенная ниже процедура `Function` вычисляет длину самой длинной стороны прямоугольного треугольника \(гипотенузы\) по значениям двух других сторон.  
  
 [!code-vb[VbVbcnProcedures#1](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-create-a-procedure_1.vb)]  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Подпрограммы](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Процедуры Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Процедуры свойств](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Процедуры операторов](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Рекурсивные процедуры](../../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)   
 [Перегрузка процедур](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Объектно\-ориентированное программирование](../Topic/Object-Oriented%20Programming%20\(C%23%20and%20Visual%20Basic\).md)