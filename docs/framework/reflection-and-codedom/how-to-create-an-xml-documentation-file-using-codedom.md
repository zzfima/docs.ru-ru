---
title: "Практическое руководство. Создание XML-файла документации с использованием CodeDOM"
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
- CodeDOM, generating XML documentation
- XML documentation, creating using CodeDOM
- Code Document Object Model, generating XML documentation
ms.assetid: e3b80484-36b9-41dd-9d21-a2f9a36381dc
caps.latest.revision: 8
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7d5569fd22cc8469052cc318fd50a5f8ef94c1a9
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-an-xml-documentation-file-using-codedom"></a><span data-ttu-id="e55c4-102">Практическое руководство. Создание XML-файла документации с использованием CodeDOM</span><span class="sxs-lookup"><span data-stu-id="e55c4-102">How to: Create an XML Documentation File Using CodeDOM</span></span>
<span data-ttu-id="e55c4-103">CodeDOM можно использовать для создания кода, создающего XML-документацию.</span><span class="sxs-lookup"><span data-stu-id="e55c4-103">CodeDOM can be used to create code that generates XML documentation.</span></span> <span data-ttu-id="e55c4-104">Этот процесс предполагает создание графа CodeDOM, содержащего комментарии XML-документации, создание кода, а также компиляцию созданного кода с параметром компилятора, при выборе которого в итоге создается XML-документация.</span><span class="sxs-lookup"><span data-stu-id="e55c4-104">The process involves creating the CodeDOM graph that contains the XML documentation comments, generating the code, and compiling the generated code with the compiler option that creates the XML documentation output.</span></span>  
  
### <a name="to-create-a-codedom-graph-that-contains-xml-documentation-comments"></a><span data-ttu-id="e55c4-105">Создание графа CodeDOM, содержащего комментарии XML-документации</span><span class="sxs-lookup"><span data-stu-id="e55c4-105">To create a CodeDOM graph that contains XML documentation comments</span></span>  
  
1.  <span data-ttu-id="e55c4-106">Создайте объект <xref:System.CodeDom.CodeCompileUnit>, содержащий граф CodeDOM для примера приложения.</span><span class="sxs-lookup"><span data-stu-id="e55c4-106">Create a <xref:System.CodeDom.CodeCompileUnit> containing the CodeDOM graph for the sample application.</span></span>  
  
