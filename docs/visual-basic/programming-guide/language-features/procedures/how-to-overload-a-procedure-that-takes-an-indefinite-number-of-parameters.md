---
title: Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], indefinite number of parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
ms.openlocfilehash: 047d566c13f03803d2e5c3bc6cce0db56df4a3f0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345846"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a>Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров (Visual Basic)
Если процедура имеет параметр [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) , нельзя определить перегруженную версию, принимающую одномерный массив для массива параметров. Дополнительные сведения см. в разделе "Неявные перегрузки для параметра ParamArray" раздела [рекомендации по перегрузке процедур](./considerations-in-overloading-procedures.md).  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a>Перегрузка процедуры, принимающей переменное число параметров  
  
1. Выясните, что процедура и вызов логики кода имеют преимущества от перегруженных версий больше, чем из параметра `ParamArray`. См. раздел "Overloads and Парамаррайс" в разделе [рекомендации по перегрузке процедур](./considerations-in-overloading-procedures.md).  
  
2. Определите, какое количество представленных значений должна принимать процедура в переменной части списка параметров. Это может включать отсутствие значения и может включать в себя регистр одного одномерного массива.  
  
3. Для каждого допустимого числа представленных значений напишите `Sub` или `Function` оператор объявления, определяющий соответствующий список параметров. Не используйте в этой перегруженной версии ключевое слово `Optional` или `ParamArray`.  
  
4. В каждом объявлении перед ключевым словом `Sub` или `Function` с ключевым словом [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) .  
  
5. После каждого объявления напишите код процедуры, который должен выполняться, когда вызывающий код предоставляет значения, соответствующие списку параметров этого объявления.  
  
6. При необходимости Завершите каждую процедуру с помощью оператора `End Sub` или `End Function`.  
  
## <a name="example"></a>Пример  
 В следующем примере показана процедура, определенная с параметром [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) , а затем эквивалентный набор перегруженных процедур.  
  
 [!code-vb[VbVbcnProcedures#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#69)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 Невозможно перегрузить такую процедуру со списком параметров, принимающим одномерный массив для массива параметров. Однако можно использовать сигнатуры других неявных перегрузок. Это показано в следующих объявлениях.  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
 Код в перегруженных версиях не должен проверять, предоставлен ли вызывающему коду одно или несколько значений для параметра `ParamArray` или, если да, сколько. Visual Basic передает управление версии, соответствующей списку аргументов вызова.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Так как процедура с параметром `ParamArray` эквивалентна набору перегруженных версий, нельзя перегружать такую процедуру со списком параметров, соответствующим любому из этих неявных перегрузок. Дополнительные сведения см. [в разделе рекомендации по перегрузке процедур](./considerations-in-overloading-procedures.md).  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Всякий раз при работе с массивом, который может быть неограниченным большим, существует риск перегрузки внутренней емкости приложения. Если вы принимаете массив параметров, следует проверить длину массива, которому был передан вызывающий код, и предпринять соответствующие шаги, если оно слишком велико для вашего приложения.  
  
## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Необязательные параметры](./optional-parameters.md)
- [Массивы параметров](./parameter-arrays.md)
- [Перегрузка процедур](./procedure-overloading.md)
- [Рекомендации по устранению неполадок](./troubleshooting-procedures.md)
- [Практическое руководство. Определение различных версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md)
- [Практическое руководство. Вызов перегруженной процедуры](./how-to-call-an-overloaded-procedure.md)
- [Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Разрешение перегрузки](./overload-resolution.md)
