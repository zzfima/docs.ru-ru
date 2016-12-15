---
title: "Структура программы Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "условная компиляция, Visual Basic"
  - "процедуры, структура"
  - "структура программы, Visual Basic"
  - "код Visual Basic, структура программы"
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Структура программы Visual Basic
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Программа [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] построена из стандартных блоков.  *Решение* состоит из одного или нескольких проектов.  *Проект* в свою очередь может содержать одну или несколько сборок.  Каждая *сборка* компилируется из одного или нескольких исходных файлов.  *Исходный файл* включает в себя определения и реализацию классов, структур, модулей и интерфейсов, и в конечном счете содержит весь код.  
  
 Дополнительные сведения об этих стандартных блоках программы [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] см. в разделах [Проекты и решения](/visual-studio/ide/solutions-and-projects-in-visual-studio) и [Сборки и глобальный кэш сборок](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Элементы программирования уровня файла  
 При создании проекта или файла и открытии редактора кода, пользователю предоставляется уже готовая часть кода, расположенная в правильном порядке.  Любой код должен создаваться в следующей последовательности:  
  
1.  Операторы `Option`  
  
2.  Операторы `Imports`  
  
3.  Операторы `Namespace` и элементы уровня пространства имен  
  
 Размещение операторов в иной последовательности может вызвать ошибки компиляции.  
  
 В программе также могут содержаться операторы условной компиляции.  Можно использовать их вместе с операторами предыдущей последовательности в исходном файле.  
  
### Операторы Option  
 Операторы `Option` устанавливают основные правила для последующего кода, способствуя предотвращению синтаксических и логических ошибок.  [Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md) проверяет, все ли переменные объявлены и написаны правильно, что сокращает время отладки.  [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) позволяет избежать логических ошибок и потери данных, возникающих при работе с переменными различных типов.  [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) указывает, каким образом строки сравниваются друг с другом, на основе их значений `Binary` или `Text`.  
  
### Оператор Imports  
 Можно включить [Оператор Imports \(пространство имен .NET и тип\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md), чтобы импортировать имена, определенные вне проекта.  Оператор `Imports` позволяет ссылаться на классы и другие типы, определенные в импортированном пространстве имен, без их уточнения.  Можно использовать столько операторов `Imports`, сколько необходимо.  Дополнительные сведения см. в разделе [Ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md).  
  
### Операторы пространства имен  
 Пространства имен помогают организовывать и классифицировать элементы программирования для облегчения их группировки и доступа к ним.  [Оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md) используется для классификации следующих операторов в определенном пространстве имен.  Дополнительные сведения см. в разделе [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
### Операторы условной компиляции  
 Операторы условной компиляции могут использоваться практически в любом месте исходного файла.  Они определяют включение или исключение частей кода во время компиляции в зависимости от определенных условий.  Также они могут использоваться для отладки приложения, поскольку условный код выполняется только в режиме отладки.  Дополнительные сведения см. в разделе [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md).  
  
## Элементы программирования уровня пространства имен  
 Классы, структуры и модули содержат весь код исходного файла.  Они являются элементами *уровня пространства имен* и могут отображаться в пространстве имен или на уровне исходного файла.  Они содержат описания всех других элементов программирования.  Интерфейсы, которые определяют подписи элементов, но не выполняют реализацию, также отображаются на уровне модуля.  Дополнительные сведения об элементах на уровне модуля см. в следующих разделах.  
  
-   [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
-   [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)  
  
-   [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 Элементы данных на уровне пространства имен являются перечислениями и делегатами.  
  
## Элементы программирования уровня модуля  
 Процедуры, операторы, свойства и события являются единственными элементами программирования, которые могут содержать исполняемый код \(то есть выполняются во время выполнения\).  Они являются элементами *уровня модуля* программы.  Дополнительные сведения об элементах уровня процедуры см. в следующих разделах.  
  
-   [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Оператор Operator](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
-   [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 Элементами данных на уровне модуля являются переменные, константы, перечисления и делегаты.  
  
## Элементы программирования уровня процедуры  
 К элементам *уровня процедуры* относятся в основном исполняемые операторы, которые составляют код времени выполнения программы.  Весь исполняемый код должен находиться в пределах некоторой процедуры \(`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`\).  Дополнительные сведения см. в разделе [Операторы](../../../visual-basic/programming-guide/language-features/statements.md).  
  
 Элементы данных на уровне процедуры ограничиваются локальными переменными и константами.  
  
## Процедура Main  
 Процедура `Main` выполняется первой при загрузке приложения.  Процедура `Main` служит начальной точкой программы и осуществляет общее управление работой приложения.  Существуют четыре вида процедуры `Main`:  
  
-   `Sub Main()`  
  
-   `Sub Main(ByVal cmdArgs() As String)`  
  
-   `Function Main() As Integer`  
  
-   `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 Наиболее распространенный вид — `Sub Main()`.  Дополнительные сведения см. в разделе [Процедура Main в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).  
  
## См. также  
 ["Hello, World", версия на языке Visual Basic](http://msdn.microsoft.com/ru-ru/9d030b60-e148-4366-a462-69532f02294c)   
 [Процедура Main в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)   
 [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [Ограничения в Visual Basic](../../../visual-basic/programming-guide/program-structure/limitations.md)