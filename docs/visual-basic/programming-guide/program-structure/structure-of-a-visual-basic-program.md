---
title: Структура программы Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- conditional compilation [Visual Basic], Visual Basic
- program structure [Visual Basic], Visual Basic
- procedures [Visual Basic], structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5def0de1e22af39eb16489a2d4d27bdbd1853f2b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="structure-of-a-visual-basic-program"></a>Структура программы Visual Basic
Программа Visual Basic построена из стандартных блоков. Объект *решения* состоит из одного или нескольких проектов. Объект *проекта* в свою очередь может содержать одну или несколько сборок. Каждый *сборки* компилируется из одного или нескольких исходных файлов. Объект *исходный файл* содержит определения и реализации классов, структур, модули и интерфейсы, которые в конечном счете содержит весь код.  
  
 Дополнительные сведения об этих стандартных блоках программы на Visual Basic см. в разделе [решения и проекты](/visualstudio/ide/solutions-and-projects-in-visual-studio) и [сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).  
  
## <a name="file-level-programming-elements"></a>Элементы программирования уровня файла  
 При запуске проекта или файла и открыть редактор кода, вы видите часть кода, имеющуюся в правильном порядке. Любой код, написанный должны создаваться в следующей последовательности:  
  
1.  `Option` Инструкции  
  
2.  `Imports` Инструкции  
  
3.  `Namespace` инструкции и элементы уровня пространства имен  
  
 Введите инструкции в другом порядке, может привести к ошибкам компиляции.  
  
 Программа также может содержать операторы условной компиляции. Можно соединять, их в исходном файле среди инструкций предыдущей последовательности.  
  
### <a name="option-statements"></a>Параметры инструкции  
 `Option` Операторы устанавливают основные правила для последующего кода, способствуя предотвращению синтаксических и логических ошибок. [Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md) гарантирует, что все переменные объявляются и написаны правильно, что сокращает время отладки. [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) позволяет свести к минимуму потерю ошибок и данных логику, которая может возникнуть при работе с переменными различных типов данных. [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) указывает способа сравнения строк друг с другом на основе их `Binary` или `Text` значения.  
  
### <a name="imports-statements"></a>Оператор Imports  
 Можно включить [оператор Imports (пространство имен .NET и тип)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) для импорта имена, определенные вне проекта. `Imports` Оператор разрешает коде для ссылки на классы и другие типы, определенные в импортированном пространстве имен без их уточнения. Можно использовать любое количество `Imports` соответствующих операторов. Дополнительные сведения см. в разделе [ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md).  
  
### <a name="namespace-statements"></a>Операторы пространств имен  
 Пространства имен помогают организовывать и классифицировать элементы программирования для упрощения группирования и доступ к. Вы используете [оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md) для классификации следующих операторов в определенном пространстве имен. Дополнительные сведения см. в разделе [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
### <a name="conditional-compilation-statements"></a>Операторы условной компиляции  
 Операторы условной компиляции могут использоваться практически в любом месте в файле исходного кода. Они смогут причинить части кода нужно включить или исключить во время компиляции в зависимости от определенных условий. Вы также их можно использовать для отладки приложения, поскольку условный код выполняется только в режиме отладки. Дополнительные сведения см. в разделе [условной компиляции](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md).  
  
## <a name="namespace-level-programming-elements"></a>Элементы программирования уровня пространства имен  
 Классы, структуры и модули содержат весь код в файле исходного кода. Они являются *уровня пространства имен* элементы, которые могут отображаться в пространстве имен или на уровне исходного файла. Они содержат описания всех элементов программирования. Интерфейсы, которые определяют подписи элементов, но не выполняют реализацию, также отображаются на уровне модуля. Дополнительные сведения об элементах уровня модуля см.  
  
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
  
 Элементы данных на уровне модуля, переменные, константы, перечисления и делегаты.  
  
## <a name="procedure-level-programming-elements"></a>Элементы программирования уровня процедуры  
 Большая часть содержимого *уровня процедуры* элементы, исполняемые операторы, которые составляют код времени выполнения программы. Весь код, исполняемый файл должен быть в некоторой процедуры (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`). Дополнительные сведения см. в разделе [Выписки](../../../visual-basic/programming-guide/language-features/statements.md).  
  
 Элементы данных на уровне процедуры ограничиваются локальных переменных и констант.  
  
## <a name="the-main-procedure"></a>Основная процедура  
 `Main` Процедура — это первый код для выполнения при загрузке приложения. `Main` служит в качестве начальной точки и общего управления для приложения. Существуют четыре вида `Main`:  
  
-   `Sub Main()`  
  
-   `Sub Main(ByVal cmdArgs() As String)`  
  
-   `Function Main() As Integer`  
  
-   `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 Наиболее распространенный этой процедуры является `Sub Main()`. Дополнительные сведения см. в разделе [процедура Main в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).  
  
## <a name="see-also"></a>См. также  
 [Процедура Main в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [Ограничения в Visual Basic](../../../visual-basic/programming-guide/program-structure/limitations.md)
