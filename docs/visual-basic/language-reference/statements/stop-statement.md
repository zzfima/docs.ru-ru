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
ms.openlocfilehash: 590ac27ebab881353a69077aabdf7a2def3396a6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967853"
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
