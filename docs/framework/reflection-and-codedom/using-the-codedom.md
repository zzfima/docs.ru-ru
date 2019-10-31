---
title: Использование CodeDOM
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- code compilers
- Code Document Object Model
- Code Document Object Model, graphs
- types, CodeDOM
- namespaces [.NET Framework], CodeDOM
- templated code generation
- dynamically representing source code
- source code models
- CodeDOM
- graphing with CodeDOM
- dynamic compilation
- code generators
- CodeDOM, graphs
ms.assetid: 0444ddf3-c3f6-44ed-a999-f710d9c3e0cf
ms.openlocfilehash: c4cab79976acae236de5a8eaad5a42cdba7d04f9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129997"
---
# <a name="using-the-codedom"></a>Использование CodeDOM
CodeDOM содержит типы, представляющие многие общие типы элементов исходного кода. Вы можете разработать программу, которая будет строить модель исходного кода, используя элементы CodeDOM для создания графа объектов. Этот граф объектов может быть воспроизведен в виде исходного кода с помощью генератора кода CodeDOM для поддерживаемого языка программирования. CodeDOM можно также использовать для компиляции исходного кода в двоичную сборку.  
  
 Ниже приведены некоторые примеры применения CodeDOM.  
  
- Формирование кода по шаблонам: формирование кода для ASP.NET, клиентских прокси для веб-служб XML, мастеров кода, конструкторов или других механизмов порождения кода.  
  
- Динамическая компиляция: поддержка компиляции кода на одном языке или нескольких языках программирования.  
  
## <a name="building-a-codedom-graph"></a>Построение графа CodeDOM  
 Пространство имен <xref:System.CodeDom> предоставляет классы для представления логической структуры исходного кода, независимой от синтаксиса языка.  
  
### <a name="the-structure-of-a-codedom-graph"></a>Структура графа CodeDOM  
 Структура графа CodeDOM представляет собой дерево контейнеров. Самым верхним (корневым) контейнером каждого графа CodeDOM, доступного для компиляции, является <xref:System.CodeDom.CodeCompileUnit>. Каждый элемент модели исходного кода должен быть связан с графом посредством свойства <xref:System.CodeDom.CodeObject> в графе.  
  
### <a name="building-a-source-code-model-for-a-sample-hello-world-program"></a>Построение модели исходного кода для образца программы "Hello, World"  
 Ниже приведено пошаговое руководство по построению графа объектов CodeDOM, представляющего код для простого приложения "Hello, World". Полный исходный код для этого примера см. в разделе <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>.  
  
