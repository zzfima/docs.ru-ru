---
title: "Вопросы, связанные с перегрузкой процедур (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- signatures, ParamArray arguments
- ParamArray keyword, parameter arrays
- ParamArray keyword, arguments and signatures
- function overloading, implicit overloads for ParamArray
- ParamArray keyword, signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures, overloading
- parameters, lists
- function overloading, typeless programming
- typeless programming
- function overloading, restrictions
- arguments [Visual Basic], optional
- optional arguments, overloading
- signatures, procedure
- parameter lists
- parameter arrays, overloading arguments
- Visual Basic code, parameter lists
- procedure overloading, considerations
- Option Explicit statement
- restrictions, overloading procedures
- procedures, parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
caps.latest.revision: 26
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: aa20cf367fba157f88afd861a4799540dcdecde1
ms.lasthandoff: 03/13/2017

---
# <a name="considerations-in-overloading-procedures-visual-basic"></a>Вопросы, связанные с перегрузкой процедур (Visual Basic)
При перегрузке процедур необходимо использовать другой *подписи* для каждой из перегруженных версий. Это обычно означает, что каждая версия необходимо указать другой список параметров. Дополнительные сведения см. в разделе «Другую подпись» в [перегрузка процедур](./procedure-overloading.md).  
  
 Можно перегрузить `Function` процедуры с `Sub` процедура и наоборот, если они имеют разные сигнатуры. Две перегрузки не отличаются только тем, что одна имеет возвращаемое значение, а другой — нет.  
  
 Свойство можно перегрузить перегрузка процедуры, так же, как и с тем же ограничениями. Однако нельзя перегрузить процедуру со свойством или наоборот.  
  
## <a name="alternatives-to-overloaded-versions"></a>Альтернативы перегруженных версий  
 Иногда существуют альтернативы перегруженных версий, особенно если наличие аргументов является необязательным или их количество может меняться.  
  
 Имейте в виду, что необязательные аргументы могут не поддерживаться все языки, а массивы параметров ограничены [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. При создании процедуры, который должен вызываться из кода, написанного на любом из нескольких различных языков, перегруженные версии предоставляют наибольшую гибкость.  
  
### <a name="overloads-and-optional-arguments"></a>Перегрузки и необязательные аргументы  
 Если вызывающий код может при необходимости предоставить или пропустить один или несколько аргументов, можно определить несколько перегруженных версий или использовать дополнительные параметры.  
  
#### <a name="when-to-use-overloaded-versions"></a>Когда следует использовать перегруженные версии  
 Можно определять наборы перегруженных версий в следующих случаях:  
  
-   Логика в коде процедуры существенно отличается в зависимости от того, является ли вызывающий код предоставляет необязательный аргумент или нет.  
  
-   Код процедуры нельзя надежно проверить, является ли вызывающий код имеет указанный необязательный аргумент. Это происходит, например, если нет ни одного кандидата для значение по умолчанию, которое вызывающий код не может предоставить.  
  
#### <a name="when-to-use-optional-parameters"></a>Когда следует использовать дополнительные параметры  
 Может потребоваться один или несколько необязательных параметров в следующих случаях:  
  
-   Присвойте параметру значение по умолчанию является только требуемое действие, когда вызывающий код не предоставляет необязательный аргумент. В таком случае код процедуры можно упростить, если определить одну версию с одним или несколькими `Optional` параметров.  
  
 Дополнительные сведения см. в разделе [необязательные параметры](./optional-parameters.md).  
  
### <a name="overloads-and-paramarrays"></a>Перегрузки и массивы параметров  
 Если вызывающий код может передавать переменное число аргументов, можно определить несколько перегруженных версий или использовать массив параметров.  
  
#### <a name="when-to-use-overloaded-versions"></a>Когда следует использовать перегруженные версии  
 Можно определять наборы перегруженных версий в следующих случаях:  
  
-   Вы знаете, что вызывающий код передает в более чем небольшое количество значений в массиве параметров.  
  
-   Логика в коде процедуры существенно отличается в зависимости от количества значений, которые передает вызывающий код.  
  
-   Вызывающий код может передавать значения различных типов данных.  
  
#### <a name="when-to-use-a-parameter-array"></a>Когда следует использовать массив параметров  
 Вам удобнее работать с `ParamArray` параметр в следующих случаях:  
  
-   Невозможно предсказать количество значений, вызывающий код может передать в массив параметров, и он может быть большим числом.  
  
-   Логика процедуры пригоден для прохода по всем значениям, которые передает вызывающий код выполняет по сути одинаковые операции над каждым значением.  
  
 Дополнительные сведения см. в разделе [массивы параметров](./parameter-arrays.md).  
  
## <a name="implicit-overloads-for-optional-parameters"></a>Неявные перегрузки для дополнительных параметров  
 Процедуры с [необязательно](../../../../visual-basic/language-reference/modifiers/optional.md) эквивалентна двум перегруженным процедурам, с необязательным параметром, а другая — нет. Невозможно перегрузить такую процедуру со списком параметров, соответствующего любой из них. Показано в следующих объявлениях.  
  
 [!code-vb[VbVbcnProcedures&#58;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]  
  
 [!code-vb[VbVbcnProcedures&#60;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures&#61;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]  
  
 Для процедуры с более чем один необязательный параметр существует набор неявных перегрузок, получающихся логикой, подобного приведенному в предыдущем примере.  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a>Неявные перегрузки для параметра ParamArray  
 Компилятор считает, что процедуры с [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) параметра бесконечным числом перегрузок, отличающихся друг от друга, в то, что вызывающий код передает в массив параметров следующим образом:  
  
-   Одна перегрузка, когда вызывающий код не передает аргумент`ParamArray`  
  
-   Одна перегрузка, когда вызывающий код предоставляет одномерный массив `ParamArray` тип элемента  
  
-   Одна перегрузка для каждого положительного целого числа, когда вызывающий код предоставляет количество аргументов, каждый из `ParamArray` тип элемента  
  
 Эти неявные перегрузки показывают следующие объявления.  
  
 [!code-vb[VbVbcnProcedures&#68;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]  
  
 [!code-vb[VbVbcnProcedures&#70;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]  
  
 Нельзя перегрузить процедуру со списком параметров, который принимает одномерный массив для массива параметров. Тем не менее можно использовать подписи неявных перегрузок. Показано в следующих объявлениях.  
  
 [!code-vb[VbVbcnProcedures&#71;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a>Программирование без типов как альтернатива перегрузке  
 Если требуется разрешить вызывающему коду передачу различных типов данных в параметр альтернативный подход — программирование. Можно задать ключ для проверки типа `Off` с помощью [оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) или [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) параметр компилятора. Затем у вас объявить тип данных параметра. Однако такой подход имеет следующие недостатки по сравнению с перегрузкой:  
  
-   Программирование выводятся менее эффективного выполнения кода.  
  
-   Процедура должна проверять каждый тип данных, который может передан.  
  
-   Компилятор не может сообщить об ошибке, если вызывающий код передает тип данных, процедура не поддерживает.  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)   
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)   
 [Рекомендации по устранению неполадок](./troubleshooting-procedures.md)   
 [Практическое руководство: определение различных версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md)   
 [Практическое руководство: вызов перегруженной процедуры](./how-to-call-an-overloaded-procedure.md)   
 [Практическое руководство: перегрузка процедуры, которая принимает необязательные параметры](./how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Практическое руководство: перегрузка процедуры, принимающей неопределенное число параметров](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Разрешение перегрузки](./overload-resolution.md)   
 [Перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md)
