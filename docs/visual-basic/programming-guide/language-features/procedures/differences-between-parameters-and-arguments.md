---
title: "Различия между параметрами и аргументами (Visual Basic) | Microsoft Docs"
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
  - "аргументы [Visual Basic], и параметры"
  - "параметры, и аргументы"
  - "параметры, определение"
  - "аргументы процедур"
  - "параметры процедуры"
  - "процедуры, аргументы"
  - "процедуры, параметры"
  - "код Visual Basic, процедуры"
ms.assetid: c237c056-74f4-4749-9f2c-15864f139a31
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Различия между параметрами и аргументами (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

В большинстве случаев процедуре требуется некоторая информация об обстоятельствах, при которых она была вызвана.  Процедура, которая выполняет повторяющуюся задачу, может использовать разную информацию при разных вызовах.  Такая информация состоит из переменных, констант и выражений, которые передаются процедуре при ее вызове.  
  
 Для передачи в процедуру этих сведений она определяет *параметр*, а вызывающий код передает *аргумент* в этот параметр.  Можно представить параметр как парковочное место и аргумент как автомобиль.  Точно так же, как различные автомобили могут парковаться на парковочном месте в разное время, при каждом вызове процедуры вызывающий код может передать другой аргумент для одного параметра.  
  
## Параметры  
 *Параметр* представляет значение, которое необходимо указать процедуре при ее вызове.  В объявлении процедуры определяются ее параметры.  
  
 При определении `Function` или `Sub` процедуры, необходимо указать *список параметров* в скобках сразу после имени процедуры.  Для каждого параметра необходимо указать имя, тип данных и механизм передачи \([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)\).  Можно также указать, что параметр является опциональным.  Это означает, что вызывающий код не обязан передавать значение для него.  
  
 Имя каждого параметра служит в качестве *локальной переменной* в процедуре.  Имя параметра используется так же, как любая другая переменная.  
  
## Аргументы  
 *Аргумент* представляет значение, указанное в параметрах процедуры при ее вызове.  Код вызова указывает аргументы при вызове процедуры.  
  
 При вызове `Function` или `Sub` процедуры *список аргументов* включается в скобках сразу после имени процедуры.  Каждый аргумент соответствует параметру в той же позиции в списке.  
  
 В отличие от определения параметра аргументы не имеют имен.  Каждый аргумент является выражением, которое может содержать ноль или более переменных, констант и литералов.  Тип данных вычисления выражения должен соответствовать типу данных, определенному для соответствующего параметра или в любом случае должен быть преобразуемым к типу параметра.  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Подпрограммы](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Процедуры Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Процедуры свойств](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Процедуры операторов](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Практическое руководство. Определение параметра для процедуры](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-parameter-for-a-procedure.md)   
 [Практическое руководство. Передача аргументов в процедуру](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Передача аргументов по значению и по ссылке](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Рекурсивные процедуры](../../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)   
 [Перегрузка процедур](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)