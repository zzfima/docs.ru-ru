---
title: Другие структуры управления (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: c42070ce2ea866e59e1b2e190f7c05e1ee7cc922
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907846"
---
# <a name="other-control-structures-visual-basic"></a>Другие структуры управления (Visual Basic)
Visual Basic предоставляет структур управления, которые помогут вам удаления ресурсов, или уменьшите количество раз, вам необходимо будет повторить ссылку на объект.  
  
## <a name="usingend-using-construction"></a>С помощью... С помощью конструкции  
 `Using...End Using` Конструкции устанавливает блок операторов, в котором следует использовать ресурсы, например подключение к SQL. При необходимости можно запросить ресурс с `Using` инструкции. После выхода из `Using` блока, Visual Basic автоматически удаляет ресурс, чтобы он доступен для использования другим кодом. Ресурс должен быть локальный и высвобождаемого. Дополнительные сведения см. в разделе [Оператор using](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="withend-with-construction"></a>С помощью... Завершить с помощью конструкции  
 `With...End With` Позволяет указать ссылку на объект один раз и затем выполнить ряд инструкций, которые обращаются к его члены. Это можно упростить код и повысить производительность, поскольку Visual Basic не восстанавливает ссылку для каждого оператора, который обращается к ней. Дополнительные сведения см. в разделе [с... Завершить с помощью инструкции](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## <a name="see-also"></a>См. также

- [Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Структуры решений](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Вложенные структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Оператор Using](../../../../visual-basic/language-reference/statements/using-statement.md)
- [Оператор With...End With](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
