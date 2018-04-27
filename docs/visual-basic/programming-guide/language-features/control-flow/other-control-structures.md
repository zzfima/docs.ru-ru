---
title: Другие структуры управления (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e1ea44cf2f0405dc55f8df60fb842691e50a9a0
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="other-control-structures-visual-basic"></a>Другие структуры управления (Visual Basic)
Visual Basic предоставляет структур управления, которые помогают удаления ресурсов или уменьшите число повторений ссылок на объект.  
  
## <a name="usingend-using-construction"></a>С помощью... Использование конструкции End  
 `Using...End Using` Конструкции устанавливает блок операторов, в котором следует использовать ресурсы, такие как SQL-соединение. При необходимости можно запросить ресурс с `Using` инструкции. После выхода из `Using` блока, Visual Basic автоматически удаляет ресурс, чтобы он будет доступен для использования другим кодом. Ресурс должен быть локальным и допускать удаление. Дополнительные сведения см. в разделе [Оператор using](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="withend-with-construction"></a>С... Завершить с построением  
 `With...End With` Позволяет указать ссылку на объект один раз, а затем запустите последовательность операторов, доступа к его членам. Это может упростить код и повысить производительность, так как Visual Basic не восстанавливает ссылку для каждого оператора, который обращается к ней. Дополнительные сведения см. в разделе [с... Завершить с инструкцией](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## <a name="see-also"></a>См. также  
 [Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [Структуры решений](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Вложенные структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Оператор Using](../../../../visual-basic/language-reference/statements/using-statement.md)  
 [Оператор With...End With](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
