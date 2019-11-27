---
title: Перечисления и уточнение имен
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- Imports statement [Visual Basic], namespace declarations
- declaring namespaces [Visual Basic], enumerations
- name collisions
- ambiguous names [Visual Basic], enumerations
- enumerations [Visual Basic], name qualification
- names [Visual Basic], avoiding conflicts
- namespaces [Visual Basic], declaring
- naming conflicts, enumerations
- naming conflicts, qualifying names
- declaring enumerations
- references [Visual Basic], enumeration members
- naming conventions [Visual Basic], naming conflicts
- declarations [Visual Basic], namespaces
ms.assetid: 08ba2738-df52-4140-bc55-f57c871c9b73
ms.openlocfilehash: 4121266447b771ba954ad52a46e0d8b88de3f9cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347499"
---
# <a name="enumerations-and-name-qualification-visual-basic"></a>Перечисления и уточнение имен (Visual Basic)
Обычно при ссылке на член перечисления необходимо уточнить имя члена с помощью имени перечисления. Например, для ссылки на элемент `Sunday` перечисления `Days` используется следующий синтаксис:  
  
 [!code-vb[VbEnumsTask#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#18)]  
  
## <a name="using-the-imports-statement"></a>Использование оператора Imports  
 Можно избежать использования полных имен, добавив инструкцию `Imports` в раздел кода объявлений пространства имен, как показано в следующем примере:  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 Оператор `Imports` импортирует имена пространств имен из проектов и сборок, на которые имеются ссылки, и из того же проекта, в котором находится модуль, в котором находится инструкция. После добавления этой инструкции можно ссылаться на члены перечисления без уточнения, как показано в следующем примере:  
  
 [!code-vb[VbEnumsTask#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#24)]  
  
 Организуя наборы связанных констант в перечисления, можно использовать одни и те же имена констант в разных контекстах. Например, можно использовать те же имена для констант дня недели в перечислениях `Days` и `WorkDays`. При использовании оператора `Imports` с перечислениями необходимо избегать неоднозначных ссылок. Рассмотрим следующий пример.  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 [!code-vb[VbEnumsTask#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#25)]  
  
 Если предположить, что `Monday` является членом перечисления `Days` и `Workdays` перечисления, этот код создает ошибку компилятора. Чтобы избежать неоднозначных ссылок при ссылке на отдельную константу, уточните имя константы с его перечислением. Следующий код ссылается на константы `Saturday` в перечислениях `Days` и `WorkDays`.  
  
 [!code-vb[VbEnumsTask#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#32)]  
  
## <a name="see-also"></a>См. также

- [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)
- [Инструкции. Объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Практическое руководство. Ссылка на элемент перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Пошаговое руководство. перебор перечислений в Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Практическое руководство. Определение строки, связанной со значением из перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Когда следует использовать перечисление](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Типы данных констант и литералов](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [Оператор Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [Оператор Imports (пространство имен и тип .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Типы данных](../../../../visual-basic/language-reference/data-types/index.md)
