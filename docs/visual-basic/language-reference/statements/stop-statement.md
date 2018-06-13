---
title: Оператор Stop (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Stop
helpviewer_keywords:
- breakpoints, Stop statements
- Stop statements [Visual Basic], syntax
- Stop statements [Visual Basic]
- execution [Visual Basic], suspending
- processing, interrupting
- processes, interrupting
- execution [Visual Basic], stopping
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
ms.openlocfilehash: 955a3b6a2f7dc1d0e9823ed6d500ab7f7f9fe5b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599139"
---
# <a name="stop-statement-visual-basic"></a>Оператор Stop (Visual Basic)
Приостанавливает выполнение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Stop  
```  
  
## <a name="remarks"></a>Примечания  
 Можно поместить `Stop` инструкций в любом месте процедуры для приостановки выполнения. С помощью `Stop` инструкция похожа на задание точки останова в коде.  
  
 `Stop` Оператор приостанавливает выполнение, но в отличие от `End`, не закрывает файлы и не удаляет переменные, если только встречается в компилируемый исполняемый файл (.exe) файл.  
  
> [!NOTE]
>  Если `Stop` встречается в коде, который выполняется вне интегрированной среды разработки (IDE), вызывается отладчик. Это верно независимо от того, скомпилирован ли код в режиме отладки или в розницу.  
  
## <a name="example"></a>Пример  
 В этом примере используется `Stop` инструкции для приостановки выполнения на каждом шаге цикла `For...Next` цикла.  
  
 [!code-vb[VbVbalrStatements#56](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/stop-statement_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор End](../../../visual-basic/language-reference/statements/end-statement.md)
