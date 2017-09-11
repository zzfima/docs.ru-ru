---
title: "Динамическое создание и компиляция исходного кода"
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
- Code Document Object Model
- System.CodeDom namespace
- language-independent source code modeling
- CodeDOM
- multiple languages supported by CodeDOM
- source code in multiple languages
- languages, multiple language support by CodeDOM
ms.assetid: d077a3e8-bd81-4bdf-b6a3-323857ea30fb
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f1eb17af8fef96f42973e65859bd17b1e835fa98
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="dynamic-source-code-generation-and-compilation"></a><span data-ttu-id="dc9d1-102">Динамическое создание и компиляция исходного кода</span><span class="sxs-lookup"><span data-stu-id="dc9d1-102">Dynamic Source Code Generation and Compilation</span></span>
<span data-ttu-id="dc9d1-103">В среду .NET Framework включен механизм, который называется Code Document Object Model (CodeDOM). Он позволяет разработчикам программ, порождающих исходный код, создавать код на нескольких языках программирования во время выполнения на основе единой модели, представляющей код для визуализации.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-103">The .NET Framework includes a mechanism called the Code Document Object Model (CodeDOM) that enables developers of programs that emit source code to generate source code in multiple programming languages at run time, based on a single model that represents the code to render.</span></span>  
  
 <span data-ttu-id="dc9d1-104">Для представления исходного кода элементы CodeDOM связываются друг с другом, образуя структуру данных, известную как граф CodeDOM, которая моделирует структуру некоторого исходного кода.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-104">To represent source code, CodeDOM elements are linked to each other to form a data structure known as a CodeDOM graph, which models the structure of some source code.</span></span>  
  
 <span data-ttu-id="dc9d1-105">Пространство имен `System.CodeDom` определяет типы, с помощью которых логическая структура исходного кода может быть представлена независимо от конкретного языка программирования.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-105">The `System.CodeDom` namespace defines types that can represent the logical structure of source code, independent of a specific programming language.</span></span> <span data-ttu-id="dc9d1-106">Пространство имен `System.CodeDom.Compiler` определяет типы, используемые для формирования исходного кода на основе графов CodeDOM и управления компиляцией исходного кода на поддерживаемых языках.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-106">The `System.CodeDom.Compiler` namespace defines types for generating source code from CodeDOM graphs and managing the compilation of source code in supported languages.</span></span> <span data-ttu-id="dc9d1-107">Набор поддерживаемых языков может быть расширен разработчиками или поставщиками компиляторов.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-107">Compiler vendors or developers can extend the set of supported languages.</span></span>  
  
 <span data-ttu-id="dc9d1-108">Независимое от языка моделирование исходного кода может быть полезно, если программа должна создавать исходный код для модели программы на нескольких языках или если конечный язык заранее не определен.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-108">Language-independent source code modeling can be valuable when a program needs to generate source code for a program model in multiple languages or for an uncertain target language.</span></span> <span data-ttu-id="dc9d1-109">Например, некоторые конструкторы используют модель CodeDOM в качестве интерфейса абстракции от языка для получения исходного кода на требуемом языке программирования, если имеется поддержка CodeDOM для этого языка.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-109">For example, some designers use the CodeDOM as a language abstraction interface to produce source code in the correct programming language, if CodeDOM support for the language is available.</span></span>  
  
 <span data-ttu-id="dc9d1-110">В платформе .NET Framework имеются генераторы и компиляторы кода для языков <xref:Microsoft.CSharp.CSharpCodeProvider>, <xref:Microsoft.JScript.JScriptCodeProvider> и <xref:Microsoft.VisualBasic.VBCodeProvider>.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-110">The .NET Framework includes code generators and code compilers for <xref:Microsoft.CSharp.CSharpCodeProvider>, <xref:Microsoft.JScript.JScriptCodeProvider>, and <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dc9d1-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="dc9d1-111">In This Section</span></span>  
 [<span data-ttu-id="dc9d1-112">Использование CodeDOM</span><span class="sxs-lookup"><span data-stu-id="dc9d1-112">Using the CodeDOM</span></span>](../../../docs/framework/reflection-and-codedom/using-the-codedom.md)  
 <span data-ttu-id="dc9d1-113">Описываются общие случаи применения, а также демонстрируется создание простого графа объектов с использованием CodeDOM.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-113">Describes common uses, and demonstrates building a simple object graph using the CodeDOM.</span></span>  
  
 [<span data-ttu-id="dc9d1-114">Создание исходного кода и компиляция программы из графа CodeDOM</span><span class="sxs-lookup"><span data-stu-id="dc9d1-114">Generating Source Code and Compiling a Program from a CodeDOM Graph</span></span>](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md)  
 <span data-ttu-id="dc9d1-115">Описание способов формирования исходного кода и его компиляции внешним компилятором с использованием классов, определенных в пространстве имен `System.CodeDom.Compiler`.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-115">Describes how to generate source code and compile the generated code with an external compiler using classes defined in the `System.CodeDom.Compiler` namespace.</span></span>  
  
 [<span data-ttu-id="dc9d1-116">Практическое руководство. Создание XML-файла документации с использованием CodeDOM</span><span class="sxs-lookup"><span data-stu-id="dc9d1-116">How to: Create an XML Documentation File Using CodeDOM</span></span>](../../../docs/framework/reflection-and-codedom/how-to-create-an-xml-documentation-file-using-codedom.md)  
 <span data-ttu-id="dc9d1-117">Описание использования CodeDOM для формирования кода с комментариями к XML-документации и компиляции сформированного кода для создания XML-документации.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-117">Describes how to use CodeDOM to generate code with XML documentation comments, and compile the generated code so that it creates the XML documentation output.</span></span>  
  
 [<span data-ttu-id="dc9d1-118">Практическое руководство. Создание класса с помощью CodeDOM</span><span class="sxs-lookup"><span data-stu-id="dc9d1-118">How to: Create a Class Using CodeDOM</span></span>](../../../docs/framework/reflection-and-codedom/how-to-create-a-class-using-codedom.md)  
 <span data-ttu-id="dc9d1-119">Описание использования CodeDOM для создания класса, содержащего поля, свойства, метод, конструктор и точку входа.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-119">Describes how to use CodeDOM to generate a class containing fields, properties, a method, a constructor, and an entry point.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="dc9d1-120">Ссылка</span><span class="sxs-lookup"><span data-stu-id="dc9d1-120">Reference</span></span>  
 <xref:System.CodeDom>  
 <span data-ttu-id="dc9d1-121">Определяет элементы, представляющие элементы кода на языках программирования, предназначенных для среды CLR.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-121">Defines elements that represent code elements in programming languages that target the common language runtime.</span></span>  
  
 <xref:System.CodeDom.Compiler>  
 <span data-ttu-id="dc9d1-122">Определяет интерфейсы для формирования и компиляции кода во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-122">Defines interfaces for generating and compiling code at run time.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="dc9d1-123">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="dc9d1-123">Related Sections</span></span>  
 [<span data-ttu-id="dc9d1-124">Краткий справочник по CodeDOM</span><span class="sxs-lookup"><span data-stu-id="dc9d1-124">CodeDOM Quick Reference</span></span>](http://msdn.microsoft.com/en-us/c77b8bfd-0a32-4e36-b59a-4f687f32c524)  
 <span data-ttu-id="dc9d1-125">Предоставляет разработчикам быстрый способ поиска элементов CodeDOM, представляющих элементы исходного кода.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-125">Provides a quick way for developers to find the CodeDOM elements that represent source code elements.</span></span>

