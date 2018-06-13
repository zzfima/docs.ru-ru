---
title: Другие структуры управления (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: 272ebcf0639b83a51e87de5ebbf93d7e750c03a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654113"
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
