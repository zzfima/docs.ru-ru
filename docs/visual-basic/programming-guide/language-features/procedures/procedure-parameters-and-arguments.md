---
title: "Параметры и аргументы процедуры (Visual Basic) | Microsoft Docs"
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
  - "списки аргументов"
  - "аргументы [Visual Basic], передача"
  - "аргументы [Visual Basic], процедуры"
  - "аргументы [Visual Basic], процедуры Visual Basic"
  - "списки параметров"
  - "параметры, списки"
  - "параметры, процедуры Visual Basic"
  - "процедуры, списки аргументов"
  - "процедуры, аргументы"
  - "процедуры, списки параметров"
  - "процедуры, параметры"
  - "значения, передача процедурам"
  - "код Visual Basic, списки аргументов"
  - "код Visual Basic, списки параметров"
  - "код Visual Basic, процедуры"
ms.assetid: ff275aff-aa13-40df-bd4c-63486db8c1e9
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Параметры и аргументы процедуры (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

В большинстве случаев процедуре требуется некоторая информация об обстоятельствах, при которых она была вызвана.  Процедура, которая выполняет повторяющуюся задачу, может использовать разную информацию при разных вызовах.  Такая информация состоит из переменных, констант и выражений, которые передаются процедуре при ее вызове.  
  
 *Параметр* представляет значение, которое необходимо указать процедуре при ее вызове.  В объявлении процедуры определяются ее параметры.  
  
 Можно определить процедуру без параметров, с одним или несколькими параметрами.  Часть определения процедуры, указывающей параметры, называется *списком параметров*.  
  
 *Аргумент* представляет значение, указанное в параметрах процедуры при ее вызове.  Код вызова указывает аргументы при вызове процедуры.  Часть вызова процедуры, которая определяет аргументы, называется *списком аргументов*.  
  
 Ниже показан код вызова процедуры `safeSquareRoot` из двух различных мест.  Первый вызов передает значение переменной `x` \(4.0\) в параметр `number`, а возвращаемое значение в `root` \(2.0\) присваивается переменной `y`.  Второй вызов передает значение литерала 9.0 в `number` и присваивает возвращаемое значение \(3.0\) переменной `z` .  
  
 ![Схема графика передачи аргумента в параметр](../../../../visual-basic/programming-guide/language-features/procedures/media/parametersargue.gif "ParametersArgue")  
Передача аргументов параметру  
  
 Дополнительные сведения см. в разделе [Различия между параметрами и аргументами](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).  
  
## Тип данных параметра  
 Тип данных для параметра определяется с помощью предложения `As` при его объявлении.  Например, приведенная ниже функция принимает строковый и целочисленный аргументы.  
  
 [!code-vb[VbVbcnProcedures#32](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/procedure-parameters-and-arguments_1.vb)]  
  
 Если переключатель проверки типа \([Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)\) установлен в `Off,` предложение `As` необязательно, кроме тех случаев, когда оно используется хотя бы одним параметром: в этом случае его должны использовать все параметры.  Если проверка типа установлена в `On`, `As` предложение является обязательным для всех параметров процедуры.  
  
 Если код вызова ожидает указания аргумента с типом данных, отличающимся от типа данных соответствующего параметра, например параметры `Byte` и `String`, он должен выполнить одно из следующих действий:  
  
-   Указать только аргументы с типами данных, которые расширяются к типу данных параметра;  
  
-   Установить `Option Strict Off`, чтобы разрешить неявные сужающие преобразования;  
  
-   Использовать ключевое слово для явного преобразования типа данных.  
  
### Параметры типа  
 *Универсальная процедура* также определяет один или несколько *параметров типа* в дополнение к его обычным параметрам.  Универсальная процедура позволяет коду вызова передать различные типы данных при каждом вызове процедуры. Таким образом она может приспособить типы данных к требованиям каждого отдельного вызова.  См. раздел [Универсальные процедуры в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Подпрограммы](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Процедуры Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Процедуры свойств](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Процедуры операторов](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Практическое руководство. Определение параметра для процедуры](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-parameter-for-a-procedure.md)   
 [Практическое руководство. Передача аргументов в процедуру](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Передача аргументов по значению и по ссылке](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Перегрузка процедур](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Преобразование типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)