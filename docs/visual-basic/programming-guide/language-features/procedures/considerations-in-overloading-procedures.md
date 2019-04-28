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
ms.openlocfilehash: f14cc28960af28530bda9a78c1309dea10c18b8f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864355"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a>Вопросы, связанные с перегрузкой процедур (Visual Basic)
При перегрузке процедур необходимо использовать другой *подпись* для каждой из перегруженных версий. Обычно это означает, что каждая версия необходимо указать другим списком параметров. Дополнительные сведения см. в разделе «Разных подпись» в [перегрузка процедур](./procedure-overloading.md).  
  
 Можно перегрузить `Function` процедуру с `Sub` процедуры и наоборот, если они имеют разные сигнатуры. Две перегрузки не отличаются только тем, что одна имеет возвращаемое значение, а другой — нет.  
  
 Свойство может быть перегружено перегрузка процедуры, так же, как и с теми же ограничениями. Тем не менее, не могут перегружать процедуру со свойством (или наоборот).  
  
## <a name="alternatives-to-overloaded-versions"></a>Альтернативы перегруженных версий  
 Иногда можно использовать различные альтернативы перегруженных версий, особенно в том случае, если наличие аргументов является необязательным или их количество может меняться.  
  
 Имейте в виду, что необязательные аргументы могут не поддерживаться все языки, а массивы параметров ограничены Visual Basic. При создании процедуры, которая, вероятнее всего, для вызова из кода, написанный на любом из нескольких различных языков, перегруженные версии предоставляют наибольшую гибкость.  
  
### <a name="overloads-and-optional-arguments"></a>Перегрузки и необязательные аргументы  
 Когда вызывающий код при необходимости можно указать или пропустить один или несколько аргументов, можно определить несколько перегруженных версий или использовать дополнительные параметры.  
  
#### <a name="when-to-use-overloaded-versions"></a>Когда следует использовать перегруженные версии  
 Можно определить ряд перегруженных версий в следующих случаях:  
  
- Логика в коде процедуры существенно отличается в зависимости от того, является ли вызывающий код предоставляет необязательный аргумент, или нет.  
  
- Код процедуры нельзя надежно проверить ли вызывающий код указанный необязательный аргумент. Это происходит, например, если нет ни одного кандидата для значение по умолчанию, которое вызывающий код не может предоставить.  
  
#### <a name="when-to-use-optional-parameters"></a>Когда следует использовать необязательные параметры  
 Может потребоваться один или несколько необязательных параметров в следующих случаях:  
  
- Только необходимое действие, когда вызывающий код не предоставляет необязательный аргумент является параметру присвоить значение по умолчанию. В таком случае код процедуры можно упростить, если определить одну версию с одним или несколькими `Optional` параметров.  
  
 Дополнительные сведения см. в разделе [необязательные параметры](./optional-parameters.md).  
  
### <a name="overloads-and-paramarrays"></a>Перегрузки и массивы параметров  
 Когда вызывающий код может передать переменное число аргументов, можно определить несколько перегруженных версий или использовать массив параметров.  
  
#### <a name="when-to-use-overloaded-versions"></a>Когда следует использовать перегруженные версии  
 Можно определить ряд перегруженных версий в следующих случаях:  
  
- Вы знаете, что вызывающий код никогда не передается больше, чем небольшое количество значений в массиве параметров.  
  
- Логика в коде процедуры существенно отличается в зависимости от того, сколько значений, которые передает вызывающий код.  
  
- Вызывающий код может передавать значения различных типов данных.  
  
#### <a name="when-to-use-a-parameter-array"></a>Когда следует использовать параметр-массив  
 Вы должны обрабатываться `ParamArray` параметр в следующих случаях:  
  
- Вы не сможете спрогнозировать количество значений, вызывающий код может передать массив параметров, и это может быть много.  
  
- Логика процедуры пригоден для итерации по всем значениям, передает вызывающий код, выполнение по сути те же операции над каждым значением.  
  
 Дополнительные сведения см. в разделе [массивы параметров](./parameter-arrays.md).  
  
## <a name="implicit-overloads-for-optional-parameters"></a>Неявные перегрузки для дополнительных параметров  
 Процедуры с [необязательно](../../../../visual-basic/language-reference/modifiers/optional.md) параметром эквивалентен двум перегруженным процедурам, один с необязательным параметром, а другая — нет. Невозможно перегрузить такую процедуру со списком параметров, соответствующий любому из этих вариантов. Следующие объявления, иллюстрируют это.  
  
 [!code-vb[VbVbcnProcedures#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#58)]  
  
 [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
 [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
 Для процедуры с более чем один необязательный параметр имеется набор неявные перегрузки, поступивших на логикой, аналогично приведенному в предыдущем примере.  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a>Неявные перегрузки параметру ParamArray.  
 Компилятор считает, что процедура с [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) параметру, чтобы бесконечное число перегрузок, отличающихся друг от друга в именно вызывающий код передает массив параметров, как показано ниже:  
  
- Одна перегрузка, когда вызывающий код не передает аргумент `ParamArray`  
  
- Одна перегрузка, когда вызывающий код предоставляет одномерный массив `ParamArray` тип элемента  
  
- Одна перегрузка для каждого положительного целого числа, когда вызывающий код предоставляет количество аргументов, каждый из `ParamArray` тип элемента  
  
 Эти неявные перегрузки показывают следующие объявления.  
  
 [!code-vb[VbVbcnProcedures#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#68)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 Не могут перегружать процедуру со списком параметров, который принимает одномерный массив для массива параметров. Тем не менее можно использовать подписи других неявных перегрузок. Следующие объявления, иллюстрируют это.  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a>Программирование в качестве альтернативы с перегрузкой  
 Если вы хотите разрешить вызывающий код для передачи различных типов данных в параметр, альтернативный подход — программирование. Можно задать ключ для проверки типа `Off` сочетанием [оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) или [Дополнительные сведения](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) параметр компилятора. Затем у вас нет объявления типа данных параметра. Однако такой подход имеет следующие недостатки по сравнению с перегрузкой:  
  
- Программирование создает менее эффективного выполнения кода.  
  
- Процедура должна проверять каждый тип данных, который может передан.  
  
- Компилятор не может сообщить об ошибке, если вызывающий код передает тип данных, процедура не поддерживает.  
  
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
