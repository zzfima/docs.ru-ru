---
title: "Практическое руководство: перегрузка процедуры, принимающей неопределенное число параметров (Visual Basic) | Документы Microsoft"
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
- procedures, parameters
- procedure overloading, indefinite number of parameters
- procedures, defining
- Visual Basic code, procedures
- procedure parameters
- procedures, overloading
- procedures, multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: c7e09bd482e35c7ce7f28a6cc7de0379b7cc89f6
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a>Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров (Visual Basic)
Если процедура имеет [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) параметра, нельзя определить перегруженную версию, принимающую одномерный массив для массива параметров. Дополнительные сведения см. в разделе «Неявные перегрузки для параметра ParamArray» в [вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md).  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a>Чтобы перегрузить процедуру, которая принимает переменное число параметров  
  
1.  Выяснить, что процедуры и вызов уместно перегруженных версий более чем из `ParamArray` параметр. В разделе «Перегрузки и массивы параметров» [вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md).  
  
2.  Определите, какое число предоставленных значений должна принимать процедура в переменной части списка параметров. Это может включать случай отсутствия значений и может включать случай одномерного массива.  
  
3.  Для каждого допустимого числа предоставленных значений напишите `Sub` или `Function` инструкцию объявления, определяющую соответствующий список параметров. Не используйте в `Optional` или `ParamArray` ключевое слово в данной перегруженной версии.  
  
4.  В каждом объявлении перед `Sub` или `Function` ключевого слова with [перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md) ключевое слово.  
  
5.  После каждого объявления напишите код процедуры, который должен выполняться, когда вызывающий код предоставляет значения, соответствующие элементам списка параметров в объявлении.  
  
6.  Завершите выполнение каждой процедуры с `End Sub` или `End Function` инструкцию соответствующим образом.  
  
## <a name="example"></a>Пример  
 В следующем примере показано процедура, определенная с [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) параметр и эквивалентный набор перегруженных процедур.  
  
 [!code-vb[VbVbcnProcedures&#69;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]  
  
 [!code-vb[VbVbcnProcedures&#70;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]  
  
 Нельзя перегрузить процедуру со списком параметров, который принимает одномерный массив для массива параметров. Тем не менее можно использовать подписи неявных перегрузок. Показано в следующих объявлениях.  
  
 [!code-vb[VbVbcnProcedures&#71;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]  
  
 Код перегруженных версий не имеет для проверки в вызывающем коде задано одно или несколько значений для `ParamArray` параметра, и если да, сколько. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]передает управление версию, которая соответствует списку аргументов вызова.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Поскольку процедура с `ParamArray` эквивалентна набору перегруженных версий, нельзя перегрузить такую процедуру со списком параметров, соответствующим любому из этих неявных перегрузок. Дополнительные сведения см. в разделе [вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md).  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 При работе с которой неограниченно большим массивом есть риск переполнения некоторой внутренней емкости приложения. Принимается массив параметров, следует проверить его длину массива, вызывающий код передается и предпринять соответствующие действия, если она слишком велика для приложения.  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)   
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)   
 [Необязательные параметры](./optional-parameters.md)   
 [Массивы параметров](./parameter-arrays.md)   
 [Перегрузка процедур](./procedure-overloading.md)   
 [Рекомендации по устранению неполадок](./troubleshooting-procedures.md)   
 [Практическое руководство: определение различных версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md)   
 [Практическое руководство: вызов перегруженной процедуры](./how-to-call-an-overloaded-procedure.md)   
 [Практическое руководство: перегрузка процедуры, которая принимает необязательные параметры](./how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Разрешение перегрузки](./overload-resolution.md)