2.  <span data-ttu-id="e55c4-107">С помощью конструктора <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A>, параметру `docComment` которого задано значение `true`, создайте элементы и текст комментариев XML-документации.</span><span class="sxs-lookup"><span data-stu-id="e55c4-107">Use the <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A> constructor with the `docComment` parameter set to `true` to create the XML documentation comment elements and text.</span></span>  
  
     <span data-ttu-id="e55c4-108">[!code-csharp[CodeDomHelloWorldSample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#4)]  [!code-vb[CodeDomHelloWorldSample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#4)]</span><span class="sxs-lookup"><span data-stu-id="e55c4-108">[!code-csharp[CodeDomHelloWorldSample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#4)]  [!code-vb[CodeDomHelloWorldSample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#4)]</span></span>  
  
### <a name="to-generate-the-code-from-the-codecompileunit"></a><span data-ttu-id="e55c4-109">Создание кода на основе объекта CodeCompileUnit</span><span class="sxs-lookup"><span data-stu-id="e55c4-109">To generate the code from the CodeCompileUnit</span></span>  
  
1.  <span data-ttu-id="e55c4-110">С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> создайте код и исходный файл для компиляции.</span><span class="sxs-lookup"><span data-stu-id="e55c4-110">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method to generate the code and create a source file to be compiled.</span></span>  
  
     <span data-ttu-id="e55c4-111">[!code-csharp[CodeDomHelloWorldSample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#5)]  [!code-vb[CodeDomHelloWorldSample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#5)]</span><span class="sxs-lookup"><span data-stu-id="e55c4-111">[!code-csharp[CodeDomHelloWorldSample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#5)]  [!code-vb[CodeDomHelloWorldSample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#5)]</span></span>  
  
### <a name="to-compile-the-code-and-generate-the-documentation-file"></a><span data-ttu-id="e55c4-112">Компиляция кода и создание файла документации</span><span class="sxs-lookup"><span data-stu-id="e55c4-112">To compile the code and generate the documentation file</span></span>  
  
1.  <span data-ttu-id="e55c4-113">Добавьте параметр компилятора **/doc** в свойство <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> объекта <xref:System.CodeDom.Compiler.CompilerParameters> и передайте объект в метод <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A>, чтобы создать файл XML-документации при компиляции кода.</span><span class="sxs-lookup"><span data-stu-id="e55c4-113">Add the **/doc** compiler option to the <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> property of a <xref:System.CodeDom.Compiler.CompilerParameters> object and pass the object to the <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> method to create the XML documentation file when the code is compiled.</span></span>  
  
     <span data-ttu-id="e55c4-114">[!code-csharp[CodeDomHelloWorldSample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#6)]  [!code-vb[CodeDomHelloWorldSample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#6)]</span><span class="sxs-lookup"><span data-stu-id="e55c4-114">[!code-csharp[CodeDomHelloWorldSample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#6)]  [!code-vb[CodeDomHelloWorldSample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#6)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="e55c4-115">Пример</span><span class="sxs-lookup"><span data-stu-id="e55c4-115">Example</span></span>  
 <span data-ttu-id="e55c4-116">В следующем примере кода создается граф CodeDOM с комментариями документации, на основе этого графа создается файл кода, этот файл компилируется, а затем создается сопоставленный файл XML-документации.</span><span class="sxs-lookup"><span data-stu-id="e55c4-116">The following code example creates a CodeDOM graph with documentation comments, generates a code file from the graph, and compiles the file and creates an associated XML documentation file.</span></span>  
  
 <span data-ttu-id="e55c4-117">[!code-csharp[CodeDomHelloWorldSample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#1)] [!code-vb[CodeDomHelloWorldSample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="e55c4-117">[!code-csharp[CodeDomHelloWorldSample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#1)] [!code-vb[CodeDomHelloWorldSample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#1)]</span></span>  
  
 <span data-ttu-id="e55c4-118">В этом примере в файле HelloWorldDoc.xml создается следующая XML-документация.</span><span class="sxs-lookup"><span data-stu-id="e55c4-118">The code example creates the following XML documentation in the HelloWorldDoc.xml file.</span></span>  
  
```xml  
<?xml version="1.0" ?>   
<doc>  
  <assembly>  
    <name>HelloWorld</name>   
  </assembly>  
  <members>  
    <member name="T:Samples.Class1">  
      <summary>  
        Create a Hello World application.   
        <seealso cref="M:Samples.Class1.Main" />   
      </summary>  
    </member>  
    <member name="M:Samples.Class1.Main">  
      <summary>  
        Main method for HelloWorld application.   
        <para>Add a new paragraph to the description.</para>   
      </summary>  
    </member>  
  </members>  
</doc>  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e55c4-119">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="e55c4-119">Compiling the Code</span></span>  
  
-   <span data-ttu-id="e55c4-120">Для выполнения этого кода должно быть установлено разрешение `FullTrust`.</span><span class="sxs-lookup"><span data-stu-id="e55c4-120">This code example requires the `FullTrust` permission set to execute successfully.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e55c4-121">См. также</span><span class="sxs-lookup"><span data-stu-id="e55c4-121">See Also</span></span>  
 <span data-ttu-id="e55c4-122">[Документирование кода с помощью XML](~/docs/visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span><span class="sxs-lookup"><span data-stu-id="e55c4-122">[Documenting Your Code with XML](~/docs/visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span></span>  
 <span data-ttu-id="e55c4-123">[Комментарии XML-документации](~/docs/csharp/programming-guide/xmldoc/xml-documentation-comments.md) </span><span class="sxs-lookup"><span data-stu-id="e55c4-123">[XML Documentation Comments](~/docs/csharp/programming-guide/xmldoc/xml-documentation-comments.md) </span></span>  
 [<span data-ttu-id="e55c4-124">Документация XML</span><span class="sxs-lookup"><span data-stu-id="e55c4-124">XML Documentation</span></span>](/cpp/ide/xml-documentation-visual-cpp)

