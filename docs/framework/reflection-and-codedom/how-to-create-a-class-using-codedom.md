---
title: "Практическое руководство. Создание класса с помощью CodeDOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Code Document Object Model, graphs
- Code Document Object Model, creating classes
- graphing with CodeDOM
- CodeDOM, creating classes
- CodeDOM, graphs
ms.assetid: 0ceb70fe-36e1-49bb-922b-e9f615c20a14
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3876ed881d98b4ee0bdb66f43de3de939111d45d
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-class-using-codedom"></a><span data-ttu-id="f1f0c-102">Практическое руководство. Создание класса с помощью CodeDOM</span><span class="sxs-lookup"><span data-stu-id="f1f0c-102">How to: Create a Class Using CodeDOM</span></span>
<span data-ttu-id="f1f0c-103">В следующих процедурах демонстрируется создание и компиляция графа CodeDOM, который создает класс, содержащий два поля, три свойства, метод, конструктор и точку входа.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-103">The following procedures illustrate how to create and compile a CodeDOM graph that generates a class containing two fields, three properties, a method, a constructor, and an entry point.</span></span>  
  
1.  <span data-ttu-id="f1f0c-104">Создайте приложение консоли, которое будет использовать код CodeDOM для создания исходного кода класса.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-104">Create a console application that will use CodeDOM code to generate the source code for a class.</span></span>  
  
     <span data-ttu-id="f1f0c-105">В этом примере создающий класс называется `Sample`, а созданный код — это класс `CodeDOMCreatedClass` в файле с именем SampleCode.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-105">In this example, the generating class is named `Sample`, and the generated code is a class named `CodeDOMCreatedClass` in a file named SampleCode.</span></span>  
  
2.  <span data-ttu-id="f1f0c-106">В создающем классе инициализируйте граф CodeDOM и используйте методы CodeDOM для определения элементов, конструктора и точки входа (метод `Main`) созданного класса.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-106">In the generating class, initialize the CodeDOM graph and use CodeDOM methods to define the members, constructor, and entry point (`Main` method) of the generated class.</span></span>  
  
     <span data-ttu-id="f1f0c-107">В этом примере созданный класс имеет два поля, три свойства, конструктор, метод и метод `Main`.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-107">In this example, the generated class has two fields, three properties, a constructor, a method, and a `Main` method.</span></span>  
  
3.  <span data-ttu-id="f1f0c-108">В создающем классе создайте поставщик кода определенного языка и вызовите его метод <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> для создания кода из графа.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-108">In the generating class, create a language-specific code provider and call its <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method to generate the code from the graph.</span></span>  
  
4.  <span data-ttu-id="f1f0c-109">Скомпилируйте и выполните приложение для создания кода.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-109">Compile and execute the application to generate the code.</span></span>  
  
     <span data-ttu-id="f1f0c-110">В этом примере созданный код находится в файле с именем SampleCode.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-110">In this example, the generated code is in a file named SampleCode.</span></span> <span data-ttu-id="f1f0c-111">Скомпилируйте и выполните этот код для просмотра выходных данных примера.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-111">Compile and execute that code to see the sample output.</span></span>  
  
### <a name="to-create-the-application-that-will-execute-the-codedom-code"></a><span data-ttu-id="f1f0c-112">Создание приложения, которое будет выполнять код CodeDOM</span><span class="sxs-lookup"><span data-stu-id="f1f0c-112">To create the application that will execute the CodeDOM code</span></span>  
  
