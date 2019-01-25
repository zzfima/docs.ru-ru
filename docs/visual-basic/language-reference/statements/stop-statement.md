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
ms.openlocfilehash: fa9a1942903dff6f673d87b67ebcad047a410425
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624786"
---
# <a name="stop-statement-visual-basic"></a>Оператор Stop (Visual Basic)
Приостанавливает выполнение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Stop  
```  
  
## <a name="remarks"></a>Примечания  
 Вы можете поместить `Stop` инструкций в любом месте процедуры для приостановки выполнения. С помощью `Stop` инструкция похожа на задание точки останова в коде.  
  
 `Stop` Инструкция приостанавливает выполнение, но в отличие от `End`, закройте все файлы или не удаляет переменные, в том случае, если только встречается в файле скомпилированный исполняемый файл (.exe).  
  
> [!NOTE]
>  Если `Stop` встречается в коде, выполняемом вне интегрированной среде разработки (IDE), вызывается отладчик. Это верно независимо от того, скомпилирован ли код в режиме debug или retail.  
  
## <a name="example"></a>Пример  
 В этом примере используется `Stop` инструкции для приостановки выполнения на каждом проходе через `For...Next` цикла.  
  
 [!code-vb[VbVbalrStatements#56](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/stop-statement_1.vb)]  
  
## <a name="see-also"></a>См. также
- [Оператор End](../../../visual-basic/language-reference/statements/end-statement.md)
