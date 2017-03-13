---
title: "Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "перегрузка процедур, неопределенное число параметров"
  - "параметры процедуры"
  - "процедуры, определение"
  - "процедуры, несколько версий"
  - "процедуры, перегрузка"
  - "процедуры, параметры"
  - "код Visual Basic, процедуры"
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Если процедура имеет параметр [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md), то нельзя определить перегруженную версию, принимающую одномерный массив для массива параметров.  Дополнительные сведения содержатся в разделе "Неявные перегрузки для параметра ParamArray" в [Вопросы, связанные с перегрузкой процедур](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md).  
  
### Чтобы перегрузить процедуру, принимающую переменное число параметров  
  
1.  Убедитесь, что использование перегруженных версий более уместно, чем использование параметра `ParamArray`.  См. раздел "Перегрузка и массив параметров" в [Вопросы, связанные с перегрузкой процедур](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md).  
  
2.  Определите, какое число предоставленных значений должна принимать процедура в переменной части списка параметров.  Это может включать случай отсутствия значений и может включать случай одномерного массива.  
  
3.  Для каждого допустимого числа предоставленных значений напишите `Sub` или `Function` инструкцию объявления, определяющую соответствующий список параметров.  Не стоит использовать ни ключевое слово `Optional`, ни `ParamArray` в данной перегруженной версии.  
  
4.  В каждом объявлении ключевому слову `Sub` или `Function` должно предшествовать ключевое слово [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md).  
  
5.  После каждого объявления напишите код процедуры, который должен выполняться, когда вызывающий код предоставит значения, соответствующие элементам списка параметров в объявлении.  
  
6.  Завершите выполнение каждой процедуры оператором `End Sub` или `End Function` .  
  
## Пример  
 В следующем примере показана процедура, определенная с параметром [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md), и эквивалентные перегруженные процедуры.  
  
 [!code-vb[VbVbcnProcedures#69](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]  
  
 Нельзя перегрузить процедуру со списком параметров, который принимает одномерный массив для массива параметров.  Однако можно использовать описания других неявных перегрузок.  Это показано в следующих объявлениях:  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]  
  
 В кодах перегруженных версий не требуется проверка, указывает ли вызывающий код одно или несколько значений параметра `ParamArray`, и если указывает, то сколько.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] передает управление в ту версию, которая соответствует списку аргументов вызова.  
  
## Компиляция кода  
 Поскольку процедура с параметром `ParamArray` эквивалентна набору перегруженных версий, нельзя перегрузить такую процедуру со списком параметров, соответствующим любому списку параметров из этих неявных перегрузок.  Дополнительные сведения см. в разделе [Вопросы, связанные с перегрузкой процедур](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md).  
  
## Безопасность платформы .NET Framework  
 При работе с неограниченно большим массивом есть риск переполнения некоторой внутренней емкости приложения.  Если принимается массив параметров, то следует проверить его длину и предпринять соответствующие действия в случае, если она слишком велика для приложения.  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Необязательные параметры](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Массивы параметров](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Перегрузка процедур](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Устранение неполадок в процедурах](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [Практическое руководство. Определение различных версий процедуры](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-multiple-versions-of-a-procedure.md)   
 [Практическое руководство. Вызов перегруженной процедуры](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-overloaded-procedure.md)   
 [Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Разрешение перегрузки](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)