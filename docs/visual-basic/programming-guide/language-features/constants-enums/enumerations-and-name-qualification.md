---
title: Перечисления и уточнение имен (Visual Basic)
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
ms.openlocfilehash: f0a806b040720cf6682f8a72025a0590dd4d91f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818440"
---
# <a name="enumerations-and-name-qualification-visual-basic"></a>Перечисления и уточнение имен (Visual Basic)
Как правило при ссылке на член перечисления, необходимо уточнить имя члена перечисления. Например, для ссылки на `Sunday` членом вашей `Days` перечисления, используется следующий синтаксис:  
  
 [!code-vb[VbEnumsTask#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#18)]  
  
## <a name="using-the-imports-statement"></a>Используя оператор Imports  
 Можно избежать с помощью полных имен, добавив `Imports` инструкцию, чтобы раздел объявлений пространства имен кода, как показано в следующем примере:  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 `Imports` Инструкция импортирует имена пространств имен из указанных проектов и сборок, а также из того же проекта модуля, в котором находится данный оператор. После добавления этой инструкции можно ссылаться к членам перечисления без квалификации, как показано в следующем примере:  
  
 [!code-vb[VbEnumsTask#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#24)]  
  
 Организуя наборами связанных констант в перечислениях, можно использовать то же имя константы в различных контекстах. Например, можно использовать те же имена констант дней недели в `Days` и `WorkDays` перечисления. Если вы используете `Imports` инструкции с перечислениями, необходимо быть осторожным, чтобы избежать неоднозначности. Рассмотрим следующий пример.  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 [!code-vb[VbEnumsTask#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#25)]  
  
 Предположим, что `Monday` является одновременно членом групп `Days` перечисления и `Workdays` перечисления, этот код создает ошибку компилятора. Чтобы избежать неоднозначности при ссылке на отдельную константу, уточните имя константы перечисления. Приведенный ниже код относится к `Saturday` константы в `Days` и `WorkDays` перечисления.  
  
 [!code-vb[VbEnumsTask#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#32)]  
  
## <a name="see-also"></a>См. также

- [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)
- [Практическое руководство. Объявления перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Практическое руководство. Ссылка на член перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Практическое руководство. Перебор элементов перечисления в Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Практическое руководство. Определение строки, связанной со значением из перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Когда следует использовать перечисление](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Типы данных констант и литералов](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [Оператор Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [Оператор Imports (пространство имен и тип .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Типы данных](../../../../visual-basic/language-reference/data-types/index.md)
