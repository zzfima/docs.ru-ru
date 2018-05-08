---
title: Оператор Resume
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
ms.openlocfilehash: 1d03f631893be51529f29af824de0d684bf43804
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="resume-statement"></a>Оператор Resume
Возобновление выполнения после завершения процедуры обработки ошибок.  
  
 Мы рекомендуем использовать структурированная обработка исключений в коде, когда это возможно, вместо использования неструктурированной обработки исключений и `On Error` и `Resume` инструкции. Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a>Части  
 `Resume`  
 Обязательно. Если ошибка произошла в той же процедуре обработчик ошибок, выполнение возобновляется с оператора, который вызвал ошибку. Если ошибка возникла в вызываемой процедуре, выполнение возобновляется с оператора, который последним вызвал процедуру, содержащую обработчик ошибок.  
  
 `Next`  
 Необязательный. Если ошибка произошла в той же процедуре обработчик ошибок, выполнение возобновляется с оператора, следующего оператора, который вызвал ошибку. Если ошибка возникла в вызываемой процедуре, выполнение возобновляется с оператора, следующего оператора, который последним вызвал процедуру, содержащую обработчик ошибок (или `On Error Resume Next` инструкции).  
  
 `line`  
 Необязательный. Выполнение возобновляется строки, указанной в обязательном `line` аргумент. `line` Аргумент представляет собой метку или номер строки и должно быть в той же процедуре обработчик ошибок.  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Мы рекомендуем использовать структурированная обработка исключений в коде, когда это возможно, вместо использования неструктурированной обработки исключений и `On Error` и `Resume` инструкции. Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 Если вы используете `Resume` инструкции в любом отличный от в процедуру обработки ошибок, возникает ошибка.  
  
 `Resume` Оператор не может использоваться в процедуре, содержащей `Try...Catch...Finally` инструкции.  
  
## <a name="example"></a>Пример  
 В этом примере используется `Resume` инструкции для окончания обработки ошибки в процедуре, а затем возобновить выполнение с инструкцией, вызвавшей ошибку. Чтобы проиллюстрировать использование создается ошибка номер 55 `Resume` инструкции.  
  
 [!code-vb[VbVbalrErrorHandling#16](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/resume-statement_1.vb)]  
  
## <a name="requirements"></a>Требования  
 **Пространство имен:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Сборка:** Visual Basic Runtime Library (Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>См. также  
 [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Оператор Error](../../../visual-basic/language-reference/statements/error-statement.md)  
 [Оператор On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)
