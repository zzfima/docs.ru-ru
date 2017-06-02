---
title: "Using the CodeDOM | Microsoft Docs"
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
  - "code compilers"
  - "Code Document Object Model"
  - "Code Document Object Model, graphs"
  - "types, CodeDOM"
  - "namespaces [.NET Framework], CodeDOM"
  - "templated code generation"
  - "dynamically representing source code"
  - "source code models"
  - "CodeDOM"
  - "graphing with CodeDOM"
  - "dynamic compilation"
  - "code generators"
  - "CodeDOM, graphs"
ms.assetid: 0444ddf3-c3f6-44ed-a999-f710d9c3e0cf
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Using the CodeDOM
CodeDOM содержит типы, представляющие многие общие типы элементов исходного кода.  Можно разработать программу, которая будет строить модель исходного кода, используя элементы CodeDOM для создания графа объектов.  Этот объектный граф может быть воспроизведен в виде исходного кода при помощи генератора кода CodeDOM для поддерживаемого языка программирования.  CodeDOM можно также использовать для компиляции исходного кода в двоичную сборку.  
  
 Примеры применения CodeDOM следующие.  
  
-   Генерация кода по шаблонам: генерация кода для ASP.NET, клиентских прокси для веб\-служб XML, мастеров кода, конструкторов или других механизмов выпуска кода.  
  
-   Динамическая компиляция: поддержка компиляции кода на одном или нескольких языках программирования.  
  
## Построение графа CodeDOM  
 Пространство имен <xref:System.CodeDom> предоставляет классы для представления логической структуры исходного кода, независимого от синтаксиса языка.  
  
### Структура графа CodeDOM  
 Структура графа CodeDOM представляет собой дерево контейнеров.  Самый верхний \(корневой\) контейнер каждого графа CodeDOM, доступного для компиляции, является <xref:System.CodeDom.CodeCompileUnit>.  Каждый элемент модели исходного кода должен быть связан с графом посредством свойства <xref:System.CodeDom.CodeObject> в графе.  
  
### Построение модели исходного кода для учебной программы "Hello, World"  
 Ниже показано пошаговое руководство построения графа объектов CodeDOM, представляющего код для простого приложения "Hello, World".  Полный исходный код для этого примера кода см. в разделе <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=fullName>.  
  
