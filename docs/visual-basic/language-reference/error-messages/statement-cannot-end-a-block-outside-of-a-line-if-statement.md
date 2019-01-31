---
title: Оператор не может завершить блок за пределами однострочной инструкции If
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 0cee52f0ca00395d93c469aae6498fd3793f1085
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266323"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a>Оператор не может завершить блок за пределами однострочной инструкции If
Однострочный `If` инструкция содержит несколько операторов, разделенных двоеточием (:), один из которых является `End` инструкции для блока управления за пределами однострочного `If`. Однострочный `If` инструкций не используйте `End If` инструкции.  
  
 **Идентификатор ошибки:** BC32005  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Переместите однострочный `If` оператор вне блока управления, содержащего `End If` инструкции.  
  
## <a name="see-also"></a>См. также
- [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
