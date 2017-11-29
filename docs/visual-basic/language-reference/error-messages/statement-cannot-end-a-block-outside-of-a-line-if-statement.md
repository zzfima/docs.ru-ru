---
title: "Оператор не может завершить блок за пределами строки &#39; Если &#39; инструкции"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords: BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 73fe3eb44e904366db7d505bbe8c5fef461eb78b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-39if39-statement"></a>Оператор не может завершить блок за пределами строки &#39; Если &#39; инструкции
Однострочный `If` инструкция содержит несколько операторов, разделенных двоеточием (:), один из которых является `End` инструкции для блока управления за пределами однострочного `If`. Однострочный `If` не используйте инструкции `End If` инструкции.  
  
 **Идентификатор ошибки:** BC32005  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Переместите однострочный `If` инструкции вне блока управления, содержащий `End If` инструкции.  
  
## <a name="see-also"></a>См. также  
 [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
