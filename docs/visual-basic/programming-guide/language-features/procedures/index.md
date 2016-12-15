---
title: "Процедуры в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "процедуры"
  - "процедуры, структурированный код"
  - "процедуры, типы"
  - "структурированный код, процедуры"
  - "код Visual Basic, процедуры"
ms.assetid: 9effbcf0-80a0-4d1a-98f4-2c6920592766
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Процедуры в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

*Процедура* является блоком операторов [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], объединенных оператором объявления \(`Function` `Sub` `Operator`, `Get`, `Set`\) и соответствующего объявления `End`.  Все выполняемые инструкции в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] должны находиться в пределах некоторой процедуры.  
  
## Вызов процедуры  
 Процедура вызывается из какой\-либо другой части кода.  Подобная операция известна как *вызов процедуры*.  После завершения процедуры она возвращает управление коду, вызвавшему ее, который называется *вызывающий код*.  Вызывающий код — это инструкция или выражение в составе инструкции, которое определяет процедуру по имени и передает ей управление.  
  
## Возвращение из процедуры  
 Процедура возвращает управление вызывающему коду после завершения работы.  Чтобы сделать это, она использует оператор [Оператор Return](../../../../visual-basic/language-reference/statements/return-statement.md), соответствующий инструкции [Оператор Exit](../../../../visual-basic/language-reference/statements/exit-statement.md) для процедуры, или оператор [Оператор End \<ключевое\_слово\>](../../../../visual-basic/language-reference/statements/end-keyword-statement.md) процедуры.  Управление затем передается вызывающему коду, следуя за точкой вызова процедуры.  
  
-   Управление немедленно возвращается вызывающему коду оператором `Return`.  Инструкции, следующие за инструкцией `Return`, не работают.  В одной и той же процедуре допускается несколько инструкций `Return`.  
  
-   Управление немедленно возвращается вызывающему коду оператором `Exit Sub` или `Exit Function`.  Инструкции, следующие за инструкцией `Exit`, не работают.  В одной и той же процедуре можно использовать несколько инструкций `Exit`, кроме того, инструкции `Return` и `Exit` можно сочетать.  
  
-   Если процедура не имеет операторов `Return` `Exit`, она завершается оператором `End Sub` `End Function`, `End Get` или `End Set`, следующим за последним оператором тела процедуры.  Оператор `End` немедленно возвращает управление вызывающему коду.  В процедуре допускается только один оператор `End`.  
  
## Параметры и аргументы  
 В большинстве случаев процедуре необходимо работать с различными данными при каждом ее вызове.  Можно передать эти сведения в процедуру как часть вызова процедуры.  Процедура определяет ноль или более *параметров*, каждый из которых представляет значение, ожидаемое ею для приема.  Каждому параметру в определении процедуры соответствует *аргумент* в вызове процедуры.  Аргумент представляет значение, которое передается соответствующему параметру в вызове данной процедуры.  
  
## Типы процедур  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] использует несколько типов процедур:  
  
-   [Подпрограммы](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) выполняют действия, но не возвращают значение в вызывающий код.  
  
-   Процедурами обработки событий являются процедуры `Sub`, которые выполняются в ответ на событие, вызванное действием пользователя или определенными условиями в программе.  
  
-   [Процедуры Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) возвращает значение в вызывающий код.  Они могут выполнять другие действия перед возвратом.  
  
-   [Процедуры свойств](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md) возвращают и задают значения свойств объектам или модулям.  
  
-   [Процедуры операторов](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md) определяет поведение стандартного оператора, если один или оба операнда являются недавно определенным классом или структурой.  
  
-   [Универсальные процедуры в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md) определяет один или несколько *параметров типа* в дополнение к их обычным параметрам, поэтому код вызова может передавать определенные типы данных каждый раз, когда он совершает вызов.  
  
## Процедуры и структурированный код  
 Каждая строка исполняемого кода в приложении должна находиться внутри некоторых процедур, таких как `Main` `calculate` и `Button1_Click`.  Если разделить большие процедуры на несколько менее крупных, приложение будет удобнее читать.  
  
 Процедуры применяются для выполнения повторяющихся задач или задач, которые нужно выполнять в разных компонентах кода, например, для часто используемых расчетных операций, действий с текстом и элементами управления, а также операций с базами данных.  Процедуры можно вызывать из разных частей кода, поэтому их можно использовать в качестве элементарных структурных блоков при создании приложения.  
  
 Структурирование кода с помощью процедур предоставляет следующие возможности.  
  
-   Процедуры позволяют разбить программу на отдельные логические блоки.  Отлаживать такие отдельные блоки легче, чем всю программу целиком.  
  
-   Процедуры, разработанные для одной программы, можно в том же виде \(или после внесения незначительных изменений\) использовать в другой программе.  Это помогает избежать дублирования кода.  
  
## См. также  
 [Практическое руководство. Создание процедуры](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure.md)   
 [Подпрограммы](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Процедуры Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Процедуры свойств](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Процедуры операторов](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Рекурсивные процедуры](../../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)   
 [Перегрузка процедур](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Универсальные процедуры в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)   
 [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)