---
title: События общих переменных WithEvents не могут обрабатываться не используемыми совместно методами
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 53372927b88df3946583564492df42170f302739
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>События общих переменных WithEvents не могут обрабатываться не используемыми совместно методами
Переменная, объявленная с `Shared` модификатор — общей переменной. Общей переменной определяет только одно место хранения. Переменная, объявленная с `WithEvents` модификатор подтверждает, что тип, к которому принадлежит переменная обрабатывает набор событий, вызываемых переменной. Когда значение присваивается переменной, свойства, созданные `WithEvents` объявление отсоединяется от любого существующего обработчика событий и подключает обработчик событий через `Add` метод.  
  
 **Идентификатор ошибки:** BC30594  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Объявите обработчик событий `Shared`.  
  
## <a name="see-also"></a>См. также  
 [Общие](../../../visual-basic/language-reference/modifiers/shared.md)  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)
