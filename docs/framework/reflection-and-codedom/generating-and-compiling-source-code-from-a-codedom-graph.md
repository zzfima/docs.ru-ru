---
title: Создание и компиляция исходного кода из графа CodeDOM
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- code compilers
- CodeDOM, generating source code
- Code Document Object Model, graphs
- templated code generation
- source code, generating
- dynamically representing source code
- generating CodeDOM graphs
- Code Document Object Model, generating source code
- translating language to language
- compiling assemblies
- generating source code in multiple languages
- graphing with CodeDOM
- dynamic compilation
- assemblies [.NET Framework], CodeDOM
- source code generation
- outputting source code by CodeDOM
- code generators
- compiling source code, multiple languages
- CodeDOM, graphs
ms.assetid: 6c864c8e-6dd3-4a65-ace0-36879d9a9c42
ms.openlocfilehash: a8d3bf7363cb887834a1c251aead05c75e2e3fe8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130220"
---
# <a name="generating-and-compiling-source-code-from-a-codedom-graph"></a>Создание и компиляция исходного кода из графа CodeDOM
Пространство имен <xref:System.CodeDom.Compiler> предоставляет интерфейсы для создания исходного кода из графов объекта CodeDOM и для управления компиляцией в поддерживаемых компиляторах. Поставщик кода может создавать исходный код на конкретном языке программирования, используя граф CodeDOM. Класс, производный от <xref:System.CodeDom.Compiler.CodeDomProvider>, обычно может предоставлять методы для создания и компиляции кода для языка, поддерживаемого поставщиком.  
  
