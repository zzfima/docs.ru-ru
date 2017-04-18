---
title: "Структура программы Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- conditional compilation, Visual Basic
- program structure, Visual Basic
- procedures, structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 64aab045538461d86946c870fa428bf8ad4ec15e
ms.lasthandoff: 03/13/2017

---
# <a name="structure-of-a-visual-basic-program"></a>Структура программы Visual Basic
A [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] программа построена из стандартных блоков. Объект *решение* состоит из одного или нескольких проектов. Объект *проекта* в свою очередь может содержать одну или несколько сборок. Каждый *сборки* компилируется из одного или нескольких исходных файлов. Объект *исходный файл* содержит определения и реализации классов, структур, модулей и интерфейсов, которые в конечном счете содержит весь код.  
  
 Дополнительные сведения о таких стандартных блоков [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] программы см. в разделе [решения и проекты](https://docs.microsoft.com/visualstudio/ide/solutions-and-projects-in-visual-studio) и [сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).  
  
## <a name="file-level-programming-elements"></a>Элементы программирования уровня файла  
 При запуске проекта или файла и открыть редактор кода, появиться код уже на месте и в правильном порядке. Любой код, написанный следует придерживаться следующей последовательности:  
  
1.  `Option`инструкции  
  
2.  `Imports`инструкции  
  
3.  `Namespace`инструкции и элементы уровня пространства имен  
  
 Введите инструкции в другом порядке, может привести к ошибкам компиляции.  
  
 Программа также может содержать операторы условной компиляции. Можно смешивать их в исходный файл вместе предыдущей последовательности.  
  
### <a name="option-statements"></a>Параметры инструкции  
 `Option`Инструкции устанавливают основные правила для последующего кода, способствуя предотвращению синтаксических и логических ошибок. [Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md) гарантирует, что все переменные объявлены и написаны правильно, что снижает время при отладке. [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) позволяет свести к минимуму логики ошибок и потери данных, возникающих при работе с переменными различных типов данных. [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) указывает способа сравнения строк друг с другом, либо на основе их `Binary` или `Text` значения.  
  
### <a name="imports-statements"></a>Оператор Imports  
 Можно включить [оператор Imports (пространство имен .NET и тип)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) Чтобы импортировать имена, определенные вне проекта. `Imports` Оператор разрешает код, чтобы ссылаться на классы и другие типы, определенные в импортированном пространстве имен, без их уточнения. Можно использовать любое количество `Imports` соответствующих операторов. Дополнительные сведения см. в разделе [ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md).  
  
### <a name="namespace-statements"></a>Операторы пространства имен  
 Пространства имен помогают организовать и классифицировать элементы программирования для упрощения группировки и доступа к ним. Использовать [оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md) для классификации следующих операторов в определенном пространстве имен. Дополнительные сведения см. в разделе [пространств имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
### <a name="conditional-compilation-statements"></a>Операторы условной компиляции  
 Операторы условной компиляции могут использоваться практически в любом месте в файле исходного кода. Они могут вызывать части кода, чтобы включить или исключить во время компиляции в зависимости от определенных условий. Также их использовании для отладки приложения, поскольку условный код выполняется только в режиме отладки. Дополнительные сведения см. в разделе [условной компиляции](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md).  
  
## <a name="namespace-level-programming-elements"></a>Элементы программирования уровня пространства имен  
 Классы, структуры и модули содержат весь код в файле исходного кода. Они являются *уровня пространства имен* элементов, которые могут находиться в пространстве имен или на уровне исходного файла. Они содержат описания всех других элементов программирования. Интерфейсы, которые определяют подписи элементов, но не выполняют реализацию, также отображаются на уровне модуля. Дополнительные сведения об элементах уровня модуля см.  
  
-   [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
-   [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)  
  
-   [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 Элементы данных на уровне пространства имен, перечисления и делегаты.  
  
## <a name="module-level-programming-elements"></a>Элементы программирования уровня модуля  
 Процедуры, операторы, свойства и события являются единственными элементами программирования, которые могут содержать исполняемый код (инструкции, которые выполняют действия во время выполнения). Они являются *уровня модуля* элементы программы. Дополнительные сведения об элементах уровня процедуры см.  
  
-   [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
-   [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 Элементы данных на уровне модуля являются переменные, константы, перечисления и делегаты.  
  
## <a name="procedure-level-programming-elements"></a>Элементы программирования уровня процедуры  
 Большая часть содержимого *уровня процедуры* элементы, исполняемые операторы, которые составляют код времени выполнения программы. Весь исполняемый код должен быть в какой-либо процедуры (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`). Дополнительные сведения см. в разделе [инструкции](../../../visual-basic/programming-guide/language-features/statements.md).  
  
 Элементы данных на уровне процедуры ограничиваются локальные переменные и константы.  
  
## <a name="the-main-procedure"></a>Основная процедура  
 `Main` Процедура — это первый код для запуска при загрузке приложения. `Main`служит в качестве начальной точки и общего управления для приложения. Существует четыре вида `Main`:  
  
-   `Sub Main()`  
  
-   `Sub Main(ByVal cmdArgs() As String)`  
  
-   `Function Main() As Integer`  
  
-   `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 Наиболее распространенный вид данной процедуры — `Sub Main()`. Дополнительные сведения см. в разделе [процедура Main в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).  
  
## <a name="see-also"></a>См. также  
 [Процедура Main в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)   
 [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [Ограничения в Visual Basic](../../../visual-basic/programming-guide/program-structure/limitations.md)
