---
title: "Перечисления и уточнение имен (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3cb97d6a8f4b7e81f2b759010214e200ec63ff21
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="enumerations-and-name-qualification-visual-basic"></a>Перечисления и уточнение имен (Visual Basic)
Обычно при ссылке на член перечисления необходимо уточнить имя члена перечисления. Например, для обращения к `Sunday` членом вашей `Days` перечисления, используется следующий синтаксис:  
  
 [!code-vb[VbEnumsTask#18](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_1.vb)]  
  
## <a name="using-the-imports-statement"></a>Используя инструкцию Imports  
 Можно избежать с помощью полных имен, добавив `Imports` инструкции в раздел объявлений пространства имен в коде, как показано в следующем примере:  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 `Imports` Инструкция импортирует имена пространств имен из указанных проектов и сборок, а также из того же проекта, модуль, в котором находится данный оператор. После добавления этой инструкции можно ссылаться к членам перечисления без квалификации, как показано в следующем примере:  
  
 [!code-vb[VbEnumsTask#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_3.vb)]  
  
 Организуя наборы связанных констант в перечисления, можно использовать то же имя константы в различных контекстах. Например, можно использовать те же имена для констант дней недели в `Days` и `WorkDays` перечисления. Если вы используете `Imports` инструкции с перечислениями Будьте внимательны, чтобы избежать неоднозначных ссылок. Рассмотрим следующий пример.  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 [!code-vb[VbEnumsTask#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_4.vb)]  
  
 Предположим, что `Monday` является одновременно членом групп `Days` перечисления и `Workdays` перечисления, этот код создает ошибку компилятора. Чтобы избежать неоднозначности при ссылке на отдельную константу, уточните имя константы перечисления. Следующий код ссылается на `Saturday` констант в `Days` и `WorkDays` перечисления.  
  
 [!code-vb[VbEnumsTask#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_5.vb)]  
  
## <a name="see-also"></a>См. также  
 [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [Как: объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [Практическое руководство. Ссылка на элемент перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [Как: перебор элементов перечисления в Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [Практическое руководство. Определение строки, связанной со значением из перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [Когда следует использовать перечисление](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [Типы данных констант и литералов](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [Оператор Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Оператор Imports (пространство имен и тип .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)
