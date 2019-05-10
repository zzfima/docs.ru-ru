---
title: Практическое руководство. Сделать переменная объекта ссылается на любой экземпляр (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 820d4cb9d17bf467d257bfbba5f43f07228c0b4f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663560"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>Практическое руководство. Сделать переменная объекта ссылается на любой экземпляр (Visual Basic)
При установке для него можно разорвать связь объектной переменной с любым экземпляром объекта [ничего не](../../../../visual-basic/language-reference/nothing.md).  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>Чтобы разорвать связь с любым экземпляром объекта переменной объекта  
  
- Присвойте переменной `Nothing` в операторе присваивания.  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Если код пытается получить доступ к члену переменной объекта, которое было задано для `Nothing`, <xref:System.NullReferenceException> происходит. Если задано значение переменной объекта `Nothing` часто, или если это возможно, переменная не инициализирована, рекомендуется заключать доступе к членам в `Try...Catch...Finally` блока.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Если вы используете переменную объекта для объектов, содержащих конфиденциальные данные, можно присвоить переменной `Nothing` Если вы не работаете активно с одного из этих объектов. Это снижает вероятность вредоносного кода, доступ к данным.  
  
## <a name="see-also"></a>См. также

- <xref:System.NullReferenceException>
- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Присваивание объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
- [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
