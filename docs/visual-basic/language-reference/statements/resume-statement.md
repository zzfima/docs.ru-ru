---
title: Resume-оператор (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Resume
- vb.ResumeNext
helpviewer_keywords:
- Next statement [Visual Basic], Resume
- Resume Next statement [Visual Basic]
- execution [Visual Basic], resuming
- run-time errors [Visual Basic], resuming after
- Resume statement [Visual Basic], syntax
- errors [Visual Basic], resuming after
- Error statement [Visual Basic], and Resume statement
- execution
- Resume statement [Visual Basic]
ms.assetid: e24d058b-1a5c-4274-acb9-7d295d3ea537
ms.openlocfilehash: fcb50a9c7e36bab046be25d7f82f91cfe0f9be8e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966922"
---
# <a name="resume-statement"></a>Оператор Resume
Возобновляет выполнение после завершения процедуры обработки ошибок.  
  
 Мы рекомендуем использовать структурированной обработки исключений в коде, когда это возможно, а не с помощью неструктурированной обработки исключений и `On Error` и `Resume` инструкций. Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a>Части  
 `Resume`  
 Обязательный. Если ошибка произошла в той же процедуре, обработчик ошибок, выполнение возобновляется с оператора, который вызвал ошибку. Если ошибка возникла в вызываемой процедуре, выполнение возобновляется с оператора, который последним вызвал процедуру, содержащую обработчик ошибок.  
  
 `Next`  
 Необязательный параметр. Если ошибка произошла в той же процедуре, обработчик ошибок, выполнение возобновляется с оператора, следующего инструкцию, которая вызвала ошибку. Если ошибка возникла в вызываемой процедуре, выполнение возобновляется с оператора, следующего оператора, который последним вызвал процедуру, содержащую обработчик ошибок (или `On Error Resume Next` инструкции).  
  
 `line`  
 Необязательный параметр. Выполнение возобновляется строки, указанной в обязательном `line` аргумент. `line` Аргумент представляет собой метку или номер строки и должно быть в той же процедуре в качестве обработчика ошибок.  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Мы рекомендуем использовать структурированной обработки исключений в коде, когда это возможно, а не с помощью неструктурированной обработки исключений и `On Error` и `Resume` инструкций. Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 Если вы используете `Resume` инструкции в любом отличное от в процедуру обработки ошибок, возникает ошибка.  
  
 `Resume` Оператор не может использоваться в любой процедуре, которая содержит `Try...Catch...Finally` инструкции.  
  
## <a name="example"></a>Пример  
 В этом примере используется `Resume` инструкцию, чтобы завершить обработку ошибок в процедуре и затем возобновить выполнение с помощью инструкции, которая вызвала ошибку. Чтобы проиллюстрировать использование создается ошибка номер 55 `Resume` инструкции.  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a>Требования  
 **Пространство имен:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Сборка:** Visual Basic (библиотека времени выполнения, в Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>См. также
- [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Оператор Error](../../../visual-basic/language-reference/statements/error-statement.md)
- [Оператор On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)