#### <a name="creating-a-compile-unit"></a>Создание модуля компиляции  
 CodeDOM определяет объект с именем <xref:System.CodeDom.CodeCompileUnit>, который может ссылаться на граф объектов CodeDOM, моделирующий компилируемый исходный код. В свойствах объекта **CodeCompileUnit** могут храниться ссылки на атрибуты, пространства имен и сборки.  
  
 Поставщики CodeDom, производные от класса <xref:System.CodeDom.Compiler.CodeDomProvider>, содержат методы, которые обрабатывают граф объектов, на который ссылается **CodeCompileUnit**.  
  
 Чтобы создать граф объектов для простого приложения, необходимо собрать модель исходного кода и сослаться на нее из **CodeCompileUnit**.  
  
 В следующем примере приведен синтаксис для создания модуля компиляции.  
  
 [!code-cpp[CodeDomExample#12](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#12)]
 [!code-csharp[CodeDomExample#12](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#12)]
 [!code-vb[CodeDomExample#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#12)]  
  
 <xref:System.CodeDom.CodeSnippetCompileUnit> может содержать раздел исходного кода, который уже написан на целевом языке, но не может быть преобразован в другой язык.  
  
#### <a name="defining-a-namespace"></a>Определение пространства имен  
 Чтобы определить пространство имен, необходимо создать объект <xref:System.CodeDom.CodeNamespace>, а затем присвоить ему имя, используя подходящий конструктор или установив значение свойства **Name**.  
  
 [!code-cpp[CodeDomExample#13](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#13)]
 [!code-csharp[CodeDomExample#13](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#13)]
 [!code-vb[CodeDomExample#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#13)]  
  
#### <a name="importing-a-namespace"></a>Импорт пространства имен  
 Чтобы добавить в пространство имен директиву импорта пространства имен, добавьте <xref:System.CodeDom.CodeNamespaceImport>, который указывает пространство имен, которое следует импортировать в коллекцию **CodeNamespace.Imports**.  
  
 В следующем фрагменте кода пространство имен **System** импортируется в коллекцию **Imports** объекта **CodeNamespace** с именем `samples`:  
  
 [!code-cpp[CodeDomExample#14](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#14)]
 [!code-csharp[CodeDomExample#14](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#14)]
 [!code-vb[CodeDomExample#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#14)]  
  
#### <a name="linking-code-elements-into-the-object-graph"></a>Связывание элементов кода с графом объектов  
 Все элементы кода, образующие граф CodeDOM, должны быть связаны с объектом <xref:System.CodeDom.CodeCompileUnit>, являющимся корневым элементом дерева, последовательностью ссылок между элементами, на которые имеются прямые ссылки из свойств корневого объекта графа. Чтобы задать ссылку из объекта-контейнера, необходимо присвоить объект свойству объекта-контейнера.  
  
 Приведенный ниже оператор добавляет `samples` **CodeNamespace** в свойство коллекции **Namespaces** корневого объекта **CodeCompileUnit**.  
  
 [!code-cpp[CodeDomExample#15](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#15)]
 [!code-csharp[CodeDomExample#15](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#15)]
 [!code-vb[CodeDomExample#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#15)]  
  
#### <a name="defining-a-type"></a>Определение типа  
 Чтобы объявить класс, структуру, интерфейс или перечисление с помощью CodeDOM, создайте объявление <xref:System.CodeDom.CodeTypeDeclaration> и присвойте ему имя. В приведенном ниже примере демонстрируется использование перегрузки конструктора для задания значения свойства **Name**.  
  
 [!code-cpp[CodeDomExample#16](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#16)]
 [!code-csharp[CodeDomExample#16](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#16)]
 [!code-vb[CodeDomExample#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#16)]  
  
 Чтобы добавить тип в пространство имен, добавьте объект <xref:System.CodeDom.CodeTypeDeclaration>, представляющий тип, который следует добавить в коллекцию **Types** пространства имен **CodeNamespace**.  
  
 В следующем примере демонстрируется добавление класса `class1` в пространство имен **CodeNamespace** с именем `samples`:  
  
 [!code-cpp[CodeDomExample#17](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#17)]
 [!code-csharp[CodeDomExample#17](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#17)]
 [!code-vb[CodeDomExample#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#17)]  
  
#### <a name="adding-class-members-to-a-class"></a>Добавление в класс членов класса  
 Пространство имен <xref:System.CodeDom> предоставляет различные элементы, которые можно использовать для представления членов класса. Каждый элемент класса может быть добавлен в коллекцию **Members** объекта <xref:System.CodeDom.CodeTypeDeclaration>.  
  
#### <a name="defining-a-code-entry-point-method-for-an-executable"></a>Определение метода, являющегося точкой входа в код исполняемого файла  
 В случае сборки кода исполняемой программы необходимо указать точку входа в программу, создав объект <xref:System.CodeDom.CodeEntryPointMethod> для представления метода, с которого должно начинаться выполнение программы.  
  
 В следующем примере показано, как определить метод точки входа, который содержит объект <xref:System.CodeDom.CodeMethodInvokeExpression>, вызывающий **System.Console.WriteLine** для вывода текста "Hello World!":  
  
 [!code-cpp[CodeDomExample#18](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#18)]
 [!code-csharp[CodeDomExample#18](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#18)]
 [!code-vb[CodeDomExample#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#18)]  
  
 Приведенный ниже оператор добавляет метод точки входа `Start` в коллекцию **Members** класса `class1`.  
  
 [!code-cpp[CodeDomExample#19](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#19)]
 [!code-csharp[CodeDomExample#19](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#19)]
 [!code-vb[CodeDomExample#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#19)]  
  
 Теперь объект <xref:System.CodeDom.CodeCompileUnit> с именем `compileUnit` содержит граф CodeDOM для простой программы "Hello World". Сведения о создании и компиляции кода на основе графа CodeDOM см. в разделе [Создание исходного кода и компиляция программы из графа CodeDOM](generating-and-compiling-source-code-from-a-codedom-graph.md).  
  
### <a name="more-information-on-building-a-codedom-graph"></a>Дополнительные сведения о построении графа CodeDOM  
 CodeDOM поддерживает многие общие типы элементов кода, которые встречаются в языках программирования, поддерживающих среду CLR. Но CodeDOM не предусматривает предоставление элементов для представления всех возможных функций языков программирования. Код, который не может быть без труда представлен элементами CodeDOM, можно инкапсулировать в объекты <xref:System.CodeDom.CodeSnippetExpression>, <xref:System.CodeDom.CodeSnippetStatement>, <xref:System.CodeDom.CodeSnippetTypeMember> или <xref:System.CodeDom.CodeSnippetCompileUnit>. Но фрагменты кода невозможно автоматически переводить с помощью CodeDOM на другие языки.  
  
 Сведения о каждом типе CodeDOM см. в справочной документации по пространству имен <xref:System.CodeDom>.  
  
 Быстро найти элемент CodeDOM, представляющий определенный тип элемента кода, можно в разделе [Краткий справочник по CodeDOM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100)).
