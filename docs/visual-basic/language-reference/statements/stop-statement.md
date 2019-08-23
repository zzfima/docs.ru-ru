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
ms.openlocfilehash: a617038ec51d98c62b6cf7e3c124c8af01305bac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957622"
---
# <a name="stop-statement-visual-basic"></a>Оператор Stop (Visual Basic)
Приостанавливает выполнение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Stop  
```  
  
## <a name="remarks"></a>Примечания  
 Операторы можно разместить `Stop` в любом месте процедуры, чтобы приостановить выполнение. `Stop` Использование инструкции аналогично установке точки останова в коде.  
  
 Инструкция приостанавливает выполнение, но в отличие от `End`этого она не закрывает никакие файлы и не очищает переменные, если она не обнаружена в скомпилированном исполняемом файле (exe). `Stop`  
  
> [!NOTE]
> `Stop` Если инструкция обнаружена в коде, который выполняется вне интегрированной среды разработки (IDE), вызывается отладчик. Это справедливо независимо от того, был ли код скомпилирован в режиме отладки или розничной торговли.  
  
## <a name="example"></a>Пример  
 В этом примере используется `Stop` оператор для приостановки выполнения для каждой итерации `For...Next` в цикле.  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a>См. также

- [Оператор End](../../../visual-basic/language-reference/statements/end-statement.md)
