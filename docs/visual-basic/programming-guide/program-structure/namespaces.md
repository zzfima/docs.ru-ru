---
title: Пространства имен
ms.date: 07/20/2015
f1_keywords:
- vb.global
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- name collisions
- Global keyword [Visual Basic]
- namespace pollution
- names [Visual Basic], avoiding conflicts
- naming conflicts [Visual Basic], namespaces
- namespaces [Visual Basic], assemblies
- Visual Basic code, namespaces
- fully qualified names [Visual Basic]
- naming conventions [Visual Basic], naming conflicts
- namespaces
ms.assetid: cffac744-ab8c-4f1f-ba50-732c22ab4b88
ms.openlocfilehash: ec892167f30a7ded739dc188ab4096cb3a5d154c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347326"
---
# <a name="namespaces-in-visual-basic"></a>Пространства имен в Visual Basic
Пространства имен упорядочивают объекты, определенные в сборке. Сборки могут содержать несколько пространств имен, которые, в свою очередь, могут содержать другие пространства имен. Пространства имен предотвращают неоднозначность и упрощают ссылки при использовании больших групп объектов, таких как библиотеки классов.  
  
 Например, .NET Framework определяет класс <xref:System.Windows.Forms.ListBox> в пространстве имен <xref:System.Windows.Forms?displayProperty=nameWithType>. В следующем фрагменте кода показано, как объявить переменную, используя полное имя для этого класса:  
  
 [!code-vb[VbVbalrApplication#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#6)]  
  
## <a name="avoiding-name-collisions"></a>Предотвращение конфликтов имен  
 .NET Framework пространства имен устраняют проблему, которая иногда называется *засорением пространства имен*, при которой разработчик библиотеки классов страдает от использования аналогичных имен в другой библиотеке. Такие конфликты с существующими компонентами иногда называют *конфликтами имен*.  
  
 Например, если вы создаете новый класс `ListBox`, то можете использовать его внутри проекта без уточнения. Однако если вы хотите использовать класс .NET Framework <xref:System.Windows.Forms.ListBox> в том же проекте, необходимо использовать полную ссылку, чтобы сделать ссылку уникальной. Если ссылка не является уникальной, Visual Basic выдает ошибку, сообщающую, что имя неоднозначно. В примере кода ниже показано, как объявить эти объекты:  
  
 [!code-vb[VbVbalrApplication#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#7)]  
  
 На следующем рисунке показаны две иерархии пространств имен, содержащие объект с именем `ListBox`:  
  
 ![Снимок экрана, на котором показаны две иерархии пространств имен.](./media/namespaces/visual-basic-namespace-hierarchy.gif)  
  
 По умолчанию каждый исполняемый файл, созданный с помощью Visual Basic, содержит пространство имен с тем же именем, что и у проекта. Например, если вы определяете объект в проекте `ListBoxProject`, то исполняемый файл ListBoxProject.exe содержит пространство имен `ListBoxProject`.  
  
 Несколько сборок могут использовать одно и то же пространство имен. Visual Basic обрабатывает их как единый набор имен. Например, можно определить классы для пространства имен `SomeNameSpace` в сборке `Assemb1`, а также определить дополнительные классы для того же пространства имен из сборки `Assemb2`.  
  
## <a name="fully-qualified-names"></a>полные имена  
 Полные имена — это ссылки на объекты, имеющие префикс в виде имени пространства имен, в котором определен объект. Вы можете использовать объекты, определенные в других проектах, если создадите ссылку на класс (выбрав **Добавить ссылку** в меню **Проект** ) и затем используете полное имя объекта в коде. В следующем фрагменте кода показано, как использовать полное имя объекта из пространства имен другого проекта:  
  
 [!code-vb[VbVbalrApplication#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#8)]  
  
 Полные имена предотвращают возникновение конфликтов имен, так как позволяют компилятору определить, какой именно объект используется. Однако сами эти имена могут получиться длинными и громоздкими. Чтобы обойти эту проблему, можно использовать оператор `Imports` для определения *псевдонима*— сокращенного имени, которое можно применить вместо полного имени. Например, в следующем примере кода создаются псевдонимы для двух полных имен, которые затем используются для определения двух объектов.  
  
 [!code-vb[VbVbalrApplication#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#9)]  
  
 [!code-vb[VbVbalrApplication#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#10)]  
  
 Если вы применяете оператор `Imports` без псевдонима, можно использовать все имена в данном пространстве имен без уточнения при условии, что они являются уникальными в данном проекте. Если проект содержит операторы `Imports` для пространств имен, где есть элементы с одинаковым именем, необходимо полностью уточнять это имя. Предположим, что проект содержал два следующих оператора `Imports` :  
  
 [!code-vb[VbVbalrApplication#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#11)]  
  
 При попытке использовать `Class1` без полного уточнения, Visual Basic выдает сообщение об ошибке, сообщающее, что имя `Class1` неоднозначно.  
  
## <a name="namespace-level-statements"></a>Операторы уровня пространства имен  
 В пространстве имен можно определить такие элементы, как модули, интерфейсы, классы, делегаты, перечисления, структуры и другие пространства имен. Вы не можете определить такие элементы, как свойства, процедуры, переменные и события, на уровне пространства имен. Их следует объявить внутри контейнеров, таких как модули, структуры или классы.  
  
## <a name="global-keyword-in-fully-qualified-names"></a>Ключевое слово Global в полных именах  
 Если вы определили вложенную иерархию пространств имен, доступ кода внутри этой иерархии к пространству имен <xref:System?displayProperty=nameWithType> платформы .NET Framework может быть заблокирован. В следующем примере показана иерархия, где пространство имен `SpecialSpace.System` блокирует доступ к <xref:System?displayProperty=nameWithType>.  
  
```vb  
Namespace SpecialSpace  
    Namespace System  
        Class abc  
            Function getValue() As System.Int32  
                Dim n As System.Int32  
                Return n  
            End Function  
        End Class  
    End Namespace  
End Namespace  
```  
  
 В результате компилятору Visual Basic не удается разрешить успешно ссылку в <xref:System.Int32?displayProperty=nameWithType>, так как `SpecialSpace.System` не определяет `Int32`. Можно использовать ключевое слово `Global` для запуска цепочки квалификации на самом внешнем уровне библиотеки классов .NET Framework. Это позволяет указать пространство имен <xref:System?displayProperty=nameWithType> или любое другое пространство имен в библиотеке классов. Это показано в следующем примере.  
  
```vb  
Namespace SpecialSpace  
    Namespace System  
        Class abc  
            Function getValue() As Global.System.Int32  
                Dim n As Global.System.Int32  
                Return n  
            End Function  
        End Class  
    End Namespace  
End Namespace  
```  
  
 Можно использовать `Global` для доступа к другим пространствам имен корневого уровня, таким как <xref:Microsoft.VisualBasic?displayProperty=nameWithType>, и любому пространству имен, сопоставленному с проектом.  
  
## <a name="global-keyword-in-namespace-statements"></a>Ключевое слово Global в операторах пространства имен  
 Можно также использовать ключевое слово `Global` в [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md). Это позволяет определить пространство имен из корневых пространств имен проекта.  
  
 Все пространства имен в проекте основаны на его корневом пространстве имен.  Visual Studio назначает имя проекта в качестве корневого пространства имен по умолчанию для всего кода в проекте. Например, если проект называется `ConsoleApplication1`, его программные элементы относятся к пространству имен `ConsoleApplication1`. При объявлении `Namespace Magnetosphere`ссылки на `Magnetosphere` в проекте будут обращаться к `ConsoleApplication1.Magnetosphere`.  
  
 В следующих примерах используется ключевое слово `Global` для объявления пространства имен из корневого пространства имен для проекта.  
  
 [!code-vb[VbVbalrApplication#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/module1.vb#22)]  
  
 В объявлении пространства имен `Global` не может быть вложенным в другое пространство имен.  
  
 Вы можете использовать [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic) для просмотра и изменения значения **Корневое пространство имен** проекта.  Для новых проектов параметру **Корневое пространство имен** по умолчанию присваивается имя проекта. Чтобы сделать `Global` пространством имен верхнего уровня, можно очистить запись **Корневое пространство имен** , оставив поле пустым. Очистка значения **Корневое пространство имен** избавляет от необходимости использовать ключевое слово `Global` в объявлениях пространств имен.  
  
 Когда оператор `Namespace` объявляет имя, которое также является пространством имен в платформе .NET Framework, пространство имен .NET Framework станет недоступным, если в полном имени не используется ключевое слово `Global` . Для обеспечения доступа к пространству имен .NET Framework без использования ключевого слова `Global` можно включить ключевое слово `Global` в оператор `Namespace` .  
  
 В следующем примере ключевое слово `Global` присутствует в объявлении пространства имен `System.Text` .  
  
 Если ключевое слово `Global` отсутствует в объявлении пространства имен, к <xref:System.Text.StringBuilder> нельзя обратиться без указания `Global.System.Text.StringBuilder`. Если ключевое слово `ConsoleApplication1`не использовалось, для проекта с именем `System.Text` ссылки на `ConsoleApplication1.System.Text` обращаются к `Global` .  
  
 [!code-vb[VbVbalrApplication#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/module1.vb#21)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms?displayProperty=nameWithType>
- [Сборки в .NET](../../../standard/assembly/index.md)
- [Ссылки и оператор Imports](references-and-the-imports-statement.md)
- [Оператор Imports (пространство имен и тип .NET)](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Написание кода в решениях Office](/visualstudio/vsto/writing-code-in-office-solutions)
