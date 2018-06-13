---
title: Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров (Visual Basic)
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
ms.openlocfilehash: 026dd59db135e8b195ae014aaff5e3a6a7846fc7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651496"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a>Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров (Visual Basic)
Если процедура имеет [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) параметра, нельзя определить перегруженную версию, принимающую одномерный массив для массива параметров. Дополнительные сведения см. в разделе «Неявные перегрузки для параметра ParamArray» в [вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md).  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a>Перегрузка процедуры, которая принимает переменное число параметров  
  
1.  Выяснить, что процедура и вызов уместно перегруженные версии, более чем из `ParamArray` параметра. В разделе «Перегрузки и массивы параметров» в [вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md).  
  
2.  Определите, какое число предоставленных значений должна принимать процедура в переменной части списка параметров. Это может включать случай отсутствия значений и может включать в случае одномерного массива.  
  
3.  Для каждого допустимого числа предоставленных значений напишите `Sub` или `Function` инструкцию объявления, определяющую соответствующий список параметров. Не используйте в `Optional` или `ParamArray` ключевое слово в данной перегруженной версии.  
  
4.  В каждое объявление перед `Sub` или `Function` ключевого слова with [перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md) ключевое слово.  
  
5.  После каждого объявления напишите код процедуры, который должен выполняться, когда вызывающий код не предоставляет значения, соответствующие списка параметров в объявлении.  
  
6.  Завершите выполнение каждой процедуры с `End Sub` или `End Function` инструкцию соответствующим образом.  
  
## <a name="example"></a>Пример  
 В следующем примере показано процедура, определенная с [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) параметра, а затем аналогичный набор перегруженных процедур.  
  
 [!code-vb[VbVbcnProcedures#69](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]  
  
 Нельзя перегрузить процедуру со списком параметров, который принимает одномерный массив для массива параметров. Тем не менее можно использовать подписи неявных перегрузок. Это показано в следующих объявлениях.  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]  
  
 Код перегруженных версий не имеет для проверки в вызывающем коде задано одно или несколько значений для `ParamArray` параметра, и если да, сколько. Visual Basic передает управление в версию, которая соответствует списку аргументов вызова.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Поскольку процедура с `ParamArray` параметр эквивалентен набор перегруженных версий, нельзя перегрузить такую процедуру со списком параметров, соответствующим любому из этих неявных перегрузок. Дополнительные сведения см. в разделе [вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md).  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 При работе с которой неограниченно большим массивом есть риск переполнения некоторой внутренней емкости приложения. Если вы принимаете массив параметров, следует проверить его длину массива, вызывающий код передается и предпринять соответствующие действия, если она слишком велика для приложения.  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Необязательные параметры](./optional-parameters.md)  
 [Массивы параметров](./parameter-arrays.md)  
 [Перегрузка процедур](./procedure-overloading.md)  
 [Рекомендации по устранению неполадок](./troubleshooting-procedures.md)  
 [Практическое руководство. Определение различных версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md)  
 [Практическое руководство. Вызов перегруженной процедуры](./how-to-call-an-overloaded-procedure.md)  
 [Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [Разрешение перегрузки](./overload-resolution.md)
