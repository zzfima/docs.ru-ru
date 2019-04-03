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
ms.openlocfilehash: 80d6734945324f3f517b256051486273f6b687ec
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827995"
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
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a>См. также

- [Оператор End](../../../visual-basic/language-reference/statements/end-statement.md)
