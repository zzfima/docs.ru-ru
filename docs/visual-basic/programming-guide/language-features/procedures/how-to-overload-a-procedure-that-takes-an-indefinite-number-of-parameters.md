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
ms.openlocfilehash: 3cf75fc6221364704379eb23d308481c34e6c0d6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59316457"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a>Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров (Visual Basic)
Если процедура имеет [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) параметр, не может определить перегруженную версию, принимающую одномерный массив для массива параметров. Дополнительные сведения см. в разделе «Неявные перегрузки для параметра ParamArray» в [вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md).  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a>Перегрузка процедуры, которая принимает переменное количество параметров  
  
1. Выяснить, что процедура и вызов уместно перегруженные версии, более чем из `ParamArray` параметра. См. в разделе «Перегрузки и массивы параметров» в [вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md).  
  
2. Определите, какое число предоставленных значений должна принимать процедура в переменной части списка параметров. Это может включать случай отсутствия значений и может включать в случае одномерного массива.  
  
3. Напишите для каждого допустимого числа предоставленных значений `Sub` или `Function` оператора объявления, который определяет соответствующий список параметров. Не используйте в `Optional` или `ParamArray` ключевое слово в данной перегруженной версии.  
  
4. В каждое объявление перед `Sub` или `Function` ключевого слова with [перегружает](../../../../visual-basic/language-reference/modifiers/overloads.md) ключевое слово.  
  
5. После каждого объявления напишите код процедуры, который должен выполняться, когда вызывающий код предоставляет значения, соответствующие списка параметров в объявлении.  
  
6. Завершите выполнение каждой процедуры с `End Sub` или `End Function` инструкцию соответствующим образом.  
  
## <a name="example"></a>Пример  
 В следующем примере показано процедура, определенная с помощью [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) параметра, а затем эквивалентным набором перегруженные процедуры.  
  
 [!code-vb[VbVbcnProcedures#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#69)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 Не могут перегружать процедуру со списком параметров, который принимает одномерный массив для массива параметров. Тем не менее можно использовать подписи других неявных перегрузок. Следующие объявления, иллюстрируют это.  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
 Код в перегруженных версий не имеет для проверки в вызывающем коде указано одно или несколько значений для `ParamArray` параметра, или если да, сколько. Visual Basic передает управление версию, которая соответствует списку аргументов вызова.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Так как процедура с `ParamArray` эквивалентны набор перегруженных версий, нельзя перегрузить такую процедуру со списком параметров, соответствующим любому из этих неявных перегрузок. Дополнительные сведения см. в разделе [вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md).  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Каждый раз, когда вы имеете дело с массив, который может быть неограниченно большим, есть риск переполнения некоторой внутренней емкости приложения. Если вы принимаете массив параметров, следует проверить длину массива, переданного ему вызывающий код и предпринять соответствующие действия, если она слишком велика для приложения.  
  
## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Необязательные параметры](./optional-parameters.md)
- [Массивы параметров](./parameter-arrays.md)
- [Перегрузка процедур](./procedure-overloading.md)
- [Рекомендации по устранению неполадок](./troubleshooting-procedures.md)
- [Практическое руководство. Определение различных версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md)
- [Практическое руководство. Вызов перегруженной процедуры](./how-to-call-an-overloaded-procedure.md)
- [Практическое руководство. Перегрузка процедуры, которая принимает необязательные параметры](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Overload Resolution](./overload-resolution.md)
