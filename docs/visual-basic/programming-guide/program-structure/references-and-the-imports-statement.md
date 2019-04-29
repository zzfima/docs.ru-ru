---
title: Ссылки и оператор Imports (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: f3396eb3e758dc456d86de80246de24349680f2e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967756"
---
# <a name="references-and-the-imports-statement-visual-basic"></a>Ссылки и оператор Imports (Visual Basic)
Вы внешние объекты можно сделать доступными в проект, выбрав **добавить ссылку** команды **проекта** меню. Ссылки в Visual Basic могут указывать на сборки, которые подобны библиотек типов, но содержат больше сведений.  
  
## <a name="the-imports-statement"></a>Оператор Imports  
 Сборки содержат один или несколько пространств имен. При добавлении ссылки на сборку, можно также добавить `Imports` инструкции модулю, который управляет видимостью пространств имен в модуль этой сборки. `Imports` Инструкция предоставляет контекст области видимости, которая позволяет использовать только часть пространства имен, необходимые для предоставления уникальной ссылки.  
  
 `Imports` Инструкция имеет следующий синтаксис:  
  
 `Imports [Aliasname =] Namespace`  
  
 `Aliasname` ссылается на короткое имя, которое можно использовать в коде для ссылки на импортированное пространство имен. `Namespace` — Это пространство имен, доступное через ссылку на проект, через определение в проект, или с помощью предыдущего `Imports` инструкции.  
  
 Модуль может содержать любое количество `Imports` инструкций. Они должны располагаться после `Option` инструкций, если он присутствует, но перед любым другим кодом.  
  
> [!NOTE]
>  Не следует путать ссылки на проекты с `Imports` инструкции или `Declare` инструкции. Ссылки на проекты делают внешние объекты, такие как объекты в сборках, доступные для проектов Visual Basic. `Imports` Инструкция используется для упрощения доступа перекрестные ссылки между проектами, но не предоставляет доступ к этим объектам. `Declare` Оператор используется для объявления ссылки на внешнюю процедуру в библиотеке динамической компоновки (DLL).  
  
## <a name="using-aliases-with-the-imports-statement"></a>Использование псевдонимов с оператор Imports  
 `Imports` Инструкции облегчает доступ к методам классов, устраняя необходимость явно вводить полные имена ссылок. Псевдонимы позволяют назначить более понятные имена только на одну часть пространства имен. Например, возврат каретки и перевод строки последовательность, которая вызывает одну часть текста, отображаемого на нескольких строках является частью <xref:Microsoft.VisualBasic.ControlChars> модуля в <xref:Microsoft.VisualBasic?displayProperty=nameWithType> пространства имен. Для использования этой константы в программе без псевдонима, потребовалось бы введите следующий код:  
  
 [!code-vb[VbVbalrApplication#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#3)]  
  
 `Imports` операторы всегда должны сразу же после первых строк `Option` инструкции в модуле. В следующем фрагменте кода показано, как импортировать и присваивать псевдоним <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> модуля:  
  
 [!code-vb[VbVbalrApplication#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#4)]  
  
 Будущие ссылки на это пространство имен может быть значительно меньше:  
  
 [!code-vb[VbVbalrApplication#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#5)]  
  
 Если `Imports` инструкция не включает имя псевдонима, элементы, определенные в импортированном пространстве имен, которые могут использоваться в модуле без указания полного имени. Если указано имя псевдонима, он должен использоваться как квалификатор для имен, содержащихся в этом пространстве имен.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [Сборки в .NET](../../../standard/assembly/index.md)
- [Практическое руководство. Создание и использование сборок с помощью командной строки](../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md)
- [Оператор Imports (пространство имен и тип .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