-   <span data-ttu-id="f1f0c-113">Создайте класс приложения консоли для включения кода CodeDOM.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-113">Create a console application class to contain the CodeDOM code.</span></span> <span data-ttu-id="f1f0c-114">Определите глобальные поля, которые должны использоваться в классе для ссылки на сборку (<xref:System.CodeDom.CodeCompileUnit>) и класс (<xref:System.CodeDom.CodeTypeDeclaration>), укажите имя созданного исходного файла и объявите метод `Main`.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-114">Define the global fields that are to be used in the class to reference the assembly (<xref:System.CodeDom.CodeCompileUnit>) and class (<xref:System.CodeDom.CodeTypeDeclaration>), specify the name of the generated source file, and declare the `Main` method.</span></span>  
  
     <span data-ttu-id="f1f0c-115">[!code-csharp[CodeDOM Class Sample Main#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample Main/CS/program.cs#1)]  [!code-vb[CodeDOM Class Sample Main#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample Main/VB/program.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="f1f0c-115">[!code-csharp[CodeDOM Class Sample Main#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample Main/CS/program.cs#1)]  [!code-vb[CodeDOM Class Sample Main#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample Main/VB/program.vb#1)]</span></span>  
  
### <a name="to-initialize-the-codedom-graph"></a><span data-ttu-id="f1f0c-116">Инициализация графа CodeDOM</span><span class="sxs-lookup"><span data-stu-id="f1f0c-116">To initialize the CodeDOM graph</span></span>  
  
-   <span data-ttu-id="f1f0c-117">В конструкторе для класса приложения консоли инициализируйте сборку и класс, затем добавьте соответствующие объявления в граф CodeDOM.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-117">In the constructor for the console application class, initialize the assembly and class, and add the appropriate declarations to the CodeDOM graph.</span></span>  
  
     <span data-ttu-id="f1f0c-118">[!code-csharp[CodeDOM Class Sample#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#2)]  [!code-vb[CodeDOM Class Sample#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#2)]</span><span class="sxs-lookup"><span data-stu-id="f1f0c-118">[!code-csharp[CodeDOM Class Sample#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#2)]  [!code-vb[CodeDOM Class Sample#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#2)]</span></span>  
  
### <a name="to-add-members-to-the-codedom-graph"></a><span data-ttu-id="f1f0c-119">Добавление элементов в граф CodeDOM</span><span class="sxs-lookup"><span data-stu-id="f1f0c-119">To add members to the CodeDOM graph</span></span>  
  
-   <span data-ttu-id="f1f0c-120">Добавьте поля в граф CodeDOM, добавив объекты <xref:System.CodeDom.CodeMemberField> в свойство <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> класса.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-120">Add fields to the CodeDOM graph by adding <xref:System.CodeDom.CodeMemberField> objects to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     <span data-ttu-id="f1f0c-121">[!code-csharp[CodeDOM Class Sample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#3)]  [!code-vb[CodeDOM Class Sample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#3)]</span><span class="sxs-lookup"><span data-stu-id="f1f0c-121">[!code-csharp[CodeDOM Class Sample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#3)]  [!code-vb[CodeDOM Class Sample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#3)]</span></span>  
  
-   <span data-ttu-id="f1f0c-122">Добавьте свойства в граф CodeDOM, добавив объекты <xref:System.CodeDom.CodeMemberProperty> в свойство <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> класса.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-122">Add properties to the CodeDOM graph by adding <xref:System.CodeDom.CodeMemberProperty> objects to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     <span data-ttu-id="f1f0c-123">[!code-csharp[CodeDOM Class Sample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#4)]  [!code-vb[CodeDOM Class Sample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#4)]</span><span class="sxs-lookup"><span data-stu-id="f1f0c-123">[!code-csharp[CodeDOM Class Sample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#4)]  [!code-vb[CodeDOM Class Sample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#4)]</span></span>  
  
-   <span data-ttu-id="f1f0c-124">Добавьте метод в граф CodeDOM, добавив объект <xref:System.CodeDom.CodeMemberMethod> в свойство <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> класса.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-124">Add a method to the CodeDOM graph by adding a <xref:System.CodeDom.CodeMemberMethod> object to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     <span data-ttu-id="f1f0c-125">[!code-csharp[CodeDOM Class Sample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#5)]  [!code-vb[CodeDOM Class Sample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#5)]</span><span class="sxs-lookup"><span data-stu-id="f1f0c-125">[!code-csharp[CodeDOM Class Sample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#5)]  [!code-vb[CodeDOM Class Sample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#5)]</span></span>  
  
-   <span data-ttu-id="f1f0c-126">Добавьте конструктор в граф CodeDOM, добавив объект <xref:System.CodeDom.CodeConstructor> в свойство <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> класса.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-126">Add a constructor to the CodeDOM graph by adding a <xref:System.CodeDom.CodeConstructor> object to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     <span data-ttu-id="f1f0c-127">[!code-csharp[CodeDOM Class Sample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#6)]  [!code-vb[CodeDOM Class Sample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#6)]</span><span class="sxs-lookup"><span data-stu-id="f1f0c-127">[!code-csharp[CodeDOM Class Sample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#6)]  [!code-vb[CodeDOM Class Sample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#6)]</span></span>  
  
-   <span data-ttu-id="f1f0c-128">Добавьте точку входа вграф CodeDOM, добавив объект <xref:System.CodeDom.CodeEntryPointMethod> в свойство <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> класса.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-128">Add an entry point to the CodeDOM graph by adding a <xref:System.CodeDom.CodeEntryPointMethod> object to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     <span data-ttu-id="f1f0c-129">[!code-csharp[CodeDOM Class Sample#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#7)]  [!code-vb[CodeDOM Class Sample#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#7)]</span><span class="sxs-lookup"><span data-stu-id="f1f0c-129">[!code-csharp[CodeDOM Class Sample#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#7)]  [!code-vb[CodeDOM Class Sample#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#7)]</span></span>  
  
### <a name="to-generate-the-code-from-the-codedom-graph"></a><span data-ttu-id="f1f0c-130">Создание кода из графа CodeDOM</span><span class="sxs-lookup"><span data-stu-id="f1f0c-130">To generate the code from the CodeDOM graph</span></span>  
  
-   <span data-ttu-id="f1f0c-131">Создайте исходный код из графа CodeDOM, вызвав метод <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A>.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-131">Generate source code from the CodeDOM graph by calling the <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method.</span></span>  
  
     <span data-ttu-id="f1f0c-132">[!code-csharp[CodeDOM Class Sample#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#8)]  [!code-vb[CodeDOM Class Sample#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#8)]</span><span class="sxs-lookup"><span data-stu-id="f1f0c-132">[!code-csharp[CodeDOM Class Sample#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#8)]  [!code-vb[CodeDOM Class Sample#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#8)]</span></span>  
  
### <a name="to-create-the-graph-and-generate-the-code"></a><span data-ttu-id="f1f0c-133">Создание графа и генерация кода</span><span class="sxs-lookup"><span data-stu-id="f1f0c-133">To create the graph and generate the code</span></span>  
  
1.  <span data-ttu-id="f1f0c-134">Добавьте методы, созданные на предыдущих этапах, в метод `Main`, определенный на первом этапе.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-134">Add the methods created in the preceding steps to the `Main` method defined in the first step.</span></span>  
  
     <span data-ttu-id="f1f0c-135">[!code-csharp[CodeDOM Class Sample#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#9)]  [!code-vb[CodeDOM Class Sample#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#9)]</span><span class="sxs-lookup"><span data-stu-id="f1f0c-135">[!code-csharp[CodeDOM Class Sample#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#9)]  [!code-vb[CodeDOM Class Sample#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#9)]</span></span>  
  
2.  <span data-ttu-id="f1f0c-136">Скомпилируйте и выполните создающий класс.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-136">Compile and execute the generating class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1f0c-137">Пример</span><span class="sxs-lookup"><span data-stu-id="f1f0c-137">Example</span></span>  
 <span data-ttu-id="f1f0c-138">В следующем примере кода представлен код, созданный на предыдущих этапах.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-138">The following code example shows the code from the preceding steps.</span></span>  
  
 <span data-ttu-id="f1f0c-139">[!code-csharp[CodeDOM Class Sample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#1)] [!code-vb[CodeDOM Class Sample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="f1f0c-139">[!code-csharp[CodeDOM Class Sample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#1)] [!code-vb[CodeDOM Class Sample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#1)]</span></span>  
  
 <span data-ttu-id="f1f0c-140">При компиляции и выполнении предыдущего примера, происходит создание следующего исходного кода.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-140">When the preceding example is compiled and executed, it produces the following source code.</span></span>  
  
 <span data-ttu-id="f1f0c-141">[!code-csharp[CodeDOM Class Sample#99](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/SampleCode.cs#99)] [!code-vb[CodeDOM Class Sample#99](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/SampleCode.vb#99)]</span><span class="sxs-lookup"><span data-stu-id="f1f0c-141">[!code-csharp[CodeDOM Class Sample#99](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/SampleCode.cs#99)] [!code-vb[CodeDOM Class Sample#99](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/SampleCode.vb#99)]</span></span>  
  
 <span data-ttu-id="f1f0c-142">Созданный исходный код формирует следующие выходные данные при компиляции и выполнении.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-142">The generated source code produces the following output when compiled and executed.</span></span>  
  
```  
The object:  
 width = 5.3,  
 height = 6.9,  
 area = 36.57  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f1f0c-143">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f1f0c-143">Compiling the Code</span></span>  
  
-   <span data-ttu-id="f1f0c-144">Для выполнения этого кода должно быть установлено разрешение `FullTrust`.</span><span class="sxs-lookup"><span data-stu-id="f1f0c-144">This code example requires the `FullTrust` permission set to execute successfully.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1f0c-145">См. также</span><span class="sxs-lookup"><span data-stu-id="f1f0c-145">See Also</span></span>  
 <span data-ttu-id="f1f0c-146">[Использование CodeDOM](../../../docs/framework/reflection-and-codedom/using-the-codedom.md) </span><span class="sxs-lookup"><span data-stu-id="f1f0c-146">[Using the CodeDOM](../../../docs/framework/reflection-and-codedom/using-the-codedom.md) </span></span>  
 [<span data-ttu-id="f1f0c-147">Создание и компиляция исходного кода из графа CodeDOM</span><span class="sxs-lookup"><span data-stu-id="f1f0c-147">Generating and Compiling Source Code from a CodeDOM Graph</span></span>](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md)

