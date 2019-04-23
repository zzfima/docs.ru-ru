---
title: Структура программы Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], Visual Basic
- program structure [Visual Basic], Visual Basic
- procedures [Visual Basic], structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
ms.openlocfilehash: 42e366a844f9c5e80a8f617bf73dfd869608540d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295774"
---
# <a name="structure-of-a-visual-basic-program"></a>Структура программы Visual Basic
Программы на Visual Basic — это результат из стандартных блоков. Объект *решение* состоит из одного или нескольких проектов. Объект *проекта* в свою очередь может содержать одну или несколько сборок. Каждый *сборки* компилируется из одного или нескольких исходных файлов. Объект *исходный файл* предоставляет определение и реализацию классов, структур, модулей и интерфейсов, которые в конечном счете содержит весь код.  
  
 Дополнительные сведения о эти блоки программы на Visual Basic, см. в разделе [решения и проекты](/visualstudio/ide/solutions-and-projects-in-visual-studio) и [сборок в .NET](../../../standard/assembly/index.md).  
  
## <a name="file-level-programming-elements"></a>Элементы программирования на уровне файлов  
 При запуске проекта или файла и открыть редактор кода, вы увидите некоторые код уже на месте и в правильном порядке. Любой код, написанный следует придерживаться следующей последовательности:  
  
1. `Option` Инструкции  
  
2. `Imports` Инструкции  
  
3. `Namespace` инструкции и элементы уровня пространства имен  
  
 При вводе инструкций в другом порядке, это может привести к ошибкам компиляции.  
  
 Программа также может содержать операторы условной компиляции. Вы можете перемежать их в файле источника вместе предыдущей последовательности.  
  
### <a name="option-statements"></a>Параметры инструкции  
 `Option` Инструкции устанавливают основные правила для последующего кода, помогая избежать синтаксических и логических ошибок. [Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md) гарантирует, что все переменные объявлены и написаны правильно, что уменьшает время при отладке. [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) помогает свести к минимуму логики ошибки и потери данных, может возникнуть при работе с переменными разных типов данных. [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) указывает способа сравнения строк друг с другом, на основе их `Binary` или `Text` значения.  
  
### <a name="imports-statements"></a>Операторы Imports  
 Можно включить [оператор Imports (пространство имен .NET и тип)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) импортировать имена, определенные вне данного проекта. `Imports` Инструкция позволяет ссылаться на классы и другие типы, определенные в импортированном пространстве имен, не определяя их код. Можно использовать любое количество `Imports` инструкций соответствующим образом. Дополнительные сведения см. в разделе [ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md).  
  
### <a name="namespace-statements"></a>Операторы пространства имен  
 Пространства имен помогают организовать и классифицировать элементы программирования для упрощения группирования и доступ к ним. Использовании [оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md) для классификации следующие инструкции в пределах определенного пространства имен. Дополнительные сведения см. в разделе [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
### <a name="conditional-compilation-statements"></a>Операторы условной компиляции  
 Условная компиляция операторы могут использоваться в любом месте в файле исходного кода. Они смогут нанести части кода нужно включить или исключить во время компиляции в зависимости от определенных условий. Вы также их можно использовать для отладки приложения, поскольку условный код выполняется только в режиме отладки. Дополнительные сведения см. в разделе [условной компиляции](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md).  
  
## <a name="namespace-level-programming-elements"></a>Элементы программирования уровня пространства имен  
 Классы, структуры и модули содержат весь код в файле исходного кода. Они являются *уровня пространства имен* элементы, которые могут отображаться в пространстве имен или на уровне файла источника. Они содержат описания всех других элементов программирования. Интерфейсы, которые определяют подписи элементов, но не выполняют реализацию, также отображаются на уровне модуля. Дополнительные сведения об элементах на уровне модуля см. в разделе ниже:  
  
-   [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
-   [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)  
  
-   [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 Элементы данных на уровне пространства имен, перечисления и делегаты.  
  
## <a name="module-level-programming-elements"></a>Элементы программирования уровня модуля  
 Процедуры, операторы, свойства и события являются единственными элементами программирования, которые могут содержать исполняемый код (инструкции, которые выполняют действия во время выполнения). Они являются *уровня модуля* элементы программы. Дополнительные сведения об элементах уровня процедуры см. в разделе ниже:  
  
-   [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
-   [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 Элементы данных на уровне модуля являются переменные, константы, перечисления и делегаты.  
  
## <a name="procedure-level-programming-elements"></a>Элементы программирования на уровне процедуры  
 Большая часть содержимого *уровня процедуры* элементы являются исполняемые операторы, которые составляют код времени выполнения программы. Весь исполняемый код должен быть в какую-либо процедуру (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`). Дополнительные сведения см. в разделе [Выписки](../../../visual-basic/programming-guide/language-features/statements.md).  
  
 Элементы данных на уровне процедуры ограничены локальных переменных и констант.  
  
## <a name="the-main-procedure"></a>Основная процедура  
 `Main` Процедура — это первый код для запуска при загрузке приложения. `Main` служит в качестве отправной точки и возможностей управления для вашего приложения. Существует четыре разновидности `Main`:  
  
-   `Sub Main()`  
  
-   `Sub Main(ByVal cmdArgs() As String)`  
  
-   `Function Main() As Integer`  
  
-   `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 Наиболее распространенный вид этой процедуры является `Sub Main()`. Дополнительные сведения см. в разделе [процедура Main в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).  
  
## <a name="see-also"></a>См. также

- [Процедура Main в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
- [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [Ограничения в Visual Basic](../../../visual-basic/programming-guide/program-structure/limitations.md)
