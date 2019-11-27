---
title: Ссылки и оператор Imports
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: 31b4fe001f2b8a62ac30488053c57cd186020421
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347280"
---
# <a name="references-and-the-imports-statement-visual-basic"></a>Ссылки и оператор Imports (Visual Basic)
Можно сделать внешние объекты доступными для проекта, выбрав команду **Добавить ссылку** в меню **проект** . Ссылки в Visual Basic могут указывать на сборки, которые подобны библиотекам типов, но содержат дополнительные сведения.  
  
## <a name="the-imports-statement"></a>Оператор Imports  
 Сборки включают одно или несколько пространств имен. При добавлении ссылки на сборку можно также добавить в модуль инструкцию `Imports`, которая управляет видимостью пространств имен этой сборки в модуле. Оператор `Imports` предоставляет контекст области, который позволяет использовать только часть пространства имен, необходимую для предоставления уникальной ссылки.  
  
 Оператор `Imports` имеет следующий синтаксис:  
  
 `Imports [Aliasname =] Namespace`  
  
 `Aliasname` ссылается на короткое имя, которое можно использовать в коде для ссылки на импортированное пространство имен. `Namespace` — это пространство имен, доступное через ссылку на проект, через определение в проекте или с помощью предыдущей инструкции `Imports`.  
  
 Модуль может содержать любое количество инструкций `Imports`. Они должны располагаться после любых операторов `Option`, если они есть, но перед любым другим кодом.  
  
> [!NOTE]
> Не путайте ссылки на проект с оператором `Imports` или `Declare`. Ссылки проекта делают внешние объекты, такие как объекты в сборках, доступными для Visual Basic проектов. Оператор `Imports` используется для упрощения доступа к ссылкам на проекты, но не предоставляет доступ к этим объектам. Оператор `Declare` используется для объявления ссылки на внешнюю процедуру в библиотеке динамической компоновки (DLL).  
  
## <a name="using-aliases-with-the-imports-statement"></a>Использование псевдонимов с оператором Imports  
 Оператор `Imports` упрощает доступ к методам классов, устраняя необходимость явно вводить полные имена ссылок. Псевдонимы позволяют назначить более дружественное имя только одной части пространства имен. Например, последовательность возврата каретки/перевода строки, которая приводит к отображению одного фрагмента текста на нескольких строках, является частью модуля <xref:Microsoft.VisualBasic.ControlChars> в пространстве имен <xref:Microsoft.VisualBasic?displayProperty=nameWithType>. Чтобы использовать эту константу в программе без псевдонима, необходимо ввести следующий код:  
  
 [!code-vb[VbVbalrApplication#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#3)]  
  
 `Imports` операторы всегда должны быть первыми строками, непосредственно следующими за инструкциями `Option` в модуле. В следующем фрагменте кода показано, как импортировать и назначить псевдоним модулю <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType>:  
  
 [!code-vb[VbVbalrApplication#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#4)]  
  
 Дальнейшие ссылки на это пространство имен могут быть значительно короче:  
  
 [!code-vb[VbVbalrApplication#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#5)]  
  
 Если инструкция `Imports` не включает имя псевдонима, элементы, определенные в импортированном пространстве имен, могут использоваться в модуле без уточнения. Если имя псевдонима указано, оно должно использоваться в качестве квалификатора для имен, содержащихся в этом пространстве имен.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [Пространства имен в Visual Basic](namespaces.md)
- [Сборки в .NET](../../../standard/assembly/index.md)
- [Оператор Imports (пространство имен и тип .NET)](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
