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
ms.openlocfilehash: bd5b0032ca63ccb2f2cc30d72a5b3f3c7eb3c346
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775738"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a>Вопросы, связанные с перегрузкой процедур (Visual Basic)
При перегрузке процедуры необходимо использовать другую *сигнатуру* для каждой перегруженной версии. Обычно это означает, что каждая версия должна указывать другой список параметров. Дополнительные сведения см. в разделе "другая сигнатура" в [перегрузке процедур](./procedure-overloading.md).  
  
 Можно перегружать `Function` процедуру с помощью `Sub` процедуры, и наоборот, если они имеют разные сигнатуры. Две перегрузки не могут различаться только в том случае, если одна из них имеет возвращаемое значение, а другая — нет.  
  
 Свойство можно перегружать так же, как и при перегрузке процедуры, с теми же ограничениями. Однако нельзя перегружать процедуру со свойством или наоборот.  
  
## <a name="alternatives-to-overloaded-versions"></a>Альтернативы перегруженным версиям  
 Иногда у вас есть альтернативы перегруженным версиям, особенно если присутствие аргументов является необязательным или их число является переменной.  
  
 Помните, что необязательные аргументы не всегда поддерживаются всеми языками, а массивы параметров ограничены Visual Basic. При написании процедуры, которая, скорее всего, будет вызываться из кода, написанного на любом из нескольких разных языков, перегруженные версии обеспечивают максимальную гибкость.  
  
### <a name="overloads-and-optional-arguments"></a>Перегрузки и необязательные аргументы  
 Если вызывающий код может дополнительно указать или опустить один или несколько аргументов, можно определить несколько перегруженных версий или использовать необязательные параметры.  
  
#### <a name="when-to-use-overloaded-versions"></a>Когда следует использовать перегруженные версии  
 Можно определить ряд перегруженных версий в следующих случаях.  
  
- Логика в коде процедуры существенно различается в зависимости от того, предоставляет ли вызывающий код необязательный аргумент.  
  
- Код процедуры не может надежно проверить, предоставил ли вызывающий код необязательный аргумент. Это происходит, например, если нет возможных кандидатов для значения по умолчанию, которое вызывающий код не может ожидать.  
  
#### <a name="when-to-use-optional-parameters"></a>Когда следует использовать необязательные параметры  
 В следующих случаях можно предпочесть один или несколько необязательных параметров:  
  
- Единственное необходимое действие, если вызывающий код не предоставляет необязательный аргумент, — установка для параметра значения по умолчанию. В этом случае код процедуры может быть менее сложным, если определить одну версию с одним или несколькими параметрами `Optional`.  
  
 Дополнительные сведения см. в разделе [необязательные параметры](./optional-parameters.md).  
  
### <a name="overloads-and-paramarrays"></a>Перегрузки и Парамаррайс  
 Когда вызывающий код может передать переменное число аргументов, можно определить несколько перегруженных версий или использовать массив параметров.  
  
#### <a name="when-to-use-overloaded-versions"></a>Когда следует использовать перегруженные версии  
 Можно определить ряд перегруженных версий в следующих случаях.  
  
- Известно, что вызывающий код никогда не передает больше чем небольшое число значений в массив параметров.  
  
- Логика в коде процедуры существенно различается в зависимости от количества значений, пройденных вызывающим кодом.  
  
- Вызывающий код может передавать значения различных типов данных.  
  
#### <a name="when-to-use-a-parameter-array"></a>Когда следует использовать массив параметров  
 Параметр `ParamArray` лучше обслуживать в следующих случаях:  
  
- Невозможно предсказать, сколько значений вызывающего кода можно передать в массив параметров, и это может быть большое число.  
  
- Логика процедуры позволяет выполнять итерацию всех значений, пройденных вызывающим кодом, выполняя фактически те же операции с каждым значением.  
  
 Дополнительные сведения см. в разделе [массивы параметров](./parameter-arrays.md).  
  
## <a name="implicit-overloads-for-optional-parameters"></a>Неявные перегрузки для необязательных параметров  
 Процедура с [необязательным](../../../../visual-basic/language-reference/modifiers/optional.md) параметром эквивалентна двум перегруженным процедурам, одна с необязательным параметром, а другая — без нее. Невозможно перегрузить такую процедуру со списком параметров, соответствующим одному из них. Это показано в следующих объявлениях.  
  
 [!code-vb[VbVbcnProcedures#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#58)]  
  
 [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
 [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
 Для процедуры с более чем одним необязательным параметром существует набор неявных перегрузок, которые прибывают логикой, аналогичной той, которая описана в предыдущем примере.  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a>Неявные перегрузки для параметра ParamArray  
 Компилятор считает, что процедура с параметром [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) имеет бесконечное количество перегрузок, отличающихся друг от друга тем, что вызывающий код передает в массив параметров, следующим образом:  
  
- Одна перегрузка для, когда вызывающий код не предоставляет аргумент в `ParamArray`  
  
- Одна перегрузка для, когда вызывающий код предоставляет одномерный массив `ParamArray`ного типа элемента  
  
- Для каждого положительного целого числа одна перегрузка для, когда вызывающий код предоставляет количество аргументов, каждый тип элемента `ParamArray`  
  
 Следующие объявления иллюстрируют эти Неявные перегрузки.  
  
 [!code-vb[VbVbcnProcedures#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#68)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 Невозможно перегрузить такую процедуру со списком параметров, принимающим одномерный массив для массива параметров. Однако можно использовать сигнатуры других неявных перегрузок. Это показано в следующих объявлениях.  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a>Нетипизированное программирование в качестве альтернативы перегрузке  
 Если вы хотите разрешить вызывающему коду передавать в параметр различные типы данных, альтернативным подходом является программирование без типа. Параметр проверки типа можно установить в `Off` с помощью [оператора Option строго](../../../../visual-basic/language-reference/statements/option-strict-statement.md) или [-оптионстрикт](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) компилятора. После этого не нужно объявлять тип данных параметра. Однако этот подход имеет следующие недостатки по сравнению с перегрузкой:  
  
- Программирование без типов дает менее эффективный код выполнения.  
  
- Процедура должна тестироваться для каждого типа данных, который он ожидает передачи.  
  
- Компилятор не может сообщить об ошибке, если вызывающий код передает тип данных, который не поддерживает процедура.  
  
## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Рекомендации по устранению неполадок](./troubleshooting-procedures.md)
- [Практическое руководство. Определение различных версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md)
- [Практическое руководство. Вызов перегруженной процедуры](./how-to-call-an-overloaded-procedure.md)
- [Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Разрешение перегрузки](./overload-resolution.md)
- [Перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md)
