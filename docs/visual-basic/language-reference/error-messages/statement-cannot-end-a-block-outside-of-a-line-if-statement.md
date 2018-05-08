---
title: Оператор не может завершить блок за пределами &#39;Если&#39; инструкции
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: af3006ddc35dfcaa52a54229881baa48cfb7809a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-39if39-statement"></a>Оператор не может завершить блок за пределами &#39;Если&#39; инструкции
Однострочный `If` инструкция содержит несколько операторов, разделенных двоеточием (:), один из которых является `End` инструкции для блока управления за пределами однострочного `If`. Однострочный `If` не используйте инструкции `End If` инструкции.  
  
 **Идентификатор ошибки:** BC32005  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Переместите однострочный `If` инструкции вне блока управления, содержащий `End If` инструкции.  
  
## <a name="see-also"></a>См. также  
 [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
