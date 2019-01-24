---
title: Оператор не может завершить блок за пределами &#39;Если&#39; инструкции
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 78fe136acbd09e202b1daeb16dd540cf42ada390
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574720"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-39if39-statement"></a>Оператор не может завершить блок за пределами &#39;Если&#39; инструкции
Однострочный `If` инструкция содержит несколько операторов, разделенных двоеточием (:), один из которых является `End` инструкции для блока управления за пределами однострочного `If`. Однострочный `If` инструкций не используйте `End If` инструкции.  
  
 **Идентификатор ошибки:** BC32005  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Переместите однострочный `If` оператор вне блока управления, содержащего `End If` инструкции.  
  
## <a name="see-also"></a>См. также
- [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
