---
title: Dim - оператор
ms.date: 05/12/2018
f1_keywords:
- vb.Dim
- Dim
helpviewer_keywords:
- Public keyword [Visual Basic], in Dim statement
- Dim statement [Visual Basic]
- fixed-length strings [Visual Basic], declaring
- variables [Visual Basic], declaring
- WithEvents keyword [Visual Basic], Dim statement
- dynamic arrays [Visual Basic], Dim statement
- variables [Visual Basic], initializing
- '{} braces'
- fields [Visual Basic], as member variables
- declarations [Visual Basic], dynamic arrays
- member variables [Visual Basic]
- default values [Visual Basic]
- data types [Visual Basic], assigning
- braces {}
- As keyword [Visual Basic], in Dim statement
- arrays [Visual Basic], declaring
- New keyword [Visual Basic], Dim statement
- To keyword [Visual Basic], in Dim statement
- storage [Visual Basic], allocating
- local variables [Visual Basic]
- declaration statements [Visual Basic]
- Dim statement [Visual Basic], syntax
- variables [Visual Basic], member and local
ms.assetid: fae3eca1-f0b2-4400-994b-7aa58a848448
ms.openlocfilehash: 1b0c3089c366c417af926c8c0703cea021674432
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744722"
---
# <a name="dim-statement-visual-basic"></a>Оператор Dim (Visual Basic)

Объявляет и выделяет дисковое пространство для одной или нескольких переменных.

## <a name="syntax"></a>Синтаксис

```vb
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]
Dim [ WithEvents ] variablelist
```

## <a name="parts"></a>Компоненты

- `attributelist`

  Необязательный параметр. См. [список атрибутов](attribute-list.md).

