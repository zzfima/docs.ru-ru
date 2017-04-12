---
title: "Пространства имен в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.global
dev_langs:
- VB
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- name collisions
- Global keyword [Visual Basic]
- namespace pollution
- names, avoiding conflicts
- naming conflicts, namespaces
- namespaces, assemblies
- Visual Basic code, namespaces
- fully qualified names
- naming conventions, naming conflicts
- namespaces
ms.assetid: cffac744-ab8c-4f1f-ba50-732c22ab4b88
caps.latest.revision: 27
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
ms.openlocfilehash: fe94e65ddbb4ebd2f7d26e8750a0a7ef5d3153af
ms.lasthandoff: 03/13/2017

---
# <a name="namespaces-in-visual-basic"></a>Пространства имен в Visual Basic
Пространства имен упорядочивают объекты, определенные в сборке. Сборки могут содержать несколько пространств имен, которые, в свою очередь, могут содержать другие пространства имен. Пространства имен предотвращают неоднозначность и упрощают ссылки при использовании больших групп объектов, таких как библиотеки классов.  
  
 Например [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] определяет <xref:System.Windows.Forms.ListBox>класса в <xref:System.Windows.Forms?displayProperty=fullName>имен.</xref:System.Windows.Forms?displayProperty=fullName> </xref:System.Windows.Forms.ListBox> В следующем фрагменте кода показано, как объявить переменную, используя полное имя для этого класса:  
  
 [!code-vb[VbVbalrApplication №&6;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_1.vb)]  
  
