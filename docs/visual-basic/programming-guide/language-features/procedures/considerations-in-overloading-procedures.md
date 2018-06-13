---
title: Вопросы, связанные с перегрузкой процедур (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- signatures [Visual Basic], ParamArray arguments
- ParamArray keyword [Visual Basic], parameter arrays
- ParamArray keyword [Visual Basic], arguments and signatures
- function overloading [Visual Basic], implicit overloads for ParamArray
- ParamArray keyword [Visual Basic], signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], overloading
- parameters [Visual Basic], lists
- function overloading [Visual Basic], typeless programming
- typeless programming
- function overloading [Visual Basic], restrictions
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], overloading
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- parameter arrays [Visual Basic], overloading arguments
- Visual Basic code, parameter lists
- procedure overloading [Visual Basic], considerations
- Option Explicit statement [Visual Basic]
- restrictions [Visual Basic], overloading procedures
- procedures [Visual Basic], parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
ms.openlocfilehash: e1768d0ac03cb6730c4337d7476ae163e75adfd3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654334"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a>Вопросы, связанные с перегрузкой процедур (Visual Basic)
При перегрузке процедур необходимо использовать другой *подписи* для каждой из перегруженных версий. Обычно это означает, что каждой версии необходимо указать другим списком параметров. Дополнительные сведения см. в разделе «Сигнатура» в [перегрузка процедур](./procedure-overloading.md).  
  
 Можно перегрузить `Function` процедуру с `Sub` процедура и наоборот, если они имеют разные сигнатуры. Две перегрузки не отличаются только тем, что одна имеет возвращаемое значение, а другой — нет.  
  
 Свойство можно перегрузить перегрузка процедуры, так же, как и с тем же ограничениям. Однако нельзя перегрузить процедуру со свойством, или наоборот.  
  
## <a name="alternatives-to-overloaded-versions"></a>Альтернативы перегруженных версий  
 Иногда имеют альтернативы перегруженных версий, особенно в том случае, если наличие аргументов является необязательным или их количество может меняться.  
  
 Имейте в виду, что необязательные аргументы могут не поддерживаться все языки, а массивы параметров ограничены Visual Basic. При создании процедуры, который должен вызываться из кода, написанного на любом из нескольких различных языков, перегруженные версии предоставляют наибольшую гибкость.  
  
### <a name="overloads-and-optional-arguments"></a>Перегрузки и необязательные аргументы  
 Если вызывающий код при необходимости можно указать или пропустить один или несколько аргументов, можно определить несколько перегруженных версий или использовать дополнительные параметры.  
  
#### <a name="when-to-use-overloaded-versions"></a>Когда следует использовать перегруженные версии  
 Можно определить набор перегруженных версий в следующих случаях:  
  
-   Логика в коде процедуры существенно отличается в зависимости от того, является ли вызывающий код предоставляет необязательный аргумент или нет.  
  
-   Код процедуры нельзя надежно проверить, является ли вызывающий код указанный необязательный аргумент. Это так, например, если нет ни одного кандидата для значение по умолчанию, которое вызывающий код не может предоставить.  
  
#### <a name="when-to-use-optional-parameters"></a>Когда следует использовать необязательные параметры  
 Можно использовать один или несколько необязательных параметрах в следующих случаях:  
  
-   Установите для параметра значение по умолчанию является только требуемые действия, когда вызывающий код не предоставляет необязательный аргумент. В этом случае код процедуры может быть проще, если определить одну версию с одним или несколькими `Optional` параметров.  
  
 Дополнительные сведения см. в разделе [необязательные параметры](./optional-parameters.md).  
  
### <a name="overloads-and-paramarrays"></a>Перегрузки и массивы параметров  
 Если вызывающий код может передавать переменное число аргументов, можно определить несколько перегруженных версий или использовать массив параметров.  
  
#### <a name="when-to-use-overloaded-versions"></a>Когда следует использовать перегруженные версии  
 Можно определить набор перегруженных версий в следующих случаях:  
  
-   Вы знаете, что вызывающий код никогда не передается больше чем небольшое количество значений в массиве параметров.  
  
-   Логика в коде процедуры существенно отличается в зависимости от того, сколько значений, которые передает вызывающий код.  
  
-   Вызывающий код может передавать значения различных типов данных.  
  
#### <a name="when-to-use-a-parameter-array"></a>Когда следует использовать массив параметров  
 Вам удобнее работать с `ParamArray` параметр в следующих случаях:  
  
-   Невозможно спрогнозировать количество значений, вызывающий код может передать массив параметров, и это может быть большое число.  
  
-   Логика процедуры пригоден для прохода по всем значениям, вызывающий код передает выполнение по сути одинаковые операции над каждым значением.  
  
 Дополнительные сведения см. в разделе [массивы параметров](./parameter-arrays.md).  
  
## <a name="implicit-overloads-for-optional-parameters"></a>Неявные перегрузки для дополнительных параметров  
 Процедуры с [необязательно](../../../../visual-basic/language-reference/modifiers/optional.md) параметр эквивалентен двум перегруженным процедурам, с необязательным параметром, а другая — нет. Невозможно перегрузить такую процедуру со списком параметров, соответствующим любому из них. Это показано в следующих объявлениях.  
  
 [!code-vb[VbVbcnProcedures#58](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]  
  
 Для процедуры с более чем один необязательный параметр имеется набор неявных перегрузок, получающихся по той же схеме, в приведенном выше примере.  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a>Неявные перегрузки параметру ParamArray.  
 Компилятор считает, что процедура с [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) параметру принимать бесконечное число перегрузок, отличающихся друг от друга в том, что вызывающий код передает массив параметров, следующим образом:  
  
-   Одна перегрузка, когда вызывающий код не передает аргумент `ParamArray`  
  
-   Одна перегрузка, когда вызывающий код предоставляет одномерный массив `ParamArray` тип элемента  
  
-   Одна перегрузка для каждого положительного целого числа, когда вызывающий код предоставляет количество аргументов, каждый из `ParamArray` тип элемента  
  
 Эти неявные перегрузки показывают следующие объявления.  
  
 [!code-vb[VbVbcnProcedures#68](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]  
  
 Нельзя перегрузить процедуру со списком параметров, который принимает одномерный массив для массива параметров. Тем не менее можно использовать подписи неявных перегрузок. Это показано в следующих объявлениях.  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a>Программирование без типов как альтернатива перегрузке  
 Если вы хотите разрешить вызывающему коду для передачи различных типов данных в параметр, альтернативный подход — программирование. Можно задать ключ для проверки типа `Off` либо [оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) или [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) параметр компилятора. Затем объявите тип данных параметра нет. Однако такой подход имеет следующие недостатки по сравнению с перегрузкой:  
  
-   Программирование выводятся менее эффективный код выполнения.  
  
-   Процедура должна проверять каждый тип данных, которые можно предвидеть передан.  
  
-   Компилятор не может сообщить об ошибке, если вызывающий код передает тип данных, процедура не поддерживает.  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Рекомендации по устранению неполадок](./troubleshooting-procedures.md)  
 [Практическое руководство. Определение различных версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md)  
 [Практическое руководство. Вызов перегруженной процедуры](./how-to-call-an-overloaded-procedure.md)  
 [Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [Разрешение перегрузки](./overload-resolution.md)  
 [Перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md)