- `accessmodifier`

  Необязательный параметр. Может применяться один из перечисленных ниже типов.

  - [Открытый](../modifiers/public.md)

  - [Protected](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [Частное](../modifiers/private.md)

  - [Protected Friend](../modifiers/protected-friend.md)

  - [Private Protected](../modifiers/private-protected.md)

  См. раздел [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

- `Shared`

  Необязательный параметр. См. раздел [Shared](../modifiers/shared.md).

- `Shadows`

  Необязательный параметр. См. раздел [Shadows](../modifiers/shadows.md).

- `Static`

  Необязательный параметр. См. раздел [static](../modifiers/static.md).

- `ReadOnly`

  Необязательный параметр. См. раздел [ReadOnly](../modifiers/readonly.md).

- `WithEvents`

  Необязательный параметр. Указывает, что это переменные объекта, которые ссылаются на экземпляры класса, которые могут создавать события. См. раздел [WithEvents](../modifiers/withevents.md).

- `variablelist`

  Обязательный элемент. Список переменных, объявляемых в этой инструкции.

  `variable [ , variable ... ]`

  Каждый элемент `variable` имеет перечисленные ниже синтаксис и компоненты.

  `variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`

  |Часть|Description|
  |---|---|
  |`variablename`|Обязательный элемент. Имя переменной. См. раздел [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|
  |`boundslist`|Необязательный параметр. Список границ каждого измерения переменной массива.|
  |`New`|Необязательный параметр. Создает новый экземпляр класса при выполнении инструкции `Dim`.|
  |`datatype`|Необязательный параметр. Тип данных переменной.|
  |`With`|Необязательный параметр. Представляет список инициализаторов объектов.|
  |`propertyname`|Необязательный параметр. Имя свойства в классе, экземпляр которого вы вносите.|
  |`propinitializer`|Требуется после `propertyname` =. Выражение, которое вычисляется и присваивается имени свойства.|
  |`initializer`|Необязательный, если не указан `New`. Выражение, которое вычисляется и присваивается переменной при ее создании.|

## <a name="remarks"></a>Remarks

Компилятор Visual Basic использует инструкцию `Dim` для определения типа данных переменной и других сведений, например кода, который может получить доступ к переменной. В следующем примере объявляется переменная для хранения `Integer` значения.

```vb
Dim numberOfStudents As Integer
```

Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.

```vb
Dim finished As Boolean
Dim monitorBox As System.Windows.Forms.Form
```

Для ссылочного типа используется ключевое слово `New` для создания нового экземпляра класса или структуры, определяемой типом данных. Если используется `New`, выражение инициализатора не используется. Вместо этого вы предоставляете аргументы, если они требуются, в конструктор класса, из которого создается переменная.

```vb
Dim bottomLabel As New System.Windows.Forms.Label
```

Переменную можно объявить в процедуре, блоке, классе, структуре или модуле. Нельзя объявить переменную в исходном файле, пространстве имен или интерфейсе. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).

Переменная, объявленная на уровне модуля вне любой процедуры, является переменной или *полем* *члена* . Переменные членов находятся в области действия класса, структуры или модуля. Переменная, объявленная на уровне процедуры, является *локальной переменной*. Локальные переменные находятся в области действия только в пределах их процедуры или блока.

Следующие модификаторы доступа используются для объявления переменных вне процедуры: `Public`, `Protected`, `Friend`, `Protected Friend`и `Private`. Дополнительные сведения см. [в разделе уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

Ключевое слово `Dim` является необязательным и обычно опускается при указании любого из следующих модификаторов: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`или `WithEvents`.

```vb
Public maximumAllowed As Double
Protected Friend currentUserName As String
Private salary As Decimal
Static runningTotal As Integer
```

Если `Option Explicit` имеет значение On (значение по умолчанию), компилятору требуется объявление для каждой используемой переменной. Дополнительные сведения см. в разделе [оператор Option Explicit](option-explicit-statement.md).

## <a name="specifying-an-initial-value"></a>Указание начального значения

При создании переменной можно присвоить значение. Для типа значения используйте *инициализатор* , чтобы указать выражение, присваиваемое переменной. Результатом вычисления выражения должно быть константа, которую можно вычислить во время компиляции.

```vb
Dim quantity As Integer = 10
Dim message As String = "Just started"
```

Если инициализатор указан и тип данных не указан в предложении `As`, *Определение* типа используется для получения типа данных из инициализатора. В следующем примере и `num1`, и `num2` строго типизированы как целые числа. Во втором объявлении определение типа выводит тип из значения 3.

```vb
' Use explicit typing.
Dim num1 As Integer = 3

' Use local type inference.
Dim num2 = 3
```

Определение типа применяется на уровне процедуры. Он не применяется за пределами процедуры в классе, структуре, модуле или интерфейсе. Дополнительные сведения о выводе типа см. в разделе [Option Infer](option-infer-statement.md) и [определение локального типа](../../programming-guide/language-features/variables/local-type-inference.md).

Сведения о том, что происходит, если не указан тип данных или инициализатор, см. в подразделе [типы данных и значения по умолчанию](dim-statement.md#default) далее в этой статье.

*Инициализатор объекта* можно использовать для объявления экземпляров именованных и анонимных типов. Следующий код создает экземпляр класса `Student` и использует инициализатор объекта для инициализации свойств.

```vb
Dim student1 As New Student With {.First = "Michael",
                                  .Last = "Tucker"}
```

Дополнительные сведения об инициализаторах объектов см. [в разделе как объявить объект с помощью инициализатора](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)объекта, [инициализаторов объектов: именованные и анонимные типы](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)и [анонимные типы](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).

## <a name="declaring-multiple-variables"></a>Объявление нескольких переменных

Можно объявить несколько переменных в одном операторе объявления, указав имя переменной для каждой из них, и после каждого имени массива с круглыми скобками. Переменные разделяются запятыми.

```vb
Dim lastTime, nextTime, allTimes() As Date
```

Если объявить более одной переменной с одним предложением `As`, вы не сможете предоставить инициализатор для этой группы переменных.

Можно указать различные типы данных для разных переменных, используя отдельное предложение `As` для каждой объявляемой переменной. Каждая переменная принимает тип данных, указанный в первом предложении `As`, обнаруженном после его части `variablename`.

```vb
Dim a, b, c As Single, x, y As Double, i As Integer
' a, b, and c are all Single; x and y are both Double
```

## <a name="arrays"></a>Массивы

Можно объявить переменную для хранения *массива*, который может содержать несколько значений. Чтобы указать, что переменная содержит массив, следует следовать его `variablename` сразу же с круглыми скобками. Дополнительные сведения см. в руководстве по работе с [массивами](../../programming-guide/language-features/arrays/index.md).

Можно указать нижнюю и верхнюю границы каждого измерения массива. Для этого включите `boundslist` в круглые скобки. Для каждого измерения `boundslist` указывает верхнюю границу и, при необходимости, нижнюю границу. Нижняя граница всегда равна нулю, независимо от того, указана она или нет. Каждый индекс может изменяться от нуля до значения его верхней границы.

Следующие две инструкции эквивалентны. Каждый оператор объявляет массив из 21 `Integer` элементов. При доступе к массиву индекс может изменяться от 0 до 20.

```vb
Dim totals(20) As Integer
Dim totals(0 To 20) As Integer
```

В следующей инструкции объявляется двухмерный массив типа `Double`. Массив содержит 4 строки (3 + 1) из 6 столбцов (5 + 1) каждого. Обратите внимание, что верхняя граница представляет наибольшее возможное значение индекса, а не длину измерения. Длина измерения является верхней границей плюс единица.

```vb
Dim matrix2(3, 5) As Double
```

Массив может иметь размер от 1 до 32.

Все границы в объявлении массива можно оставить пустыми. В этом случае массив имеет указанное число измерений, но не инициализировано. Он имеет значение `Nothing`, пока не будут инициализированы хотя бы некоторые его элементы. В операторе `Dim` должны быть указаны границы для всех измерений или для отсутствия измерений.

```vb
' Declare an array with blank array bounds.
Dim messages() As String
' Initialize the array.
ReDim messages(4)
```

Если массив имеет более одного измерения, необходимо включить запятые между круглыми скобками, чтобы указать количество измерений.

```vb
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte
```

Можно объявить *массив нулевой длины* , объявляя один из измерений массива равным-1. Переменная, содержащая массив нулевой длины, не имеет значения `Nothing`. Для некоторых функций среды CLR требуются массивы нулевой длины. При попытке доступа к такому массиву возникает исключение времени выполнения. Дополнительные сведения см. в статье [Arrays (C++/CLI and C++/CX)](../../programming-guide/language-features/arrays/index.md) (Массивы (C++/CLI и C++/CX)).

Значения массива можно инициализировать с помощью литерала массива. Для этого заключите значения инициализации в фигурные скобки (`{}`).

```vb
Dim longArray() As Long = {0, 1, 2, 3}
```

Для многомерных массивов инициализация каждого отдельного измерения заключается в фигурные скобки во внешнем измерении. Элементы задаются в построчном порядке.

```vb
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}
```

Дополнительные сведения о литералах массивов см. в разделе [массивы](../../programming-guide/language-features/arrays/index.md).

## <a name="default"></a>Типы данных и значения по умолчанию

В следующей таблице перечислены результаты различных сочетаний заданных типов данных и инициализаторов в операторе `Dim`.

|Указан тип данных?|Указан инициализатор?|Пример|Результат|
|---|---|---|---|
|нет|нет|`Dim qty`|Если [параметр optioned](option-strict-statement.md) имеет значение OFF (значение по умолчанию), то переменной присваивается значение `Nothing`.<br /><br /> Если параметр `Option Strict` включен, возникает ошибка времени при компиляции.|
|нет|Да|`Dim qty = 5`|Если [параметр Infer](option-infer-statement.md) имеет значение On (значение по умолчанию), переменная принимает тип данных инициализатора. См. раздел [определение локального типа](../../programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Если параметры `Option Infer` и `Option Strict` отключены, переменная получает тип данных `Object`.<br /><br /> Если параметр `Option Infer` отключен, а параметр `Option Strict` включен, возникает ошибка времени компиляции.|
|Да|нет|`Dim qty As Integer`|Переменная инициализируется со значением по умолчанию для типа данных. См. таблицу далее в этом разделе.|
|Да|Да|`Dim qty  As Integer = 5`|Если тип данных инициализатора нельзя преобразовать в указанный тип данных, возникает ошибка времени компиляции.|

Если указать тип данных, но не указать инициализатор, Visual Basic инициализирует переменную как значение по умолчанию для ее типа данных. В следующей таблице приведены значения инициализации по умолчанию.

|Тип данных|Значение по умолчанию|
|---|---|
|Все числовые типы (включая `Byte` и `SByte`)|0|
|`Char`|Двоичный 0|
|Все ссылочные типы (включая `Object`, `String`и все массивы)|`Nothing`|
|`Boolean`|`False`|
|`Date`|12:00 AM 1 января 1 года (01/01/0001 12:00:00 AM)|

Каждый элемент структуры инициализируется так, как если бы он был отдельной переменной. Если вы объявили длину массива, но не инициализируйте его элементы, каждый элемент инициализируется так, как если бы он был отдельной переменной.

## <a name="static-local-variable-lifetime"></a>Время существования статической локальной переменной

`Static` локальная переменная имеет более длительное время существования, чем процедура, в которой она объявлена. Границы времени существования переменной зависят от того, где была объявлена процедура и является ли она `Shared`ой.

|Объявление процедуры|Переменная инициализирована|Переменная останавливается|
|---|---|---|
|В модуле|При первом вызове процедуры|При остановке выполнения программы|
|В классе или структуре процедура `Shared`|При первом вызове процедуры либо в определенном экземпляре, либо в самом классе или структуре.|При остановке выполнения программы|
|В классе или структуре процедура не `Shared`|При первом вызове процедуры в определенном экземпляре|Когда экземпляр выпускается для сборки мусора (GC)|

## <a name="attributes-and-modifiers"></a>Атрибуты и модификаторы

Атрибуты можно применять только к переменным члена, а не к локальным переменным. Атрибут вносит сведения в метаданные сборки, что не имеет смысла для временного хранения, например локальных переменных.

На уровне модуля нельзя использовать модификатор `Static` для объявления переменных члена. На уровне процедуры нельзя использовать `Shared`, `Shadows`, `ReadOnly`, `WithEvents`или модификаторы доступа для объявления локальных переменных.

Можно указать, какой код может получить доступ к переменной, указав `accessmodifier`. Переменные-члены класса и модуля (вне любой процедуры) по умолчанию имеют частный доступ, а переменные-члены структуры по умолчанию имеют общий доступ. Уровни доступа можно изменить с помощью модификаторов доступа. Нельзя использовать модификаторы доступа для локальных переменных (внутри процедуры).

Можно указать `WithEvents` только для переменных-членов, но не для локальных переменных внутри процедуры. При указании `WithEvents`тип данных переменной должен быть конкретным типом класса, а не `Object`. Нельзя объявить массив с `WithEvents`. Дополнительные сведения о событиях см. в разделе [события](../../programming-guide/language-features/events/index.md).

> [!NOTE]
> Код за пределами класса, структуры или модуля должен уточнять имя переменной-члена именем этого класса, структуры или модуля. Код за пределами процедуры или блока не может ссылаться на локальные переменные в этой процедуре или блоке.

## <a name="releasing-managed-resources"></a>Освобождение управляемых ресурсов

Сборщик мусора .NET Framework уничтожает управляемые ресурсы без дополнительного программирования. Однако можно вызвать принудительное удаление управляемого ресурса вместо ожидания сборщика мусора.

Если класс принадлежит особому ценному и ограниченному ресурсу (например, к подключению к базе данных или файлу), может возникнуть необходимость в ожидании следующей сборки мусора для очистки экземпляра класса, который больше не используется. Класс может реализовывать интерфейс <xref:System.IDisposable>, чтобы предоставить способ освобождения ресурсов перед сборкой мусора. Класс, реализующий этот интерфейс, предоставляет метод `Dispose`, который может быть вызван для немедленного освобождения ценных ресурсов.

Инструкция `Using` автоматизирует процесс получения ресурса, выполнения набора инструкций и последующего удаления ресурса. Однако ресурс должен реализовывать интерфейс <xref:System.IDisposable>. Дополнительные сведения см. в разделе [Оператор using](using-statement.md).

## <a name="example"></a>Пример

В следующем примере переменные объявляются с помощью оператора `Dim` с различными параметрами.

[!code-vb[VbVbalrStatements#141](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#141)]

## <a name="example"></a>Пример

В следующем примере выводятся простые числа от 1 до 30. Область локальных переменных описывается в разделе Комментарии к коду.

[!code-vb[VbVbalrStatements#142](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#142)]

## <a name="example"></a>Пример

В следующем примере переменная `speedValue` объявляется на уровне класса. Ключевое слово `Private` используется для объявления переменной. Доступ к переменной может осуществляться любой процедурой в классе `Car`.

[!code-vb[VbVbalrStatements#144](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#144)]

[!code-vb[VbVbalrStatements#145](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#145)]

## <a name="see-also"></a>См. также раздел

- [Оператор Const](const-statement.md)
- [Оператор reDim](redim-statement.md)
- [Оператор Option Explicit](option-explicit-statement.md)
- [Оператор Option Infer](option-infer-statement.md)
- [Оператор Option Strict](option-strict-statement.md)
- [Страница "Компиляция" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [Объявление переменных](../../programming-guide/language-features/variables/variable-declaration.md)
- [Массивы](../../programming-guide/language-features/arrays/index.md)
- [Инициализаторы объектов. Именованные и анонимные типы](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Анонимные типы](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Инициализаторы объектов. Именованные и анонимные типы](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Практическое руководство. Объявление объекта с помощью инициализатора объектов](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
- [Вывод локального типа](../../programming-guide/language-features/variables/local-type-inference.md)
