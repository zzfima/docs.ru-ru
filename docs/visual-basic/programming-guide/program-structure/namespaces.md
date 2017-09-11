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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: bfc9f8f71b5ce5e05b6509ad490354663f894651
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="namespaces-in-visual-basic"></a><span data-ttu-id="a949d-102">Пространства имен в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a949d-102">Namespaces in Visual Basic</span></span>
<span data-ttu-id="a949d-103">Пространства имен упорядочивают объекты, определенные в сборке.</span><span class="sxs-lookup"><span data-stu-id="a949d-103">Namespaces organize the objects defined in an assembly.</span></span> <span data-ttu-id="a949d-104">Сборки могут содержать несколько пространств имен, которые, в свою очередь, могут содержать другие пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a949d-104">Assemblies can contain multiple namespaces, which can in turn contain other namespaces.</span></span> <span data-ttu-id="a949d-105">Пространства имен предотвращают неоднозначность и упрощают ссылки при использовании больших групп объектов, таких как библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="a949d-105">Namespaces prevent ambiguity and simplify references when using large groups of objects such as class libraries.</span></span>  
  
 <span data-ttu-id="a949d-106">Например [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] определяет <xref:System.Windows.Forms.ListBox>класса в <xref:System.Windows.Forms?displayProperty=fullName>имен.</xref:System.Windows.Forms?displayProperty=fullName> </xref:System.Windows.Forms.ListBox></span><span class="sxs-lookup"><span data-stu-id="a949d-106">For example, the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] defines the <xref:System.Windows.Forms.ListBox> class in the <xref:System.Windows.Forms?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="a949d-107">В следующем фрагменте кода показано, как объявить переменную, используя полное имя для этого класса:</span><span class="sxs-lookup"><span data-stu-id="a949d-107">The following code fragment shows how to declare a variable using the fully qualified name for this class:</span></span>  
  
 <span data-ttu-id="a949d-108">[!code-vb[VbVbalrApplication №&6;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a949d-108">[!code-vb[VbVbalrApplication#6](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_1.vb)]</span></span>  
  
## <a name="avoiding-name-collisions"></a><span data-ttu-id="a949d-109">Предотвращение конфликтов имен</span><span class="sxs-lookup"><span data-stu-id="a949d-109">Avoiding Name Collisions</span></span>  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]<span data-ttu-id="a949d-110">пространства имен разрешают проблему, иногда называемую *загрязнение пространства имен*, в котором разработчик библиотеки классов возникают проблемы с использованием одинаковых имен в разных библиотеках.</span><span class="sxs-lookup"><span data-stu-id="a949d-110"> namespaces address a problem sometimes called *namespace pollution*, in which the developer of a class library is hampered by the use of similar names in another library.</span></span> <span data-ttu-id="a949d-111">Такие конфликты с существующими компонентами иногда называют *конфликтами имен*.</span><span class="sxs-lookup"><span data-stu-id="a949d-111">These conflicts with existing components are sometimes called *name collisions*.</span></span>  
  
 <span data-ttu-id="a949d-112">Например, если вы создаете новый класс `ListBox`, то можете использовать его внутри проекта без уточнения.</span><span class="sxs-lookup"><span data-stu-id="a949d-112">For example, if you create a new class named `ListBox`, you can use it inside your project without qualification.</span></span> <span data-ttu-id="a949d-113">Тем не менее если вы хотите использовать [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.Windows.Forms.ListBox>класс в том же проекте, необходимо использовать полную ссылку должна быть уникальной ссылки.</xref:System.Windows.Forms.ListBox></span><span class="sxs-lookup"><span data-stu-id="a949d-113">However, if you want to use the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.Windows.Forms.ListBox> class in the same project, you must use a fully qualified reference to make the reference unique.</span></span> <span data-ttu-id="a949d-114">Если эта ссылка не является уникальной, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] выдает сообщение об ошибке, уведомляющее о неоднозначности имени.</span><span class="sxs-lookup"><span data-stu-id="a949d-114">If the reference is not unique, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] produces an error stating that the name is ambiguous.</span></span> <span data-ttu-id="a949d-115">В примере кода ниже показано, как объявить эти объекты:</span><span class="sxs-lookup"><span data-stu-id="a949d-115">The following code example demonstrates how to declare these objects:</span></span>  
  
 <span data-ttu-id="a949d-116">[!code-vb[VbVbalrApplication&#7;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="a949d-116">[!code-vb[VbVbalrApplication#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_2.vb)]</span></span>  
  
 <span data-ttu-id="a949d-117">На следующем рисунке показаны две иерархии пространств имен, в каждой из которых присутствует объект `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="a949d-117">The following illustration shows two namespace hierarchies, both containing an object named `ListBox`.</span></span>  
  
 <span data-ttu-id="a949d-118">![Иерархия пространства имен](../../../visual-basic/programming-guide/program-structure/media/vanamespacehierarchy.gif "vaNamespaceHierarchy")</span><span class="sxs-lookup"><span data-stu-id="a949d-118">![Namespace Hierarchy](../../../visual-basic/programming-guide/program-structure/media/vanamespacehierarchy.gif "vaNamespaceHierarchy")</span></span>  
  
 <span data-ttu-id="a949d-119">По умолчанию каждый исполняемый файл, созданный с помощью [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], содержит пространство имен с таким же именем, как и у проекта.</span><span class="sxs-lookup"><span data-stu-id="a949d-119">By default, every executable file you create with [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] contains a namespace with the same name as your project.</span></span> <span data-ttu-id="a949d-120">Например, если вы определяете объект в проекте `ListBoxProject`, то исполняемый файл ListBoxProject.exe содержит пространство имен `ListBoxProject`.</span><span class="sxs-lookup"><span data-stu-id="a949d-120">For example, if you define an object within a project named `ListBoxProject`, the executable file ListBoxProject.exe contains a namespace called `ListBoxProject`.</span></span>  
  
 <span data-ttu-id="a949d-121">Несколько сборок могут использовать одно и то же пространство имен.</span><span class="sxs-lookup"><span data-stu-id="a949d-121">Multiple assemblies can use the same namespace.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="a949d-122"> обрабатывает их как единый набор имен.</span><span class="sxs-lookup"><span data-stu-id="a949d-122"> treats them as a single set of names.</span></span> <span data-ttu-id="a949d-123">Например, можно определить классы для пространства имен `SomeNameSpace` в сборке `Assemb1`, а также определить дополнительные классы для того же пространства имен из сборки `Assemb2`.</span><span class="sxs-lookup"><span data-stu-id="a949d-123">For example, you can define classes for a namespace called `SomeNameSpace` in an assembly named `Assemb1`, and define additional classes for the same namespace from an assembly named `Assemb2`.</span></span>  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="a949d-124">Полные имена</span><span class="sxs-lookup"><span data-stu-id="a949d-124">Fully Qualified Names</span></span>  
 <span data-ttu-id="a949d-125">Полные имена — это ссылки на объекты, имеющие префикс в виде имени пространства имен, в котором определен объект.</span><span class="sxs-lookup"><span data-stu-id="a949d-125">Fully qualified names are object references that are prefixed with the name of the namespace in which the object is defined.</span></span> <span data-ttu-id="a949d-126">Вы можете использовать объекты, определенные в других проектах, если создадите ссылку на класс (выбрав **Добавить ссылку** в меню **Проект** ) и затем используете полное имя объекта в коде.</span><span class="sxs-lookup"><span data-stu-id="a949d-126">You can use objects defined in other projects if you create a reference to the class (by choosing **Add Reference** from the **Project** menu) and then use the fully qualified name for the object in your code.</span></span> <span data-ttu-id="a949d-127">В следующем фрагменте кода показано, как использовать полное имя объекта из пространства имен другого проекта:</span><span class="sxs-lookup"><span data-stu-id="a949d-127">The following code fragment shows how to use the fully qualified name for an object from another project's namespace:</span></span>  
  
 <span data-ttu-id="a949d-128">[!code-vb[VbVbalrApplication №&8;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="a949d-128">[!code-vb[VbVbalrApplication#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_3.vb)]</span></span>  
  
 <span data-ttu-id="a949d-129">Полные имена предотвращают возникновение конфликтов имен, так как позволяют компилятору определить, какой именно объект используется.</span><span class="sxs-lookup"><span data-stu-id="a949d-129">Fully qualified names prevent naming conflicts because they make it possible for the compiler to determine which object is being used.</span></span> <span data-ttu-id="a949d-130">Однако сами эти имена могут получиться длинными и громоздкими.</span><span class="sxs-lookup"><span data-stu-id="a949d-130">However, the names themselves can get long and cumbersome.</span></span> <span data-ttu-id="a949d-131">Чтобы обойти эту проблему, можно использовать оператор `Imports` для определения *псевдонима*— сокращенного имени, которое можно применить вместо полного имени.</span><span class="sxs-lookup"><span data-stu-id="a949d-131">To get around this, you can use the `Imports` statement to define an *alias*—an abbreviated name you can use in place of a fully qualified name.</span></span> <span data-ttu-id="a949d-132">Например, в следующем примере кода создаются псевдонимы для двух полных имен, которые затем используются для определения двух объектов.</span><span class="sxs-lookup"><span data-stu-id="a949d-132">For example, the following code example creates aliases for two fully qualified names, and uses these aliases to define two objects.</span></span>  
  
 <span data-ttu-id="a949d-133">[!code-vb[VbVbalrApplication №&9;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="a949d-133">[!code-vb[VbVbalrApplication#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_4.vb)]</span></span>  
  
 <span data-ttu-id="a949d-134">[!code-vb[VbVbalrApplication&#10;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="a949d-134">[!code-vb[VbVbalrApplication#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_5.vb)]</span></span>  
  
 <span data-ttu-id="a949d-135">Если вы применяете оператор `Imports` без псевдонима, можно использовать все имена в данном пространстве имен без уточнения при условии, что они являются уникальными в данном проекте.</span><span class="sxs-lookup"><span data-stu-id="a949d-135">If you use the `Imports` statement without an alias, you can use all the names in that namespace without qualification, provided they are unique to the project.</span></span> <span data-ttu-id="a949d-136">Если проект содержит операторы `Imports` для пространств имен, где есть элементы с одинаковым именем, необходимо полностью уточнять это имя.</span><span class="sxs-lookup"><span data-stu-id="a949d-136">If your project contains `Imports` statements for namespaces that contain items with the same name, you must fully qualify that name when you use it.</span></span> <span data-ttu-id="a949d-137">Предположим, что проект содержал два следующих оператора `Imports` :</span><span class="sxs-lookup"><span data-stu-id="a949d-137">Suppose, for example, your project contained the following two `Imports` statements:</span></span>  
  
 <span data-ttu-id="a949d-138">[!code-vb[VbVbalrApplication&11;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="a949d-138">[!code-vb[VbVbalrApplication#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_6.vb)]</span></span>  
  
 <span data-ttu-id="a949d-139">При попытке использовать `Class1` без полного уточнения [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] выдает сообщение об ошибке, указывающее, что имя `Class1` является неоднозначным.</span><span class="sxs-lookup"><span data-stu-id="a949d-139">If you attempt to use `Class1` without fully qualifying it, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] produces an error stating that the name `Class1` is ambiguous.</span></span>  
  
## <a name="namespace-level-statements"></a><span data-ttu-id="a949d-140">Операторы уровня пространства имен</span><span class="sxs-lookup"><span data-stu-id="a949d-140">Namespace Level Statements</span></span>  
 <span data-ttu-id="a949d-141">В пространстве имен можно определить такие элементы, как модули, интерфейсы, классы, делегаты, перечисления, структуры и другие пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a949d-141">Within a namespace, you can define items such as modules, interfaces, classes, delegates, enumerations, structures, and other namespaces.</span></span> <span data-ttu-id="a949d-142">Вы не можете определить такие элементы, как свойства, процедуры, переменные и события, на уровне пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a949d-142">You cannot define items such as properties, procedures, variables and events at the namespace level.</span></span> <span data-ttu-id="a949d-143">Их следует объявить внутри контейнеров, таких как модули, структуры или классы.</span><span class="sxs-lookup"><span data-stu-id="a949d-143">These items must be declared within containers such as modules, structures, or classes.</span></span>  
  
## <a name="global-keyword-in-fully-qualified-names"></a><span data-ttu-id="a949d-144">Ключевое слово Global в полных именах</span><span class="sxs-lookup"><span data-stu-id="a949d-144">Global Keyword in Fully Qualified Names</span></span>  
 <span data-ttu-id="a949d-145">Если определены вложенная иерархия пространств имен, код внутри этой иерархии может заблокировать доступ к <xref:System?displayProperty=fullName>пространства имен платформы .NET Framework.</xref:System?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a949d-145">If you have defined a nested hierarchy of namespaces, code inside that hierarchy might be blocked from accessing the <xref:System?displayProperty=fullName> namespace of the .NET Framework.</span></span> <span data-ttu-id="a949d-146">В следующем примере демонстрируется иерархия, в которой `SpecialSpace.System` имен блокирует доступ к <xref:System?displayProperty=fullName>.</xref:System?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a949d-146">The following example illustrates a hierarchy in which the `SpecialSpace.System` namespace blocks access to <xref:System?displayProperty=fullName>.</span></span>  
  
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
  
 <span data-ttu-id="a949d-147">В результате компилятор Visual Basic не удается разрешить успешно ссылку на <xref:System.Int32?displayProperty=fullName>, так как `SpecialSpace.System` не определяет `Int32`.</xref:System.Int32?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a949d-147">As a result, the Visual Basic compiler cannot successfully resolve the reference to <xref:System.Int32?displayProperty=fullName>, because `SpecialSpace.System` does not define `Int32`.</span></span> <span data-ttu-id="a949d-148">Можно использовать ключевое слово `Global` для запуска цепочки квалификации на самом внешнем уровне библиотеки классов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a949d-148">You can use the `Global` keyword to start the qualification chain at the outermost level of the .NET Framework class library.</span></span> <span data-ttu-id="a949d-149">Это позволяет указать <xref:System?displayProperty=fullName>пространства имен или любое другое пространство имен в библиотеке классов.</xref:System?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a949d-149">This allows you to specify the <xref:System?displayProperty=fullName> namespace or any other namespace in the class library.</span></span> <span data-ttu-id="a949d-150">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a949d-150">The following example illustrates this.</span></span>  
  
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
  
 <span data-ttu-id="a949d-151">Можно использовать `Global` для доступа к других пространств имен корневого уровня, такие как <xref:Microsoft.VisualBasic?displayProperty=fullName>и любое пространство имен, связанных с проектом.</xref:Microsoft.VisualBasic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a949d-151">You can use `Global` to access other root-level namespaces, such as <xref:Microsoft.VisualBasic?displayProperty=fullName>, and any namespace associated with your project.</span></span>  
  
## <a name="global-keyword-in-namespace-statements"></a><span data-ttu-id="a949d-152">Ключевое слово Global в операторах пространства имен</span><span class="sxs-lookup"><span data-stu-id="a949d-152">Global Keyword in Namespace Statements</span></span>  
 <span data-ttu-id="a949d-153">Можно также использовать `Global` ключевое слово в [оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a949d-153">You can also use the `Global` keyword in a [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md).</span></span> <span data-ttu-id="a949d-154">Это позволяет определить пространство имен из корневых пространств имен проекта.</span><span class="sxs-lookup"><span data-stu-id="a949d-154">This lets you define a namespace out of the root namespace of your project.</span></span>  
  
 <span data-ttu-id="a949d-155">Все пространства имен в проекте основаны на его корневом пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="a949d-155">All namespaces in your project are based on the root namespace for the project.</span></span>  <span data-ttu-id="a949d-156">Visual Studio назначает имя проекта в качестве корневого пространства имен по умолчанию для всего кода в проекте.</span><span class="sxs-lookup"><span data-stu-id="a949d-156">Visual Studio assigns your project name as the default root namespace for all code in your project.</span></span> <span data-ttu-id="a949d-157">Например, если проект называется `ConsoleApplication1`, его программные элементы относятся к пространству имен `ConsoleApplication1`.</span><span class="sxs-lookup"><span data-stu-id="a949d-157">For example, if your project is named `ConsoleApplication1`, its programming elements belong to namespace `ConsoleApplication1`.</span></span> <span data-ttu-id="a949d-158">При объявлении `Namespace Magnetosphere`ссылки на `Magnetosphere` в проекте будут обращаться к `ConsoleApplication1.Magnetosphere`.</span><span class="sxs-lookup"><span data-stu-id="a949d-158">If you declare `Namespace Magnetosphere`, references to `Magnetosphere` in the project will access `ConsoleApplication1.Magnetosphere`.</span></span>  
  
 <span data-ttu-id="a949d-159">В следующих примерах используется ключевое слово `Global` для объявления пространства имен из корневого пространства имен для проекта.</span><span class="sxs-lookup"><span data-stu-id="a949d-159">The following examples use the `Global` keyword to declare a namespace out of the root namespace for the project.</span></span>  
  
 <span data-ttu-id="a949d-160">[!code-vb[VbVbalrApplication&#22;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="a949d-160">[!code-vb[VbVbalrApplication#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_7.vb)]</span></span>  
  
 <span data-ttu-id="a949d-161">В объявлении пространства имен `Global` не может быть вложенным в другое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="a949d-161">In a namespace declaration, `Global` cannot be nested in another namespace.</span></span>  
  
 <span data-ttu-id="a949d-162">Можно использовать [страница "приложение" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic) для просмотра и изменения **корневое пространство имен** проекта.</span><span class="sxs-lookup"><span data-stu-id="a949d-162">You can use the [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic) to view and modify the **Root Namespace** of the project.</span></span>  <span data-ttu-id="a949d-163">Для новых проектов параметру **Корневое пространство имен** по умолчанию присваивается имя проекта.</span><span class="sxs-lookup"><span data-stu-id="a949d-163">For new projects, the **Root Namespace** defaults to the project name.</span></span> <span data-ttu-id="a949d-164">Чтобы сделать `Global` пространством имен верхнего уровня, можно очистить запись **Корневое пространство имен** , оставив поле пустым.</span><span class="sxs-lookup"><span data-stu-id="a949d-164">To cause `Global` to be the top-level namespace, you can clear the **Root Namespace** entry so that the box is empty.</span></span> <span data-ttu-id="a949d-165">Очистка значения **Корневое пространство имен** избавляет от необходимости использовать ключевое слово `Global` в объявлениях пространств имен.</span><span class="sxs-lookup"><span data-stu-id="a949d-165">Clearing **Root Namespace** removes the need for the `Global` keyword in namespace declarations.</span></span>  
  
 <span data-ttu-id="a949d-166">Когда оператор `Namespace` объявляет имя, которое также является пространством имен в платформе .NET Framework, пространство имен .NET Framework станет недоступным, если в полном имени не используется ключевое слово `Global` .</span><span class="sxs-lookup"><span data-stu-id="a949d-166">If a `Namespace` statement declares a name that is also a namespace in the .NET Framework, the .NET Framework namespace becomes unavailable if the `Global` keyword is not used in a fully qualified name.</span></span> <span data-ttu-id="a949d-167">Для обеспечения доступа к пространству имен .NET Framework без использования ключевого слова `Global` можно включить ключевое слово `Global` в оператор `Namespace` .</span><span class="sxs-lookup"><span data-stu-id="a949d-167">To enable access to that .NET Framework namespace without using the `Global` keyword, you can include the `Global` keyword in the `Namespace` statement.</span></span>  
  
 <span data-ttu-id="a949d-168">В следующем примере ключевое слово `Global` присутствует в объявлении пространства имен `System.Text` .</span><span class="sxs-lookup"><span data-stu-id="a949d-168">The following example has the `Global` keyword in the `System.Text` namespace declaration.</span></span>  
  
 <span data-ttu-id="a949d-169">Если `Global` ключевое слово не найден в объявление пространства имен <xref:System.Text.StringBuilder>не может осуществляться без указания `Global.System.Text.StringBuilder`.</xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="a949d-169">If the `Global` keyword was not present in the namespace declaration, <xref:System.Text.StringBuilder> could not be accessed without specifying `Global.System.Text.StringBuilder`.</span></span> <span data-ttu-id="a949d-170">Если ключевое слово `ConsoleApplication1`не использовалось, для проекта с именем `System.Text` ссылки на `ConsoleApplication1.System.Text` обращаются к `Global` .</span><span class="sxs-lookup"><span data-stu-id="a949d-170">For a project named `ConsoleApplication1`, references to `System.Text` would access `ConsoleApplication1.System.Text` if the `Global` keyword was not used.</span></span>  
  
 <span data-ttu-id="a949d-171">[!code-vb[VbVbalrApplication&#21;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="a949d-171">[!code-vb[VbVbalrApplication#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_8.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a949d-172">См. также</span><span class="sxs-lookup"><span data-stu-id="a949d-172">See Also</span></span>  
 <span data-ttu-id="a949d-173"><xref:System.Windows.Forms.ListBox></xref:System.Windows.Forms.ListBox></span><span class="sxs-lookup"><span data-stu-id="a949d-173"><xref:System.Windows.Forms.ListBox></span></span>   
 <span data-ttu-id="a949d-174"><xref:System.Windows.Forms?displayProperty=fullName></xref:System.Windows.Forms?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a949d-174"><xref:System.Windows.Forms?displayProperty=fullName></span></span>   
<span data-ttu-id="a949d-175"> [Сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="a949d-175"> [Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="a949d-176"> [Практическое руководство: Создание и использование сборок с помощью командной строки](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4) </span><span class="sxs-lookup"><span data-stu-id="a949d-176"> [How to: Create and Use Assemblies Using the Command Line](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4) </span></span>  
<span data-ttu-id="a949d-177"> [Ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span><span class="sxs-lookup"><span data-stu-id="a949d-177"> [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span></span>  
<span data-ttu-id="a949d-178"> [Оператор Imports (пространство имен .NET и тип)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span><span class="sxs-lookup"><span data-stu-id="a949d-178"> [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span></span>  
<span data-ttu-id="a949d-179"> [Написание кода в решениях Office](https://msdn.microsoft.com/library/bb608596)</span><span class="sxs-lookup"><span data-stu-id="a949d-179"> [Writing Code in Office Solutions](https://msdn.microsoft.com/library/bb608596)</span></span>