#### Создание единицы компиляции  
 CodeDOM определяет объект с именем <xref:System.CodeDom.CodeCompileUnit>, который может ссылаться на граф объекта CodeDOM, моделирующего исходный компилируемый код.  В свойствах объекта **CodeCompileUnit** могут храниться ссылки на атрибуты, пространства имен и сборки.  
  
 Поставщики CodeDom, производные из класса <xref:System.CodeDom.Compiler.CodeDomProvider>, содержат методы, которые обрабатывают граф объекта, на который ссылается **CodeCompileUnit**.  
  
 Чтобы создать граф объектов для простого приложения, необходимо собрать модель исходного кода и сослаться на нее из **CodeCompileUnit**.  
  
 В следующем примере приведен синтаксис создания новой единицы компиляции.  
  
 [!code-cpp[CodeDomExample#12](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#12)]
 [!code-csharp[CodeDomExample#12](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#12)]
 [!code-vb[CodeDomExample#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#12)]  
  
 <xref:System.CodeDom.CodeSnippetCompileUnit> может содержать раздел исходного кода, который уже написан в целевом языке, но не может быть преобразован в другой язык.  
  
#### Определение пространства имен  
 Чтобы определить пространство имен, необходимо создать объект <xref:System.CodeDom.CodeNamespace>, а затем присвоить ему имя, используя подходящий конструктор или установив значение свойства **Name**.  
  
 [!code-cpp[CodeDomExample#13](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#13)]
 [!code-csharp[CodeDomExample#13](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#13)]
 [!code-vb[CodeDomExample#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#13)]  
  
#### Импорт пространства имен  
 Чтобы добавить в пространство имен директиву импорта пространства имен, добавьте <xref:System.CodeDom.CodeNamespaceImport>, который указывает пространство имен, которое следует импортировать в коллекцию **CodeNamespace.Imports**.  
  
 В следующем фрагменте кода пространство имен **System** импортируется в коллекцию **Imports** объекта **CodeNamespace** с именем `samples`:  
  
 [!code-cpp[CodeDomExample#14](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#14)]
 [!code-csharp[CodeDomExample#14](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#14)]
 [!code-vb[CodeDomExample#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#14)]  
  
#### Связывание элементов кода с графом объектов  
 Все элементы кода, образующие граф CodeDOM, должны быть связаны с объектом <xref:System.CodeDom.CodeCompileUnit>, являющимся корневым элементом дерева, последовательностью ссылок между элементами, на которые имеются прямые ссылки из свойств корневого объекта графа.  Чтобы установить ссылку на объект из объекта\-контейнера, необходимо присвоить свойству контейнера значение объекта.  
  
 Следующий оператор добавляет `samples` **CodeNamespace** в свойство коллекции **Namespaces** корневого объекта **CodeCompileUnit**.  
  
 [!code-cpp[CodeDomExample#15](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#15)]
 [!code-csharp[CodeDomExample#15](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#15)]
 [!code-vb[CodeDomExample#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#15)]  
  
#### Определение типа  
 Чтобы объявить класс, структуру, интерфейс или перечисление с помощью CodeDOM, создайте новое объявление <xref:System.CodeDom.CodeTypeDeclaration> и присвойте ему имя.  В следующем примере демонстрируется использование перегрузки конструктора для задания значения свойства **Name**.  
  
 [!code-cpp[CodeDomExample#16](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#16)]
 [!code-csharp[CodeDomExample#16](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#16)]
 [!code-vb[CodeDomExample#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#16)]  
  
 Чтобы добавить тип в пространство имен, добавьте объект <xref:System.CodeDom.CodeTypeDeclaration>, который представляет тип, который следует добавить в коллекцию **Типы** пространства имен **CodeNamespace**.  
  
 В следующем примере демонстрируется добавление класса `class1` в пространство имен **CodeNamespace** с именем `samples`:  
  
 [!code-cpp[CodeDomExample#17](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#17)]
 [!code-csharp[CodeDomExample#17](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#17)]
 [!code-vb[CodeDomExample#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#17)]  
  
#### Добавление в класс элементов класса  
 Пространство имен <xref:System.CodeDom> предоставляет различные элементы, которые могут быть использованы для представления элементов класса.  Каждый элемент класса может быть добавлен в коллекцию **Members** объекта <xref:System.CodeDom.CodeTypeDeclaration>.  
  
#### Определение метода, являющегося точкой входа исполняемого файла  
 В случае построения кода исполняемой программы необходимо указать точку входа программы, создав объект <xref:System.CodeDom.CodeEntryPointMethod> для представления метода, с которого должно начинаться выполнение программы.  
  
 В следующем примере показывается, как определить метод точки входа, который содержит объект <xref:System.CodeDom.CodeMethodInvokeExpression>, вызывающий **System.Console.WriteLine** для отображения "Hello World\!":  
  
 [!code-cpp[CodeDomExample#18](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#18)]
 [!code-csharp[CodeDomExample#18](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#18)]
 [!code-vb[CodeDomExample#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#18)]  
  
 Следующий оператор добавляет метод точки входа `Start` в коллекцию **Members** класса `class1`.  
  
 [!code-cpp[CodeDomExample#19](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#19)]
 [!code-csharp[CodeDomExample#19](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#19)]
 [!code-vb[CodeDomExample#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#19)]  
  
 Теперь объект <xref:System.CodeDom.CodeCompileUnit> с именем `compileUnit` содержит граф CodeDOM для простой программы "Hello World".  Сведения о создании и компиляции кода из графа CodeDOM см. в разделе [Создание исходного кода и компиляция программы из графа CodeDOM](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md).  
  
### Дополнительные сведения о построении графа CodeDOM  
 CodeDOM поддерживает многие общие типы элементов кода, встречающихся в языках программирования, поддерживающих среду CLR.  Но CodeDOM не предусматривает предоставление элементов для представления всех возможных функций языков программирования.  Код, который не может быть без труда представлен элементами CodeDOM, можно инкапсулировать в объекты <xref:System.CodeDom.CodeSnippetExpression>, <xref:System.CodeDom.CodeSnippetStatement>, <xref:System.CodeDom.CodeSnippetTypeMember> или <xref:System.CodeDom.CodeSnippetCompileUnit>.  Однако эти фрагменты не могут быть автоматически транслированы с помощью CodeDOM в другие языки.  
  
 Сведения по каждому типу CodeDOM см. в справочной документации по пространству имен <xref:System.CodeDom>.  
  
 Быстро найти элемент CodeDOM, представляющий определенный тип элемента кода, можно в разделе [CodeDOM Quick Reference](http://msdn.microsoft.com/ru-ru/c77b8bfd-0a32-4e36-b59a-4f687f32c524).