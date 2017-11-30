---
title: "Объект или класс не поддерживает набор событий"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: be4b9140222ef969bfb836fd74f45b8f662360b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>Объект или класс не поддерживает набор событий
Предпринята попытка использования `WithEvents` переменной с компонентом, который не может служить источником событий для указанного набора событий. Например, требуется приемник событий объекта, создайте другой объект, `Implements` первый объект. Хотя может показаться, что может управлять событиями из реализованного объекта, это не всегда так. `Implements`реализует только интерфейс для методов и свойств. `WithEvents`не поддерживается для частного `UserControls`, так как информация о типе, необходимые для вызова `ObjectEvent` доступен не во время выполнения.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Не удается получить события для компонента, который не является источником событий.  
  
## <a name="see-also"></a>См. также  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)  
 [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
