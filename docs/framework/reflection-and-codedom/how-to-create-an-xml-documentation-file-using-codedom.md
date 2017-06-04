---
title: "How to: Create an XML Documentation File Using CodeDOM | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "CodeDOM, generating XML documentation"
  - "XML documentation, creating using CodeDOM"
  - "Code Document Object Model, generating XML documentation"
ms.assetid: e3b80484-36b9-41dd-9d21-a2f9a36381dc
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Create an XML Documentation File Using CodeDOM
CodeDOM можно использовать для создания кода, создающего XML\-документацию.  Этот процесс предполагает создание графа CodeDOM, содержащего комментарии XML\-документации, создание кода, а также компиляцию созданного кода с параметром компилятора, при выборе которого в итоге создается XML\-документация.  
  
### Чтобы создать граф CodeDOM, который содержит комментарии XML\-документации, выполните следующие действия  
  
1.  Создайте объект <xref:System.CodeDom.CodeCompileUnit>, содержащий граф CodeDOM для примера приложения.  
  
2.  При помощи конструктора <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A>, параметру `docComment` которого присвоено значение `true`, создайте элементы и текст комментариев XML\-документации.  
  
     [!code-csharp[CodeDomHelloWorldSample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#4)]
     [!code-vb[CodeDomHelloWorldSample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#4)]  
  
### Чтобы создать код на основе объекта CodeCompileUnit, выполните следующие действия  
  
1.  При помощи метода <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> создайте код и исходный файл для компиляции.  
  
     [!code-csharp[CodeDomHelloWorldSample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#5)]
     [!code-vb[CodeDomHelloWorldSample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#5)]  
  
### Чтобы скомпилировать код и создать файл документации, выполните следующие действия  
  
1.  Добавьте параметр компилятора **\/doc** в свойство <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> объекта <xref:System.CodeDom.Compiler.CompilerParameters> и передайте этот объект в метод <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A>, чтобы создать файл XML\-документации при компиляции кода.  
  
     [!code-csharp[CodeDomHelloWorldSample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#6)]
     [!code-vb[CodeDomHelloWorldSample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#6)]  
  
## Пример  
 В следующем примере кода создается граф CodeDOM с комментариями документации, на основе этого графа создается файл кода, этот файл компилируется, а затем создается сопоставленный файл XML\-документации.  
  
 [!code-csharp[CodeDomHelloWorldSample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#1)]
 [!code-vb[CodeDomHelloWorldSample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#1)]  
  
 В этом примере в файле HelloWorldDoc.xml создается следующая XML\-документация.  
  
```  
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
  
## Компиляция кода  
  
-   Для выполнения этого кода должно быть установлено разрешение `FullTrust`.  
  
## См. также  
 [Документирование кода с помощью XML](../Topic/Documenting%20Your%20Code%20with%20XML%20\(Visual%20Basic\).md)   
 [Комментарии к XML\-документации](../Topic/XML%20Documentation%20Comments%20\(C%23%20Programming%20Guide\).md)   
 [Документация XML](../Topic/XML%20Documentation%20\(Visual%20C++\).md)