---
title: "Ссылки и оператор Imports (Visual Basic) | Документы Microsoft"
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
- assemblies [Visual Basic], namespaces
- references, assembly
- namespaces, assemblies
- referencing assemblies
- Imports statement, referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 283a27e7703b31a9aeed8f7e4104e89b7ff78525
ms.lasthandoff: 03/13/2017

---
# <a name="references-and-the-imports-statement-visual-basic"></a>Ссылки и оператор Imports (Visual Basic)
Вы внешние объекты можно сделать доступными для проекта, выбрав **добавить ссылку** на **проекта** меню. Ссылки в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] могут указывать на сборки, которые подобны библиотекам типов, но содержат больше сведений.  
  
## <a name="the-imports-statement"></a>Оператор Imports  
 Сборки содержат один или несколько пространств имен. При добавлении ссылки на сборку, можно добавить `Imports` инструкции к модулю, управляющему видимостью пространств имен этой сборки в данном модуле. `Imports` Инструкция предоставляет контекст области видимости, что позволяет использовать только часть пространства имен, необходимую для предоставления уникальной ссылки.  
  
 `Imports` Инструкция имеет следующий синтаксис:  
  
 `Imports` [`|``Aliasname` =] `Namespace`  
  
 `Aliasname`ссылается на короткое имя, которое можно использовать в коде для ссылки на импортируемое пространство имен. `Namespace`— Это пространство имен, доступное либо через ссылку на проект, через определение в проекте, либо через предыдущим `Imports` инструкции.  
  
 Модуль может содержать любое количество `Imports` инструкции. Они должны располагаться после `Option` инструкций, если он присутствует, но перед любым другим кодом.  
  
> [!NOTE]
>  Не следует путать ссылки на проекты с `Imports` инструкции или `Declare` инструкции. Ссылки на проекты делают внешние объекты, такие как объекты в сборках, доступные для [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] проектов. `Imports` Инструкция используется для упрощения доступа к ссылкам на проекты, но не предоставляет доступ к этим объектам. `Declare` Инструкция используется для объявления ссылки на внешнюю процедуру в библиотеке динамической компоновки (DLL).  
  
## <a name="using-aliases-with-the-imports-statement"></a>Использование псевдонимов при помощи оператора Imports  
 `Imports` Инструкция облегчает доступ к методам классов, устраняя необходимость явно вводить полные имена ссылок. Псевдонимы позволяют присваивать более понятные имена только одной части пространства имен. Например, возврат каретки и перевод строки последовательность, которая единый фрагмент текста, отображаемого на нескольких строках является частью <xref:Microsoft.VisualBasic.ControlChars>модуля в <xref:Microsoft.VisualBasic?displayProperty=fullName>имен.</xref:Microsoft.VisualBasic?displayProperty=fullName> </xref:Microsoft.VisualBasic.ControlChars> Для использования этой константы в программе без псевдонима, потребовалось бы введите следующий код:  
  
 [!code-vb[VbVbalrApplication&#3;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]  
  
 `Imports`инструкции должны всегда быть сразу же после первой строки `Option` инструкции в модуле. В следующем фрагменте кода показано, как импортировать и присваивать псевдоним <xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName>модуля:</xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName>  
  
 [!code-vb[VbVbalrApplication&#4;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]  
  
 Будущие ссылки на это пространство имен может быть значительно более краткими:  
  
 [!code-vb[VbVbalrApplication&#5;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]  
  
 Если `Imports` инструкции псевдоним не включен, элементы, определенные в импортированном пространстве имен, которые могут использоваться в модуле без указания полного имени. Если указано имя псевдонима, он должен использоваться как квалификатор имен, содержащихся в этом пространстве имен.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.ControlChars></xref:Microsoft.VisualBasic.ControlChars>   
 <xref:Microsoft.VisualBasic></xref:Microsoft.VisualBasic>   
 [NIB. Практическое руководство. Добавление и удаление ссылок с помощью диалогового окна "Добавление ссылки"](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Практическое руководство: Создание и использование сборок с помощью командной строки](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)   
 [Оператор Imports (пространство имен и тип .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
