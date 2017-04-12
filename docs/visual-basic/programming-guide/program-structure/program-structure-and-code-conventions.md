---
title: "Структура программы и соглашения о коде (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- coding conventions
- Visual Basic code, coding conventions
- coding conventions, Visual Basic
- programs, structure
- program structure
- naming conventions, Visual Basic
- best practices, coding conventions
- conventions, Visual Basic coding
- Visual Basic code
- programming, Visual Basic coding conventions
ms.assetid: dd9be76f-6944-4e78-ad72-0b6084a3fc13
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cd25d99d74bf1e4d416c9da63758f6ad04027258
ms.lasthandoff: 03/13/2017

---
# <a name="program-structure-and-code-conventions-visual-basic"></a>Соглашения о структуре программы и коде (Visual Basic)
В этом разделе представлены типичная [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] структура программы, простая [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] программы «Hello, World» и обсуждается [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] соглашения о коде. Соглашения о написании кода, рекомендации, которые касаются не логики программы а ее физическую структуру и внешний вид. После их делает код проще читать, понимать и поддерживать. Соглашения о коде могут включать, помимо прочего:  
  
-   Стандартизованные форматы использования меток и комментирования кода.  
  
-   Рекомендации для интервала, форматирования и создания отступов кода.  
  
-   Соглашения об именовании объектов, переменных и процедур.  
  
 Ниже содержится набор инструкций для программирования [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] программ, а также примеры применения.  
  
## <a name="in-this-section"></a>Содержание  
 [Структура программы Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 Обзор элементов, составляющих [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] программы.  
  
 [Процедура Main в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 Описывает процедуру, которая служит в качестве начальной точки и общего управления для приложения.  
  
 [Ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 Описывает, как ссылаться на объекты в других сборках.  
  
 [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 Описывает, как пространства имен упорядочивания объектов в сборках.  
  
 [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 Содержит общие рекомендации по именованию процедур, константы, переменные, аргументы и объекты.  
  
 [Соглашения о написании кода Visual Basic](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 Общие сведения о правилах, используемых при разработке примеров в данной документации.  
  
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 Описывается, как выборочно скомпилировать одни блоки кода, игнорировать другим пользователям.  
  
 [Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 Показан способ разбиения длинных операторов на несколько строк и сбора коротких операторов в одну строку.  
  
 [Практическое руководство. Сворачивание и скрытие частей кода](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)  
 Показано, как Сворачивание и скрытие частей кода в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] редактора кода.  
  
 [Практическое руководство. Операторы меток](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)  
 Показано, как пометить строку кода для обозначения при использовании операторами, такие как `On Error Goto`.  
  
 [Специальные символы в коде](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 Показано, как и где использовать нецифровые и неалфавитные символы.  
  
 [Комментарии в коде](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 Описывает добавление описательные комментарии в коде.  
  
 [Ключевые слова как имена элементов в коде](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 Описывает использование квадратных скобок (`[]`) для обозначения имен переменных, которые также [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ключевые слова.  
  
 [Me, My, MyBase и MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 Описывает различные способы обращения к элементам [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] программы.  
  
 [Ограничения в Visual Basic](../../../visual-basic/programming-guide/program-structure/limitations.md)  
 Описание устранения известных ограничений кода в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## <a name="related-sections"></a>Связанные разделы  
 [Условные обозначения и соглашения о коде](../../../visual-basic/language-reference/typographic-and-code-conventions.md)  
 Предоставляет стандартные соглашения кода для [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 [Создание кода](https://docs.microsoft.com/visualstudio/ide/writing-code-in-the-code-and-text-editor)  
 Описание возможностей, облегчающих записи и управления кодом.
