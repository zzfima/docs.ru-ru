---
title: Другие структуры управления
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: 758df361f421684655147ae288af3f350e53c4d7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348133"
---
# <a name="other-control-structures-visual-basic"></a>Другие структуры управления (Visual Basic)
Visual Basic предоставляет управляющие структуры, которые помогают удалить ресурс или сократить количество повторных ссылок на объект.  
  
## <a name="usingend-using-construction"></a>Использование... Завершить с помощью конструкции  
 Конструкция `Using...End Using` устанавливает блок операторов, в рамках которого используется ресурс, например соединение SQL. При необходимости можно получить ресурс с помощью инструкции `Using`. При выходе из блока `Using` Visual Basic автоматически уничтожает ресурс, чтобы он был доступен для использования другим кодом. Ресурс должен быть локальным и удаляемым. Дополнительные сведения см. в разделе [Оператор using](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="withend-with-construction"></a>С помощью... Завершить конструкцию  
 Конструкция `With...End With` позволяет указать ссылку на объект один раз, а затем выполнить последовательность инструкций, обращающихся к ее членам. Это может упростить код и повысить производительность, поскольку Visual Basic не придется повторно устанавливать ссылку для каждой инструкции, которая обращается к ней. Дополнительные сведения см [. в разделе with... Конец оператора](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## <a name="see-also"></a>См. также

- [Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Структуры решений](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Вложенные структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Оператор Using](../../../../visual-basic/language-reference/statements/using-statement.md)
- [Оператор With...End With](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
