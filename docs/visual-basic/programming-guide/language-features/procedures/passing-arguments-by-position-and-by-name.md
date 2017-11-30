---
title: "Передача аргументов по позиции и по имени (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arguments [Visual Basic], passing by name
- procedures [Visual Basic], arguments
- := passing arguments
- procedure arguments
- Visual Basic code, procedures
- named arguments [Visual Basic], passing arguments
- arguments [Visual Basic], passing by position
- Function procedures [Visual Basic], passing arguments
- named parameters [Visual Basic], passing arguments
- named arguments
- passing parameters [Visual Basic], named parameter arguments
- passing parameters [Visual Basic], by position
- procedures [Visual Basic], calling
- named parameters
- Sub procedures [Visual Basic], passing arguments
- argument passing
- passing parameters [Visual Basic], by name
- argument passing [Visual Basic], by position
- arguments [Visual Basic], listing by name
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 164f69fcf23049441a0acbe05058c792d5363a03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>Передача аргументов по позиции и по имени (Visual Basic)
При вызове `Sub` или `Function` процедуры, можно передать аргументы *по позиции* — в том порядке, в котором они отображаются в определении процедуры, или их можно передать *по имени*, без учета.  
  
 Если аргумент передается по имени, укажите его объявленное имя, за которым следует двоеточие и знак равенства (`:=`), а затем значение аргумента. Можно передать аргументы в любом порядке.  
  
 Например, следующая `Sub` процедура принимает три аргумента:  
  
 [!code-vb[VbVbcnProcedures#41](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_1.vb)]  
  
 При вызове этой процедуры можно указать аргументов по позиции, по имени или с помощью их сочетании.  
  
## <a name="passing-arguments-by-position"></a>Передача аргументов по позиции  
 Можно вызвать процедуру `studentInfo` с передачей аргументов по позиции, разделенными запятыми, как показано в следующем примере:  
  
 [!code-vb[VbVbcnProcedures#42](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_2.vb)]  
  
 Если необязательный аргумент в списке позиционный аргумент опущен, необходимо отметить его место запятой. В следующем примере вызывается `studentInfo` без `age` аргумент:  
  
 [!code-vb[VbVbcnProcedures#43](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_3.vb)]  
  
## <a name="passing-arguments-by-name"></a>Передача аргументов по имени  
 Кроме того, можно вызвать метод `studentInfo` с аргументами, передаваемыми по имени и также разделенными запятыми, как показано в следующем примере:  
  
 [!code-vb[VbVbcnProcedures#44](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_4.vb)]  
  
## <a name="mixing-arguments-by-position-and-by-name"></a>Смешивание аргументов по позиции и по имени  
 Аргументов по позиции и по имени в одном вызове процедуры, можно указать, как показано в следующем примере:  
  
 [!code-vb[VbVbcnProcedures#45](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_5.vb)]  
  
 В приведенном выше примере дополнительная запятая, не обязательно отмечающая пропущенный аргумент `age` аргумент, поскольку `birth` передается по имени.  
  
 Если аргументы перепутаны позиции и имя, это позиционные аргументы должны быть первой. После аргумента, передаваемого по имени, все последующие аргументы должны быть по имени.  
  
## <a name="supplying-optional-arguments-by-name"></a>Задание необязательных аргументов по имени  
 Передача аргументов по имени особенно удобна при вызове процедуры, которая имеет более чем один необязательный аргумент. Если аргументы передаются по имени, не имеют несколько запятых подряд для опускать позиционные аргументы. Передача аргументов по имени делает его более удобным для отслеживания какие аргументы заданы, а какие пропущены.  
  
## <a name="restrictions-on-supplying-arguments-by-name"></a>Ограничения при передаче аргументов по имени  
 Аргументы невозможно передать по имени, чтобы избежать ввода обязательных аргументов. Можно опустить только необязательные аргументы.  
  
 Невозможно передать массив параметров по имени. Это так, как при вызове процедуры, необходимо указать неопределенное число разделенных запятыми аргументов для массива параметров, и компилятор не может связывать несколько аргументов с одним именем.  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Практическое руководство. Передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)  
 [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)  
 [Необязательные параметры](./optional-parameters.md)  
 [Массивы параметров](./parameter-arrays.md)  
 [Необязательный](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)