## <a name="using-a-codedom-code-provider-to-generate-source-code"></a>Использование поставщика кода CodeDOM для создания исходного кода  
 Чтобы создать исходный код на конкретном языке, необходим граф CodeDOM, представляющий структуру создаваемого исходного кода.  
  
 В следующем примере демонстрируется создание экземпляра <xref:Microsoft.CSharp.CSharpCodeProvider>.  
  
 [!code-cpp[CodeDomExample#21](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#21)]
 [!code-csharp[CodeDomExample#21](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#21)]
 [!code-vb[CodeDomExample#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#21)]  
  
 Граф для создания кода, как правило, содержится в <xref:System.CodeDom.CodeCompileUnit>. Чтобы создать код для **CodeCompileUnit**, содержащего граф CodeDOM, вызовите метод <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> поставщика кода. Этот метод имеет параметр для указания объекта <xref:System.IO.TextWriter>, используемого для создания исходного кода, поэтому иногда сначала необходимо создавать **TextWriter**, в который и будет осуществляться запись. В следующем примере демонстрируется генерация кода из **CodeCompileUnit** и запись созданного исходного кода в файл с именем HelloWorld.cs.  
  
 [!code-cpp[CodeDomExample#22](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#22)]
 [!code-csharp[CodeDomExample#22](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#22)]
 [!code-vb[CodeDomExample#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#22)]  
  
## <a name="using-a-codedom-code-provider-to-compile-assemblies"></a>Использование поставщика кода CodeDOM для компиляции сборок  
 **Вызов процесса компиляции**  
  
 Чтобы скомпилировать сборку, используя поставщик CodeDom, необходимо иметь либо исходный код для компиляции на языке, для которого есть компилятор, либо граф CodeDOM, из которого может быть создан исходный код для компиляции.  
  
 При компиляции из графа CodeDOM передайте объект <xref:System.CodeDom.CodeCompileUnit>, содержащий граф, в метод <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A> поставщика кода. Если имеется файл исходного кода на языке, который понимает компилятор, передайте имя файла, содержащего исходный код, в метод <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> поставщика CodeDom. Также можно передать строку, содержащую исходный код на языке, воспринимаемом компилятором, в метод <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A> поставщика CodeDom.  
  
 **Настройка параметров компиляции**  
  
 Все стандартные методы вызова компиляции поставщика CodeDom имеют параметр типа <xref:System.CodeDom.Compiler.CompilerParameters>, который указывает параметры, используемые для компиляции.  
  
 Можно указать имя файла для выходной сборки в свойстве <xref:System.CodeDom.Compiler.CompilerParameters.OutputAssembly%2A> объекта **CompilerParameters**. В противном случае будет использоваться имя выходного файла по умолчанию.  
  
 По умолчанию инициализируется новый объект **CompilerParameters** со свойством <xref:System.CodeDom.Compiler.CompilerParameters.GenerateExecutable%2A>, равным **false**. При компиляции исполняемой программы необходимо установить значение свойства **GenerateExecutable** равным **true**. Если **GenerateExecutable** имеет значение **false**, компилятор создаст библиотеку классов.  
  
 При компиляции исполняемой программы из графа CodeDOM следует определить в графе объект <xref:System.CodeDom.CodeEntryPointMethod>. Если в коде имеется несколько точек входа, может понадобиться задать свойство <xref:System.CodeDom.Compiler.CompilerParameters.MainClass%2A> объекта **CompilerParameters** равным имени класса, в котором определяется используемая точка входа.  
  
 Чтобы включить сведения об отладке в создаваемый исполняемый файл, присвойте свойству <xref:System.CodeDom.Compiler.CompilerParameters.IncludeDebugInformation%2A> значение **true**.  
  
 Если проект ссылается на какие-либо сборки, необходимо указать имена этих сборок, как элементы в коллекции <xref:System.Collections.Specialized.StringCollection>, так же, как свойство <xref:System.CodeDom.Compiler.CompilerParameters.ReferencedAssemblies%2A> объекта **CompilerParameters** используется при вызове компиляции.  
  
 Для того чтобы скомпилированная сборка записывалась в память, а не на диск, задайте для свойства <xref:System.CodeDom.Compiler.CompilerParameters.GenerateInMemory%2A> значение **true**. При создании сборки в памяти код может получить ссылку на создаваемую сборку из свойства <xref:System.CodeDom.Compiler.CompilerResults.CompiledAssembly%2A> объекта <xref:System.CodeDom.Compiler.CompilerResults>. При записи сборки на диск можно получить путь к созданной сборке из свойства <xref:System.CodeDom.Compiler.CompilerResults.PathToAssembly%2A> объекта **CompilerResults**.  
  
 Чтобы указать пользовательскую строку аргументов командной строки, которую следует использовать при вызове процесса компиляции, задайте строку в свойстве <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A>.  
  
 Если для вызова процесса компилятора требуется маркер безопасности Win32, задайте этот маркер в свойстве <xref:System.CodeDom.Compiler.CompilerParameters.UserToken%2A>.  
  
 Чтобы сделать ссылку на исходный файл Win32 в скомпилированной сборке, укажите имя исходного файла Win32 в свойстве <xref:System.CodeDom.Compiler.CompilerParameters.Win32Resource%2A>.  
  
 Чтобы указать уровень предупреждения, на котором следует прекратить компиляцию, задайте свойство <xref:System.CodeDom.Compiler.CompilerParameters.WarningLevel%2A> как целое число, представляющее уровень предупреждения для прекращения компиляции. Можно также настроить компилятор для прекращения компиляции при обнаружении предупреждений, задав свойству <xref:System.CodeDom.Compiler.CompilerParameters.TreatWarningsAsErrors%2A> значение **true**.  
  
 В следующем примере кода демонстрируется компиляция исходного файла с помощью поставщика CodeDom, производного от класса <xref:System.CodeDom.Compiler.CodeDomProvider>.  
  
 [!code-cpp[CodeDomExample#23](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#23)]
 [!code-csharp[CodeDomExample#23](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#23)]
 [!code-vb[CodeDomExample#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#23)]  
  
## <a name="languages-with-initial-support"></a>Встроенная поддержка языков  
 .NET Framework предоставляет компиляторы и генераторы кода для следующих языков: C#, Visual Basic, C++ и JScript. Поддержка CodeDOM может быть расширена на другие языки путем реализации генераторов и компиляторов кода для определенных языков.  
  
## <a name="see-also"></a>См. также

- <xref:System.CodeDom>
- <xref:System.CodeDom.Compiler>
- [Динамическое создание и компиляция исходного кода](dynamic-source-code-generation-and-compilation.md)
- [Краткий справочник по CodeDOM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100))
