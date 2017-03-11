---
title: "Соглашения о структуре программы и коде (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "соглашения о написании кода"
  - "код Visual Basic, соглашения о написании кода"
  - "соглашения о написании кода, Visual Basic"
  - "программы, структура"
  - "структура программы"
  - "соглашения об именовании, Visual Basic"
  - "рекомендации, соглашения о написании кода"
  - "соглашения, написание кода в Visual Basic"
  - "код Visual Basic"
  - "программирование, соглашения о написании кода в Visual Basic"
ms.assetid: dd9be76f-6944-4e78-ad72-0b6084a3fc13
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Соглашения о структуре программы и коде (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

В этом разделе представлены типичная структура программы [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], простая [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] программа "Hello, World" и описание соглашений о коде [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] .  Соглашения о коде представляют собой рекомендации, которые касаются не логики программы, а ее внешней структуры и оформления.  Удовлетворяющий этим соглашениям код легче читается, его можно проще понять и поддерживать.  Среди прочего, соглашения о коде могут включать:  
  
-   стандартизованные форматы использования меток и комментирования кода;  
  
-   рекомендации о форматировании кода, а также об использовании отступов и пробелов;  
  
-   соглашения об именовании объектов, переменных и процедур.  
  
 Ниже содержится ряд рекомендаций по написанию программ на [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] и примеры применения этих рекомендаций.  
  
## В этом подразделе  
 [Структура программы Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 Обзор элементов, составляющих программу на [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 [Процедура Main в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 Обсуждение процедуры, служащей начальной точкой программы и осуществляющей общее управление работой приложения.  
  
 [Ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 Описание способов создания ссылок на объекты в других сборках.  
  
 [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 Способы организации объектов в сборках с помощью пространств имен.  
  
 [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 Общие рекомендации по именованию процедур, констант, переменных, аргументов и объектов.  
  
 [Соглашения о написании кода в Visual Basic](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 Общие сведения о правилах, используемых при разработке примеров в данной документации.  
  
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 Описывается, как выборочно скомпилировать одни блоки кода, проигнорировав другие.  
  
 [Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 Примеры разбиения длинных операторов на несколько строк и сбора коротких операторов в одну строку.  
  
 [Практическое руководство. Сворачивание и сокрытие частей кода](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)  
 Показывает, как сворачивать и скрывать разделы кода в редакторе кода [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 [Практическое руководство. Операторы меток](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)  
 Показывает, как пометить строку кода для обозначения при использовании инструкций, например `On Error Goto`.  
  
 [Специальные символы в коде](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 Описание того, как и где использовать нецифровые и неалфавитные знаки.  
  
 [Комментарии в коде](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 Способы включения в код описательных комментариев.  
  
 [Ключевые слова как имена элементов в коде](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 Описывает использование квадратных скобок \(`[]`\) для обозначения имен переменных, которые также являются ключевыми словами [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 [Me, My, MyBase и MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 Описывает различные способы обращения к элементам программы [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 [Ограничения в Visual Basic](../../../visual-basic/programming-guide/program-structure/limitations.md)  
 Описание устранения известных ограничений кода в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
## Связанные подразделы  
 [Условные обозначения и соглашения о коде](../../../visual-basic/language-reference/typographic-and-code-conventions.md)  
 Предоставляет стандартные соглашения кода для [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 [Создание кода](/visual-studio/ide/writing-code-in-the-code-and-text-editor)  
 Описание функций, облегчающих написание кода и управление им.