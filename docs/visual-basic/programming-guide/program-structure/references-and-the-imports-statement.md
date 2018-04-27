---
title: Ссылки и оператор Imports (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 051351c2fa0648de54bbfd36b1630ec1cd49d6f0
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="references-and-the-imports-statement-visual-basic"></a>Ссылки и оператор Imports (Visual Basic)
Вы внешние объекты можно сделать доступными для проекта, выбрав **добавить ссылку** на **проекта** меню. Ссылки в Visual Basic могут указывать на сборки, которые подобны библиотеки типов, но содержат больше сведений.  
  
## <a name="the-imports-statement"></a>Оператор Imports  
 Сборки содержат один или несколько пространств имен. При добавлении ссылки на сборку, можно также добавить `Imports` инструкции к модулю, управляющее видимостью пространств имен этой сборки в модуле. `Imports` Инструкция предоставляет контекст области видимости, что позволяет использовать только часть пространства имен, необходимую для предоставления уникальной ссылки.  
  
 `Imports` Инструкция имеет следующий синтаксис:  
  
 `Imports` [`|``Aliasname` =] `Namespace`  
  
 `Aliasname` ссылается на короткое имя, которое можно использовать в коде для обозначения импортированного пространства имен. `Namespace` представляет пространство имен, доступное либо через ссылку на проект, через определение в проекте, или предыдущим `Imports` инструкции.  
  
 Модуль может содержать любое количество `Imports` инструкции. Они должны располагаться после `Option` инструкций, если он имеется, но перед любым другим кодом.  
  
> [!NOTE]
>  Не следует путать ссылки на проекты с `Imports` инструкции или `Declare` инструкции. Ссылки на проекты делают внешние объекты, такие как объекты в сборках, доступные для проектов Visual Basic. `Imports` Инструкция используется для упрощения доступа к ссылкам на проекты, но не предоставляет доступ к этим объектам. `Declare` Оператор используется для объявления ссылки на внешнюю процедуру в библиотеке динамической компоновки (DLL).  
  
## <a name="using-aliases-with-the-imports-statement"></a>Использование псевдонимов с оператором Imports  
 `Imports` Инструкция облегчает доступ к методам классов, устраняя необходимость явно вводить полные имена ссылок. Псевдонимы позволяют присваивать более понятные имена только на одну часть пространства имен. Например, возврат каретки и перевод строки последовательность, которая единый фрагмент текста, который будет отображаться на несколько строк является частью <xref:Microsoft.VisualBasic.ControlChars> модуля в <xref:Microsoft.VisualBasic?displayProperty=nameWithType> пространства имен. Для использования этой константы в программе без псевдонима, потребовалось бы введите следующий код:  
  
 [!code-vb[VbVbalrApplication#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]  
  
 `Imports` операторы всегда должны сразу же после первой строки `Option` инструкции в модуле. В следующем фрагменте кода показано, как импортировать и присваивать псевдоним <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> модуля:  
  
 [!code-vb[VbVbalrApplication#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]  
  
 Будущие ссылки на это пространство имен может быть значительно более краткими:  
  
 [!code-vb[VbVbalrApplication#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]  
  
 Если `Imports` инструкции псевдоним не включен, элементы, определенные в импортированном пространстве имен, которые могут использоваться в модуле без указания полного имени. Если указано имя псевдонима, он должен использоваться как квалификатор имен, содержащихся в этом пространстве имен.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.ControlChars>  
 <xref:Microsoft.VisualBasic>  
   
 [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Практическое руководство. Создание и использование сборок с помощью командной строки](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)  
 [Оператор Imports (пространство имен и тип .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
