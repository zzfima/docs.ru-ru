---
title: Оператор не может завершить блок за пределами однострочной инструкции If
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 85573099ec0a3f8a23c17bdf384c4c105f9157df
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62055138"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a>Оператор не может завершить блок за пределами однострочной инструкции If
Однострочный `If` инструкция содержит несколько операторов, разделенных двоеточием (:), один из которых является `End` инструкции для блока управления за пределами однострочного `If`. Однострочный `If` инструкций не используйте `End If` инструкции.  
  
 **Идентификатор ошибки:** BC32005  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Переместите однострочный `If` оператор вне блока управления, содержащего `End If` инструкции.  
  
## <a name="see-also"></a>См. также

- [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
