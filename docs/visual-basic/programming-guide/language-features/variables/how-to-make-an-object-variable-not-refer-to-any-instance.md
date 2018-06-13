---
title: Практическое руководство. Как сделать так, чтобы объектная переменная не указывала ни на какой экземпляр (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: bf918b762261e1dd1fc4161a10203f3d0067e454
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649728"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>Практическое руководство. Как сделать так, чтобы объектная переменная не указывала ни на какой экземпляр (Visual Basic)
Разорвать связь объектной переменной с любым экземпляром объекта, указав для нее значение [ничего не](../../../../visual-basic/language-reference/nothing.md).  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>Чтобы разорвать связь объектной переменной с любым экземпляром объекта  
  
-   Присвойте переменной `Nothing` в операторе присваивания.  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Если код пытается получить доступ к члену объектную переменную, которая настроена для `Nothing`, <xref:System.NullReferenceException> происходит. Если значение переменной объекта `Nothing` часто, или если это возможно, переменная не инициализирована, рекомендуется заключать обращения к членам в `Try...Catch...Finally` блока.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Если вы используете объектную переменную для объектов, содержащих конфиденциальные или важные данные, можно присвоить переменной `Nothing` при отсутствии обращения активно с одного из этих объектов. Это снижает вероятность получения доступа к данным вредоносного кода.  
  
## <a name="see-also"></a>См. также  
 <xref:System.NullReferenceException>  
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Присваивание объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Nothing](../../../../visual-basic/language-reference/nothing.md)  
 [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Разрешение вопросов, связанных с исключениями: System.NullReferenceException](http://msdn.microsoft.com/library/4822b0b4-8105-43fb-887a-3cc51ff02899)
