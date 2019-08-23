---
title: Оператор Resume (Visual Basic)
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
ms.openlocfilehash: 884bdaa0c19508b5a6bf6377568a53acc6880518
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957681"
---
# <a name="resume-statement"></a>Оператор Resume
Возобновляет выполнение по завершении подпрограммы обработки ошибок.  
  
 Мы рекомендуем использовать структурированную обработку исключений в коде, когда это возможно, вместо использования неструктурированной обработки исключений и `On Error` инструкций и. `Resume` Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a>Части  
 `Resume`  
 Обязательный. Если ошибка произошла в той же процедуре, что и обработчик ошибок, выполнение возобновляется с помощью инструкции, вызвавшей ошибку. Если ошибка произошла в вызванной процедуре, выполнение возобновляется с оператора, который последний раз вызывался из процедуры, содержащей подпрограмму обработки ошибок.  
  
 `Next`  
 Необязательный параметр. Если ошибка произошла в той же процедуре, что и обработчик ошибок, выполнение возобновляется с помощью инструкции, следующей за инструкцией, вызвавшей ошибку. Если ошибка произошла в вызванной процедуре, выполнение возобновляется с помощью инструкции, следующей за инструкцией, которая последний раз вызвала процедуру, содержащую подпрограмму обработки ошибок `On Error Resume Next` (или).  
  
 `line`  
 Необязательный параметр. Выполнение возобновляется в строке, указанной в аргументе `line` Required. `line` Аргумент является меткой строки или номером строки и должен находиться в той же процедуре, что и обработчик ошибок.  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
> Рекомендуется использовать структурированную обработку исключений в коде, когда это возможно, вместо использования неструктурированной обработки исключений и `On Error` инструкций и. `Resume` Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 При использовании `Resume` инструкции в любом месте, кроме в подпрограммы обработки ошибок, возникает ошибка.  
  
 Инструкция не может быть использована в любой процедуре, `Try...Catch...Finally` содержащей оператор. `Resume`  
  
## <a name="example"></a>Пример  
 В этом примере `Resume` оператор используется для завершения обработки ошибок в процедуре, а затем возобновляется выполнение с инструкцией, вызвавшей ошибку. Номер ошибки 55 создается для демонстрации использования `Resume` инструкции.  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a>Требования  
 **Пространство имен:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Сборок** Visual Basic (библиотека времени выполнения, в Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>См. также

- [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Оператор Error](../../../visual-basic/language-reference/statements/error-statement.md)
- [Оператор On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)
