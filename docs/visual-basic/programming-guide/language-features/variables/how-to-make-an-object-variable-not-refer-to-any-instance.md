---
title: Практическое руководство. Сделать объектную переменную нессылающейся на какой-либо экземпляр (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: e647f2f891b06aa1767faac49b01df98ea31ec1c
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004916"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>Практическое руководство. Сделать объектную переменную нессылающейся на какой-либо экземпляр (Visual Basic)
Можно разорвать связь объектной переменной с любым экземпляром объекта, задав для него значение [Nothing](../../../../visual-basic/language-reference/nothing.md).  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>Отмена связывания объектной переменной с любым экземпляром объекта  
  
- Присвойте переменной значение `Nothing` в операторе присваивания.  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Если код пытается получить доступ к члену объектной переменной, для которой задано значение `Nothing`, возникает <xref:System.NullReferenceException>. Если для переменной объекта присвоить значение `Nothing` часто или если переменная не инициализирована, рекомендуется заключить доступ к членам в блок `Try...Catch...Finally`.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 При использовании объектной переменной для объектов, содержащих конфиденциальные или конфиденциальные данные, можно присвоить переменной значение `Nothing`, если вы активно не работаете с одним из этих объектов. Это снижает вероятность того, что вредоносный код получает доступ к данным.  
  
## <a name="see-also"></a>См. также

- <xref:System.NullReferenceException>
- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Присваивание объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
- [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