## <a name="avoiding-name-collisions"></a>Предотвращение конфликтов имен  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]пространства имен разрешают проблему, иногда называемую *загрязнение пространства имен*, в котором разработчик библиотеки классов возникают проблемы с использованием одинаковых имен в разных библиотеках. Такие конфликты с существующими компонентами иногда называют *конфликтами имен*.  
  
 Например, если вы создаете новый класс `ListBox`, то можете использовать его внутри проекта без уточнения. Тем не менее если вы хотите использовать [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.Windows.Forms.ListBox>класс в том же проекте, необходимо использовать полную ссылку должна быть уникальной ссылки.</xref:System.Windows.Forms.ListBox> Если эта ссылка не является уникальной, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] выдает сообщение об ошибке, уведомляющее о неоднозначности имени. В примере кода ниже показано, как объявить эти объекты:  
  
 [!code-vb[VbVbalrApplication&#7;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_2.vb)]  
  
 На следующем рисунке показаны две иерархии пространств имен, в каждой из которых присутствует объект `ListBox`.  
  
 ![Иерархия пространства имен](../../../visual-basic/programming-guide/program-structure/media/vanamespacehierarchy.gif "vaNamespaceHierarchy")  
  
 По умолчанию каждый исполняемый файл, созданный с помощью [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], содержит пространство имен с таким же именем, как и у проекта. Например, если вы определяете объект в проекте `ListBoxProject`, то исполняемый файл ListBoxProject.exe содержит пространство имен `ListBoxProject`.  
  
 Несколько сборок могут использовать одно и то же пространство имен. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] обрабатывает их как единый набор имен. Например, можно определить классы для пространства имен `SomeNameSpace` в сборке `Assemb1`, а также определить дополнительные классы для того же пространства имен из сборки `Assemb2`.  
  
## <a name="fully-qualified-names"></a>Полные имена  
 Полные имена — это ссылки на объекты, имеющие префикс в виде имени пространства имен, в котором определен объект. Вы можете использовать объекты, определенные в других проектах, если создадите ссылку на класс (выбрав **Добавить ссылку** в меню **Проект** ) и затем используете полное имя объекта в коде. В следующем фрагменте кода показано, как использовать полное имя объекта из пространства имен другого проекта:  
  
 [!code-vb[VbVbalrApplication №&8;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_3.vb)]  
  
 Полные имена предотвращают возникновение конфликтов имен, так как позволяют компилятору определить, какой именно объект используется. Однако сами эти имена могут получиться длинными и громоздкими. Чтобы обойти эту проблему, можно использовать оператор `Imports` для определения *псевдонима*— сокращенного имени, которое можно применить вместо полного имени. Например, в следующем примере кода создаются псевдонимы для двух полных имен, которые затем используются для определения двух объектов.  
  
 [!code-vb[VbVbalrApplication №&9;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_4.vb)]  
  
 [!code-vb[VbVbalrApplication&#10;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_5.vb)]  
  
 Если вы применяете оператор `Imports` без псевдонима, можно использовать все имена в данном пространстве имен без уточнения при условии, что они являются уникальными в данном проекте. Если проект содержит операторы `Imports` для пространств имен, где есть элементы с одинаковым именем, необходимо полностью уточнять это имя. Предположим, что проект содержал два следующих оператора `Imports` :  
  
 [!code-vb[VbVbalrApplication&11;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_6.vb)]  
  
 При попытке использовать `Class1` без полного уточнения [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] выдает сообщение об ошибке, указывающее, что имя `Class1` является неоднозначным.  
  
## <a name="namespace-level-statements"></a>Операторы уровня пространства имен  
 В пространстве имен можно определить такие элементы, как модули, интерфейсы, классы, делегаты, перечисления, структуры и другие пространства имен. Вы не можете определить такие элементы, как свойства, процедуры, переменные и события, на уровне пространства имен. Их следует объявить внутри контейнеров, таких как модули, структуры или классы.  
  
## <a name="global-keyword-in-fully-qualified-names"></a>Ключевое слово Global в полных именах  
 Если определены вложенная иерархия пространств имен, код внутри этой иерархии может заблокировать доступ к <xref:System?displayProperty=fullName>пространства имен платформы .NET Framework.</xref:System?displayProperty=fullName> В следующем примере демонстрируется иерархия, в которой `SpecialSpace.System` имен блокирует доступ к <xref:System?displayProperty=fullName>.</xref:System?displayProperty=fullName>  
  
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
  
 В результате компилятор Visual Basic не удается разрешить успешно ссылку на <xref:System.Int32?displayProperty=fullName>, так как `SpecialSpace.System` не определяет `Int32`.</xref:System.Int32?displayProperty=fullName> Можно использовать ключевое слово `Global` для запуска цепочки квалификации на самом внешнем уровне библиотеки классов .NET Framework. Это позволяет указать <xref:System?displayProperty=fullName>пространства имен или любое другое пространство имен в библиотеке классов.</xref:System?displayProperty=fullName> Это показано в следующем примере.  
  
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
  
 Можно использовать `Global` для доступа к других пространств имен корневого уровня, такие как <xref:Microsoft.VisualBasic?displayProperty=fullName>и любое пространство имен, связанных с проектом.</xref:Microsoft.VisualBasic?displayProperty=fullName>  
  
## <a name="global-keyword-in-namespace-statements"></a>Ключевое слово Global в операторах пространства имен  
 Можно также использовать `Global` ключевое слово в [оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md). Это позволяет определить пространство имен из корневых пространств имен проекта.  
  
 Все пространства имен в проекте основаны на его корневом пространстве имен.  Visual Studio назначает имя проекта в качестве корневого пространства имен по умолчанию для всего кода в проекте. Например, если проект называется `ConsoleApplication1`, его программные элементы относятся к пространству имен `ConsoleApplication1`. При объявлении `Namespace Magnetosphere`ссылки на `Magnetosphere` в проекте будут обращаться к `ConsoleApplication1.Magnetosphere`.  
  
 В следующих примерах используется ключевое слово `Global` для объявления пространства имен из корневого пространства имен для проекта.  
  
 [!code-vb[VbVbalrApplication&#22;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_7.vb)]  
  
 В объявлении пространства имен `Global` не может быть вложенным в другое пространство имен.  
  
 Можно использовать [страница "приложение" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic) для просмотра и изменения **корневое пространство имен** проекта.  Для новых проектов параметру **Корневое пространство имен** по умолчанию присваивается имя проекта. Чтобы сделать `Global` пространством имен верхнего уровня, можно очистить запись **Корневое пространство имен** , оставив поле пустым. Очистка значения **Корневое пространство имен** избавляет от необходимости использовать ключевое слово `Global` в объявлениях пространств имен.  
  
 Когда оператор `Namespace` объявляет имя, которое также является пространством имен в платформе .NET Framework, пространство имен .NET Framework станет недоступным, если в полном имени не используется ключевое слово `Global` . Для обеспечения доступа к пространству имен .NET Framework без использования ключевого слова `Global` можно включить ключевое слово `Global` в оператор `Namespace` .  
  
 В следующем примере ключевое слово `Global` присутствует в объявлении пространства имен `System.Text` .  
  
 Если `Global` ключевое слово не найден в объявление пространства имен <xref:System.Text.StringBuilder>не может осуществляться без указания `Global.System.Text.StringBuilder`.</xref:System.Text.StringBuilder> Если ключевое слово `ConsoleApplication1`не использовалось, для проекта с именем `System.Text` ссылки на `ConsoleApplication1.System.Text` обращаются к `Global` .  
  
 [!code-vb[VbVbalrApplication&#21;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_8.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ListBox></xref:System.Windows.Forms.ListBox>   
 <xref:System.Windows.Forms?displayProperty=fullName></xref:System.Windows.Forms?displayProperty=fullName>   
 [Сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Практическое руководство: Создание и использование сборок с помощью командной строки](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)   
 [Ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Оператор Imports (пространство имен .NET и тип)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Написание кода в решениях Office](https://msdn.microsoft.com/library/bb608596)
