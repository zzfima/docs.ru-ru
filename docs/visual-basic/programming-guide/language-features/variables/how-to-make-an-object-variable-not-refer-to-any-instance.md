---
title: Практическое руководство. Как сделать так, чтобы объектная переменная не указывала ни на какой экземпляр
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 320dadb61c12f3339c5328dcef31c41503892c56
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352893"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>Практическое руководство. Как сделать так, чтобы объектная переменная не указывала ни на какой экземпляр (Visual Basic)
Можно разорвать связь объектной переменной с любым экземпляром объекта, задав для него значение [Nothing](../../../../visual-basic/language-reference/nothing.md).  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>Отмена связывания объектной переменной с любым экземпляром объекта  
  
- Задайте для переменной значение `Nothing` в операторе присваивания.  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Если код пытается получить доступ к члену объектной переменной, для которой задано значение `Nothing`, происходит <xref:System.NullReferenceException>. Если переменная объекта присвоена `Nothing` часто или если переменная не инициализирована, рекомендуется заключить доступ к членам в блок `Try...Catch...Finally`.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 При использовании объектной переменной для объектов, содержащих конфиденциальные или конфиденциальные данные, можно присвоить переменной значение `Nothing`, если вы не работаете с одним из этих объектов. Это снижает вероятность того, что вредоносный код получает доступ к данным.  
  
## <a name="see-also"></a>См. также

- <xref:System.NullReferenceException>
- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Присваивание объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
- [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
