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
ms.openlocfilehash: 5b810af86f8659ffbe27d23d36aece408516a9bd
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972056"
---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="087f0-102">Ссылки и оператор Imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="087f0-102">References and the Imports Statement (Visual Basic)</span></span>
<span data-ttu-id="087f0-103">Можно сделать внешние объекты доступными для проекта, выбрав команду **Добавить ссылку** в меню **проект** .</span><span class="sxs-lookup"><span data-stu-id="087f0-103">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="087f0-104">Ссылки в Visual Basic могут указывать на сборки, которые подобны библиотекам типов, но содержат дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="087f0-104">References in Visual Basic can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="087f0-105">Оператор Imports</span><span class="sxs-lookup"><span data-stu-id="087f0-105">The Imports Statement</span></span>  
 <span data-ttu-id="087f0-106">Сборки включают одно или несколько пространств имен.</span><span class="sxs-lookup"><span data-stu-id="087f0-106">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="087f0-107">При добавлении ссылки на сборку можно также добавить `Imports` инструкцию в модуль, управляющий видимостью пространств имен этой сборки в модуле.</span><span class="sxs-lookup"><span data-stu-id="087f0-107">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="087f0-108">`Imports` Оператор предоставляет контекст области, который позволяет использовать только часть пространства имен, необходимую для предоставления уникальной ссылки.</span><span class="sxs-lookup"><span data-stu-id="087f0-108">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="087f0-109">`Imports` Оператор имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="087f0-109">The `Imports` statement has the following syntax:</span></span>  
  
 `Imports [Aliasname =] Namespace`  
  
 <span data-ttu-id="087f0-110">`Aliasname`ссылается на короткое имя, которое можно использовать в коде для ссылки на импортированное пространство имен.</span><span class="sxs-lookup"><span data-stu-id="087f0-110">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="087f0-111">`Namespace`— Это пространство имен, доступное через ссылку на проект, через определение в проекте или с помощью предыдущей `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="087f0-111">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="087f0-112">Модуль может содержать любое количество `Imports` инструкций.</span><span class="sxs-lookup"><span data-stu-id="087f0-112">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="087f0-113">Они должны располагаться `Option` после любых операторов, если они есть, но перед любым другим кодом.</span><span class="sxs-lookup"><span data-stu-id="087f0-113">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="087f0-114">Не путайте ссылки на проект с `Imports` оператором `Declare` или инструкцией.</span><span class="sxs-lookup"><span data-stu-id="087f0-114">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="087f0-115">Ссылки проекта делают внешние объекты, такие как объекты в сборках, доступными для Visual Basic проектов.</span><span class="sxs-lookup"><span data-stu-id="087f0-115">Project references make external objects, such as objects in assemblies, available to Visual Basic projects.</span></span> <span data-ttu-id="087f0-116">`Imports` Оператор используется для упрощения доступа к ссылкам на проекты, но не предоставляет доступ к этим объектам.</span><span class="sxs-lookup"><span data-stu-id="087f0-116">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="087f0-117">`Declare` Оператор используется для объявления ссылки на внешнюю процедуру в библиотеке динамической компоновки (DLL).</span><span class="sxs-lookup"><span data-stu-id="087f0-117">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="087f0-118">Использование псевдонимов с оператором Imports</span><span class="sxs-lookup"><span data-stu-id="087f0-118">Using Aliases with the Imports Statement</span></span>  
 <span data-ttu-id="087f0-119">`Imports` Оператор упрощает доступ к методам классов, устраняя необходимость явно вводить полные имена ссылок.</span><span class="sxs-lookup"><span data-stu-id="087f0-119">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="087f0-120">Псевдонимы позволяют назначить более дружественное имя только одной части пространства имен.</span><span class="sxs-lookup"><span data-stu-id="087f0-120">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="087f0-121">Например, последовательность возврата каретки/перевода строки, которая приводит к отображению одного фрагмента текста на нескольких строках, является частью <xref:Microsoft.VisualBasic.ControlChars> модуля <xref:Microsoft.VisualBasic?displayProperty=nameWithType> в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="087f0-121">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="087f0-122">Чтобы использовать эту константу в программе без псевдонима, необходимо ввести следующий код:</span><span class="sxs-lookup"><span data-stu-id="087f0-122">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 [!code-vb[VbVbalrApplication#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#3)]  
  
 <span data-ttu-id="087f0-123">`Imports`операторы всегда должны быть первыми строками, непосредственно следующими `Option` за любыми операторами в модуле.</span><span class="sxs-lookup"><span data-stu-id="087f0-123">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="087f0-124">В следующем фрагменте кода показано, как импортировать и назначить для <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> модуля псевдоним.</span><span class="sxs-lookup"><span data-stu-id="087f0-124">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> module:</span></span>  
  
 [!code-vb[VbVbalrApplication#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#4)]  
  
 <span data-ttu-id="087f0-125">Дальнейшие ссылки на это пространство имен могут быть значительно короче:</span><span class="sxs-lookup"><span data-stu-id="087f0-125">Future references to this namespace can be considerably shorter:</span></span>  
  
 [!code-vb[VbVbalrApplication#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#5)]  
  
 <span data-ttu-id="087f0-126">`Imports` Если инструкция не включает имя псевдонима, элементы, определенные в импортированном пространстве имен, могут использоваться в модуле без уточнения.</span><span class="sxs-lookup"><span data-stu-id="087f0-126">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="087f0-127">Если имя псевдонима указано, оно должно использоваться в качестве квалификатора для имен, содержащихся в этом пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="087f0-127">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="087f0-128">См. также</span><span class="sxs-lookup"><span data-stu-id="087f0-128">See also</span></span>

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [<span data-ttu-id="087f0-129">Пространства имен в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="087f0-129">Namespaces in Visual Basic</span></span>](namespaces.md)
- [<span data-ttu-id="087f0-130">Сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="087f0-130">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="087f0-131">Оператор Imports (пространство имен и тип .NET)</span><span class="sxs-lookup"><span data-stu-id="087f0-131">Imports Statement (.NET Namespace and Type)</span></span>](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
