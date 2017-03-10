---
title: "Ссылки и оператор Imports (Visual Basic) | Microsoft Docs"
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
  - "сборки [Visual Basic], пространства имен"
  - "сборки [Visual Basic], ссылки"
  - "оператор Imports, ссылки на сборки"
  - "пространства имен, сборки"
  - "ссылки, сборка"
  - "ссылки на сборки"
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Ссылки и оператор Imports (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Внешние объекты можно сделать доступными для проекта, выбрав в меню **Проект** команду **Добавить ссылку**.  Ссылки в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] могут указывать на сборки, которые подобны библиотекам типов, но содержат больше сведений.  
  
## Оператор Imports  
 Сборки включают одно или несколько пространств имен.  Когда добавляется ссылка к сборке, можно также добавить оператор `Imports` к модулю, управляющему видимостью пространств имен этой сборки в данном модуле.  Оператор `Imports` определяет контекст области видимости, что позволяет использовать только часть пространства имен, необходимую для предоставления уникальной ссылки.  
  
 Оператор `Imports` имеет следующий синтаксис:  
  
 `Imports` \[         `|` `Aliasname` \=\] `Namespace`  
  
 `Aliasname` — это короткое имя, которое можно использовать в коде для обозначения импортированного пространства имен.  `Namespace` — это пространство имен, доступное либо через ссылку в проекте, либо через определение в проекте, либо с помощью предшествующей инструкции `Imports`.  
  
 Модуль может содержать любое количество операторов `Imports`.  Они должны располагаться после операторов `Option`, если таковые присутствуют, но перед любым другим кодом.  
  
> [!NOTE]
>  Не следует путать ссылки на проекты с оператором `Imports` или `Declare`.  Ссылки на проекты делают внешние объекты, такие как объекты в сборках, доступные для проектов [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  Оператор `Imports` используется для упрощения доступа к ссылкам на проекты, однако он не обеспечивает доступа к этим объектам.  Оператор `Declare` применяется для объявления ссылки на внешнюю процедуру в библиотеке DLL.  
  
## Использование псевдонимов при помощи оператора Imports  
 Оператор `Imports` облегчает доступ к методам классов, устраняя необходимость явно вводить полные проверенные имена ссылок.  Псевдонимы позволяют присваивать более понятные имена только одной части пространства имен.  Например, последовательность возврат каретки \/ перевод строки, в результате которой один фрагмент текста отображается в нескольких строках, является частью модуля <xref:Microsoft.VisualBasic.ControlChars> пространства имен <xref:Microsoft.VisualBasic?displayProperty=fullName>.  Использование этой константы в программе без псевдонима потребовало бы написания следующего кода:  
  
 [!code-vb[VbVbalrApplication#3](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/references-and-the-impor_1.vb)]  
  
 Операторы `Imports` должны всегда располагаться в первых строках модуля сразу же после операторов `Option`.   В следующем фрагменте кода показано, как импортировать и присваивать псевдоним модулю <xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName>:  
  
 [!code-vb[VbVbalrApplication#4](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/references-and-the-impor_2.vb)]  
  
 Дальнейшие ссылки на это пространство имен могут быть значительно более краткими:  
  
 [!code-vb[VbVbalrApplication#5](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/references-and-the-impor_3.vb)]  
  
 Если в оператор `Imports` псевдоним не включен, то элементы, определенные в импортированном пространстве имен, могут использоваться в модуле без указания полного имени.  Если псевдоним назначен, он должен использоваться в качестве квалификатора имен, содержащихся в данном пространстве имен.  
  
## См. также  
 <xref:Microsoft.VisualBasic.ControlChars>   
 <xref:Microsoft.VisualBasic>   
 [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/ru-ru/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Сборки и глобальный кэш сборок](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Практическое руководство. Создание и использование сборок с помощью командной строки](../Topic/How%20to:%20Create%20and%20Use%20Assemblies%20Using%20the%20Command%20Line%20\(C%23%20and%20Visual%20Basic\).md)   
 [Оператор Imports \(пространство имен .NET и тип\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)