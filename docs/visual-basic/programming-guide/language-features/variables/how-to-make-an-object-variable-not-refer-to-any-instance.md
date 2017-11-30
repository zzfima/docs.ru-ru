---
title: "Практическое руководство. Как сделать так, чтобы объектная переменная не указывала ни на какой экземпляр (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3b33aef06300bf35b7138ec5b40747532a77140a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
