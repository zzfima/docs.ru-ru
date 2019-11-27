---
title: Оператор Stop
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
ms.openlocfilehash: 497c5f207b2228412411cc3eb01976564f82bd6c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346470"
---
# <a name="stop-statement-visual-basic"></a>Оператор Stop (Visual Basic)
Приостанавливает выполнение.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Stop  
```  
  
## <a name="remarks"></a>Примечания  
 Инструкции `Stop` можно разместить в любом месте процедуры, чтобы приостановить выполнение. Использование оператора `Stop` аналогично установке точки останова в коде.  
  
 Инструкция `Stop` приостанавливает выполнение, но в отличие от `End`, она не закрывает никакие файлы и не очищает переменные, если только она не обнаружена в скомпилированном исполняемом файле (exe).  
  
> [!NOTE]
> Если оператор `Stop` встречается в коде, который выполняется вне интегрированной среды разработки (IDE), вызывается отладчик. Это справедливо независимо от того, был ли код скомпилирован в режиме отладки или розничной торговли.  
  
## <a name="example"></a>Пример  
 В этом примере используется инструкция `Stop` для приостановки выполнения каждой итерации в цикле `For...Next`.  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a>См. также

- [Оператор End](../../../visual-basic/language-reference/statements/end-statement.md)
