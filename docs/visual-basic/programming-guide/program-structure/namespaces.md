---
title: "Пространства имен в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.global"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "сборки [Visual Basic], пространства имен"
  - "конфликты имен"
  - "Global - ключевое слово [Visual Basic]"
  - "загрязнение пространства имен"
  - "имена, предотвращение конфликтов"
  - "конфликты имен, пространства имен"
  - "пространства имен, сборки"
  - "код Visual Basic, пространства имен"
  - "полные имена"
  - "соглашения об именовании, конфликты имен"
  - "пространства имен"
ms.assetid: cffac744-ab8c-4f1f-ba50-732c22ab4b88
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# Пространства имен в Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Пространства имен упорядочивают объекты, определенные в сборке. Сборки могут содержать несколько пространств имен, которые, в свою очередь, могут содержать другие пространства имен. Пространства имен предотвращают неоднозначность и упрощают ссылки при использовании больших групп объектов, таких как библиотеки классов.  
  
 Например, [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] определяет класс <xref:System.Windows.Forms.ListBox> в пространстве имен <xref:System.Windows.Forms?displayProperty=fullName>. В следующем фрагменте кода показано, как объявить переменную, используя полное имя для этого класса:  
  
 [!code-vb[VbVbalrApplication#6](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/namespaces_1.vb)]  
  
## Предотвращение конфликтов имен  
 Пространства имен [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] помогают решить проблему, которую иногда называют *загрязнением пространства имен*, при которой у разработчика библиотеки классов возникают трудности, связанные с использованием аналогичных имен в другой библиотеке. Такие конфликты с существующими компонентами иногда называют *конфликтами имен*.  
  
 Например, если вы создаете новый класс `ListBox`, то можете использовать его внутри проекта без уточнения. Однако если вы захотите использовать в том же проекте класс <xref:System.Windows.Forms.ListBox> [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)], потребуется использовать полную ссылку, чтобы сделать ссылку уникальной. Если эта ссылка не является уникальной, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] выдает сообщение об ошибке, уведомляющее о неоднозначности имени. В примере кода ниже показано, как объявить эти объекты:  
  
 [!code-vb[VbVbalrApplication#7](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/namespaces_2.vb)]  
  
 На следующем рисунке показаны две иерархии пространств имен, в каждой из которых присутствует объект `ListBox`.  
  
 ![Иерархия пространства имен](../../../visual-basic/programming-guide/program-structure/media/vanamespacehierarchy.png "vaNamespaceHierarchy")  
  
 По умолчанию каждый исполняемый файл, созданный с помощью [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], содержит пространство имен с таким же именем, как и у проекта. Например, если вы определяете объект в проекте `ListBoxProject`, то исполняемый файл ListBoxProject.exe содержит пространство имен `ListBoxProject`.  
  
 Несколько сборок могут использовать одно и то же пространство имен.[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] обрабатывает их как единый набор имен. Например, можно определить классы для пространства имен `SomeNameSpace` в сборке `Assemb1`, а также определить дополнительные классы для того же пространства имен из сборки `Assemb2`.  
  
## Полные имена  
 Полные имена — это ссылки на объекты, имеющие префикс в виде имени пространства имен, в котором определен объект. Вы можете использовать объекты, определенные в других проектах, если создадите ссылку на класс \(выбрав **Добавить ссылку** в меню **Проект**\) и затем используете полное имя объекта в коде. В следующем фрагменте кода показано, как использовать полное имя объекта из пространства имен другого проекта:  
  
 [!code-vb[VbVbalrApplication#8](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/namespaces_3.vb)]  
  
 Полные имена предотвращают возникновение конфликтов имен, так как позволяют компилятору определить, какой именно объект используется. Однако сами эти имена могут получиться длинными и громоздкими. Чтобы обойти эту проблему, можно использовать оператор `Imports` для определения *псевдонима* — сокращенного имени, которое можно применить вместо полного имени. Например, в следующем примере кода создаются псевдонимы для двух полных имен, которые затем используются для определения двух объектов.  
  
 [!code-vb[VbVbalrApplication#9](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/namespaces_4.vb)]  
  
 [!code-vb[VbVbalrApplication#10](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/namespaces_5.vb)]  
  
 Если вы применяете оператор `Imports` без псевдонима, можно использовать все имена в данном пространстве имен без уточнения при условии, что они являются уникальными в данном проекте. Если проект содержит операторы `Imports` для пространств имен, где есть элементы с одинаковым именем, необходимо полностью уточнять это имя. Предположим, что проект содержал два следующих оператора `Imports`:  
  
 [!code-vb[VbVbalrApplication#11](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/namespaces_6.vb)]  
  
 При попытке использовать `Class1` без полного уточнения [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] выдает сообщение об ошибке, указывающее, что имя `Class1` является неоднозначным.  
  
## Операторы уровня пространства имен  
 В пространстве имен можно определить такие элементы, как модули, интерфейсы, классы, делегаты, перечисления, структуры и другие пространства имен. Вы не можете определить такие элементы, как свойства, процедуры, переменные и события, на уровне пространства имен. Их следует объявить внутри контейнеров, таких как модули, структуры или классы.  
  
## Ключевое слово Global в полных именах  
 Если вы определили вложенную иерархию пространств имен, доступ кода внутри этой иерархии к пространству имен <xref:System?displayProperty=fullName> платформы .NET Framework может быть заблокирован. В следующем примере показана иерархия, где пространство имен `SpecialSpace.System` блокирует доступ к <xref:System?displayProperty=fullName>.  
  
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
  
 В результате компилятору Visual Basic не удается разрешить успешно ссылку в <xref:System.Int32?displayProperty=fullName>, так как `SpecialSpace.System` не определяет `Int32`. Можно использовать ключевое слово `Global` для запуска цепочки квалификации на самом внешнем уровне библиотеки классов .NET Framework. Это позволяет указать пространство имен <xref:System?displayProperty=fullName> или любое другое пространство имен в библиотеке классов. Это показано в следующем примере.  
  
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
  
 Можно использовать `Global` для доступа к другим пространствам имен корневого уровня, таким как <xref:Microsoft.VisualBasic?displayProperty=fullName>, и любому пространству имен, сопоставленному с проектом.  
  
## Ключевое слово Global в операторах пространства имен  
 Можно также использовать ключевое слово `Global` в [Оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md). Это позволяет определить пространство имен из корневых пространств имен проекта.  
  
 Все пространства имен в проекте основаны на его корневом пространстве имен.  Visual Studio назначает имя проекта в качестве корневого пространства имен по умолчанию для всего кода в проекте. Например, если проект называется `ConsoleApplication1`, его программные элементы относятся к пространству имен `ConsoleApplication1`. При объявлении `Namespace Magnetosphere` ссылки на `Magnetosphere` в проекте будут обращаться к `ConsoleApplication1.Magnetosphere`.  
  
 В следующих примерах используется ключевое слово `Global` для объявления пространства имен из корневого пространства имен для проекта.  
  
 [!code-vb[VbVbalrApplication#22](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/namespaces_7.vb)]  
  
 В объявлении пространства имен `Global` не может быть вложенным в другое пространство имен.  
  
 Вы можете использовать [Страница «Приложение» в конструкторе проектов \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic) для просмотра и изменения значения **Корневое пространство имен** проекта.  Для новых проектов параметру **Корневое пространство имен** по умолчанию присваивается имя проекта. Чтобы сделать `Global` пространством имен верхнего уровня, можно очистить запись **Корневое пространство имен**, оставив поле пустым. Очистка значения **Корневое пространство имен** избавляет от необходимости использовать ключевое слово `Global` в объявлениях пространств имен.  
  
 Когда оператор `Namespace` объявляет имя, которое также является пространством имен в платформе .NET Framework, пространство имен .NET Framework станет недоступным, если в полном имени не используется ключевое слово `Global`. Для обеспечения доступа к пространству имен .NET Framework без использования ключевого слова `Global` можно включить ключевое слово `Global` в оператор `Namespace`.  
  
 В следующем примере ключевое слово `Global` присутствует в объявлении пространства имен `System.Text`.  
  
 Если ключевое слово `Global` отсутствует в объявлении пространства имен, к <xref:System.Text.StringBuilder> нельзя обратиться без указания `Global.System.Text.StringBuilder`. Если ключевое слово `Global` не использовалось, для проекта с именем `ConsoleApplication1` ссылки на `System.Text` обращаются к `ConsoleApplication1.System.Text`.  
  
 [!code-vb[VbVbalrApplication#21](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/namespaces_8.vb)]  
  
## См. также  
 <xref:System.Windows.Forms.ListBox>   
 <xref:System.Windows.Forms?displayProperty=fullName>   
 [Сборки и глобальный кэш сборок](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Практическое руководство. Создание и использование сборок с помощью командной строки](../Topic/How%20to:%20Create%20and%20Use%20Assemblies%20Using%20the%20Command%20Line%20\(C%23%20and%20Visual%20Basic\).md)   
 [Ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Оператор Imports \(пространство имен .NET и тип\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Написание кода в решениях Office](/office-dev/office-dev/writing-code-in-office-solutions)