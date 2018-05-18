---
title: Оператор Dim (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: c051572e83b915346d48ec12fb5d97f77b47e4c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="dim-statement-visual-basic"></a>Оператор Dim (Visual Basic)
Объявляет и выделяет место для одной или нескольких переменных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]   
Dim [ WithEvents ] variablelist  
```  
  
## <a name="parts"></a>Части  
  
-   `attributelist`  
  
     Необязательный. В разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
-   `accessmodifier`  
  
     Необязательный. Ниже указаны доступные значения.  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     В разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `Shared`  
  
     Необязательный. В разделе [общих](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Необязательный. В разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `Static`  
  
     Необязательный. В разделе [статических](../../../visual-basic/language-reference/modifiers/static.md).  
  
-   `ReadOnly`  
  
     Необязательный. В разделе [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
-   `WithEvents`  
  
     Необязательный. Указывает, что они объектные переменные, которые ссылаются на экземпляры класса, который может порождать события. В разделе [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).  
  
-   `variablelist`  
  
     Обязательно. Список переменных, объявляемых в этом операторе.  
  
     `variable [ , variable ... ]`  
  
     Каждый элемент `variable` имеет перечисленные ниже синтаксис и компоненты.  
  
     `variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`  
  
    |Отделение|Описание|  
    |---|---|  
    |`variablename`|Обязательно. Имя переменной. В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
    |`boundslist`|Необязательный. Список границ для каждого измерения массива.|  
    |`New`|Необязательный. Создает новый экземпляр класса при `Dim` выполняется инструкция.|  
    |`datatype`|Необязательный. Тип данных переменной.|  
    |`With`|Необязательный. Появился в списке инициализаторов объекта.|  
    |`propertyname`|Необязательный. Имя свойства в классе становится экземпляром.|  
    |`propinitializer`|После `propertyname` =. Выражение, которое является вычисляется и присваивается имя свойства.|  
    |`initializer`|Необязательный, если `New` не указан. Выражение, которое вычисляется и присваивается переменной при ее создании.|  
  
## <a name="remarks"></a>Примечания  
 Компилятор Visual Basic использует `Dim` инструкцию, чтобы определить тип данных переменной и другие сведения, например, какой код может обращаться к переменной. В следующем примере объявляется переменная для хранения `Integer` значение.  
  
```vb  
Dim numberOfStudents As Integer  
```  
  
 Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.  
  
```vb  
Dim finished As Boolean  
Dim monitorBox As System.Windows.Forms.Form  
```  
  
 Для ссылочного типа, используйте `New` указано ключевое слово для создания нового экземпляра класса или структуры, для типа данных. Если вы используете `New`, тип выражения инициализатора не используется. Вместо этого аргументы, если они требуются, чтобы конструктор класса, из которого создается переменная.  
  
```vb  
Dim bottomLabel As New System.Windows.Forms.Label  
```  
  
 Можно объявить переменную в процедуре, блок, класса, структуры или модуля. Невозможно объявить переменную в исходный файл, пространство имен или интерфейс. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Переменная, объявленная на уровне модуля, вне любой процедуры — *переменной-члена* или *поля*. Переменные-члены находятся в области всего их класса, структуры или модуля. Переменная, объявленная на уровне процедуры — *локальной переменной*. Локальные переменные находятся в области действия только в пределах их процедуры или блока.  
  
 Следующие модификаторы доступа используются для объявления переменных вне процедуры: `Public`, `Protected`, `Friend`, `Protected Friend`, и `Private`. Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `Dim` Ключевое слово является необязательным и обычно указывается, если указать один из следующих модификаторов: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, или `WithEvents`.  
  
```vb  
Public maximumAllowed As Double  
Protected Friend currentUserName As String  
Private salary As Decimal  
Static runningTotal As Integer  
```  
  
 Если `Option Explicit` является on (по умолчанию), компилятор требует объявления для каждой переменной можно использовать. Дополнительные сведения см. в разделе [оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md).  
  
## <a name="specifying-an-initial-value"></a>Указание начального значения  
 Можно назначить значение переменной при ее создании. Для типа значения используйте *инициализатора* позволяет указать выражение, назначаемое переменной. Выражение должно возвращать константой, может быть вычислено во время компиляции.  
  
```vb  
Dim quantity As Integer = 10  
Dim message As String = "Just started"  
```  
  
 Если указан инициализатор и тип данных не указан в `As` предложение, *вывод типа* используется для определения типа данных из инициализатора. В следующем примере оба `num1` и `num2` являются строго типизированными как целые числа. Во втором объявлении определения типов определяет тип значение 3.  
  
```vb  
' Use explicit typing.  
Dim num1 As Integer = 3  
  
' Use local type inference.  
Dim num2 = 3  
```  
  
 Определение типов применяется на уровне процедуры. Не применяется вне процедур в класс, структура, модуль или интерфейс. Дополнительные сведения о выводе типа см. в разделе [Option Infer-оператор](../../../visual-basic/language-reference/statements/option-infer-statement.md) и [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
 Сведения о том, что происходит, когда не указан тип данных или инициализатор в разделе [по умолчанию типы данных и значения](../../../visual-basic/language-reference/statements/dim-statement.md#default) далее в этом разделе.  
  
 Можно использовать *инициализатора объекта* объявлять экземпляров именованные и анонимные типы. Следующий код создает экземпляр `Student` класса и использует инициализатора объекта для инициализации свойств.  
  
```vb  
Dim student1 As New Student With {.First = "Michael",   
                                  .Last = "Tucker"}  
```  
  
 Дополнительные сведения об инициализаторах объектов см. в разделе [как: объявление объекта с помощью инициализатора объектов](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [инициализаторы объектов: именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), и [анонимные типы ](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="declaring-multiple-variables"></a>Объявление нескольких переменных  
 Можно объявить несколько переменных в одном операторе объявления, указав имя переменной для каждого из них и имя массива в скобки. Переменные разделяются запятыми.  
  
```vb  
Dim lastTime, nextTime, allTimes() As Date  
```  
  
 Если объявляется несколько переменных с одним `As` предложение, невозможно указать инициализатор для этой группы переменных.  
  
 Можно указать различные типы данных для переменных с помощью отдельных `As` предложение для каждой объявляемой переменной. Каждая переменная имеет тип данных, указанный в первом `As` предложение возникли после его `variablename` части.  
  
```vb  
Dim a, b, c As Single, x, y As Double, i As Integer  
' a, b, and c are all Single; x and y are both Double  
```  
  
## <a name="arrays"></a>Массивы  
 Можно объявить переменную для хранения *массив*, который может содержать несколько значений. Чтобы указать, что переменная содержит массив, выполните его `variablename` немедленно со скобками. Дополнительные сведения о массивах см. в разделе [массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
 Можно указать нижнюю и верхнюю границу для каждого измерения массива. Чтобы сделать это, включите `boundslist` в скобках. Для каждого измерения `boundslist` указывает верхнюю границу и при необходимости нижнюю границу. Нижняя граница всегда равно нулю, задания или нет. Каждый индекс может изменяться от нуля до значения верхней границы.  
  
 Следующие две инструкции эквивалентны. Каждый оператор объявляет массив из 21 `Integer` элементов. При доступе к массива, индекс может изменяться от 0 до 20.  
  
```vb  
Dim totals(20) As Integer  
Dim totals(0 To 20) As Integer  
```  
  
 Следующий оператор объявляет двумерный массив типа `Double`. Массив имеет 4 строки (3 + 1) по 6 столбцов (5 + 1) каждая. Обратите внимание, что верхняя граница представляет наибольшее возможное значение для индекса, но не длину измерения. Длина измерения равна верхней границе плюс один.  
  
```vb  
Dim matrix2(3, 5) As Double  
```  
  
 Массив может быть в диапазоне от 1 до 32 измерений.  
  
 Все границы можно оставить пустым в объявлении массива. После этого массив имеет размерность, указываемые, но он не инициализирован. Он имеет значение `Nothing` до инициализации по крайней мере некоторые из его элементов. `Dim` Инструкции должны быть указаны границы для всех измерений либо измерения не.  
  
```vb  
' Declare an array with blank array bounds.  
Dim messages() As String  
' Initialize the array.  
ReDim messages(4)  
```  
  
 Если массив имеет более одного измерения, необходимо включить запятые заключено в круглые скобки, чтобы указать число измерений.  
  
```vb  
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte  
```  
  
 Можно объявить *массив нулевой длины* , объявив одно из измерений массива равным – 1. Переменная, содержащая массив нулевой длины не имеет значения `Nothing`. Массивы с нулевой длиной необходимы определенные функции среды CLR. При попытке получить доступ к такой массив, возникает исключение времени выполнения. Дополнительные сведения см. в разделе [массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
 Значения массива можно инициализировать с помощью литерала массива. Чтобы сделать это, заключите начальных значений в фигурные скобки (`{}`).  
  
```vb  
Dim longArray() As Long = {0, 1, 2, 3}  
```  
  
 Для многомерных массивов инициализация для каждой отдельной размерности заключается в фигурные скобки внешней размерности. Имена указываются в строках заказа.  
  
```vb  
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}  
```  
  
 Дополнительные сведения о литералах массива см. в разделе [массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
##  <a name="default"></a> Типы данных по умолчанию и значения  
 В следующей таблице перечислены результаты различных сочетаний заданных типов данных и инициализаторов в операторе `Dim`.  
  
|Указан тип данных?|Указан инициализатор?|Пример|Результат|  
|---|---|---|---|  
|Нет|Нет|`Dim qty`|Если [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) — off (по умолчанию), переменная принимает значение `Nothing`.<br /><br /> Если параметр `Option Strict` включен, при компиляции возникает ошибка.|  
|Нет|Да|`Dim qty = 5`|Если [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) включен (по умолчанию), переменная получает тип данных инициализатора. В разделе [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Если параметры `Option Infer` и `Option Strict` отключены, переменная получает тип данных `Object`.<br /><br /> Если параметр `Option Infer` отключен, а параметр `Option Strict` включен, при компиляции возникает ошибка.|  
|Да|Нет|`Dim qty As Integer`|Переменная инициализируется со значением по умолчанию для типа данных. См. в таблице ниже в данном разделе.|  
|Да|Да|`Dim qty  As Integer = 5`|Если тип данных инициализатора нельзя преобразовать в указанный тип данных, возникает ошибка времени компиляции.|  
  
 Если указать тип данных, но не указан инициализатор, Visual Basic инициализирует переменную со значением по умолчанию для своего типа данных. В следующей таблице представлены значения инициализации.  
  
|Тип данных|Значение по умолчанию|  
|---|---|  
|Все числовые типы (включая `Byte` и `SByte`)|0|  
|`Char`|Двоичный 0|  
|Все ссылочные типы (включая `Object`, `String`и все массивы)|`Nothing`|  
|`Boolean`|`False`|  
|`Date`|Полночь 1 января 1 года (01/01/0001 12:00:00 AM)|  
  
 Каждый элемент структуры инициализируется, как если бы он был отдельной переменной. Если объявляется длина массива, но не инициализируются его элементы, каждый элемент инициализируется, как если бы он был отдельной переменной.  
  
## <a name="static-local-variable-lifetime"></a>Время существования статической локальной переменной  
 Объект `Static` локальная переменная имеет дольше процедуры, в котором она объявлена. Пределы существования переменной зависят от того, где объявлен процедуры и является ли оно `Shared`.  
  
|Объявление процедуры|Переменная инициализирована|Переменная прекращает существующие|  
|---|---|---|  
|В модуле|Первый раз при вызове процедуры|Когда программа завершает выполнение|  
|В классе или структуре процедура является `Shared`|Первый раз процедура вызывается на определенном экземпляре или на классе или структуре самой|Когда программа завершает выполнение|  
|В классе или структуре не процедуры `Shared`|При первом запуске при вызове процедуры на определенном экземпляре|Если этот экземпляр освобождается для сборки мусора (GC)|  
  
## <a name="attributes-and-modifiers"></a>Атрибуты и модификаторы  
 Можно применить атрибуты только для переменных-членов, а не к локальным переменным. Атрибут вносит сведения для метаданных сборки, которые не имеют смысла для временного хранения, такие как локальные переменные.  
  
 На уровне модуля нельзя использовать `Static` модификатор для объявления переменных-членов. На уровне процедуры, нельзя использовать `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, или любой доступ модификаторы объявления локальных переменных.  
  
 Можно указать, какой код может обращаться к переменной, указав `accessmodifier`. Класс модуля члены и переменные (вне любых процедур) по умолчанию имеют закрытый доступ, а переменные-члены структуры по умолчанию общий доступ. Вы можете настроить уровни доступа с помощью модификаторов доступа. Невозможно использовать модификаторы доступа для локальных переменных (внутри процедуры).  
  
 Можно указать `WithEvents` только для переменных-членов, но не для локальных переменных в процедуре. При указании `WithEvents`, тип данных переменной должен быть определенный тип класса, не `Object`. Не удается объявить массив с `WithEvents`. Дополнительные сведения о событиях см. в разделе [события](../../../visual-basic/programming-guide/language-features/events/index.md).  
  
> [!NOTE]
>  Код вне класса, структуры или модуля необходимо определять имя переменной-члена с именем этого класса, структуры или модуля. Код за пределами процедуры или блока не может ссылаться на любые локальные переменные в рамках этой процедуры или блока.  
  
## <a name="releasing-managed-resources"></a>Освободить управляемые ресурсы.  
 Сборщик мусора .NET Framework без дополнительного кодирования с вашей стороны освобождает управляемые ресурсы. Тем не менее можно принудительно при реализации управляемых ресурсов, а не ждет, пока сборщик мусора.  
  
 Если класс удерживает особо ценный и редкий ресурс (например, дескриптор соединения или файла базы данных), может не потребоваться дождаться следующей сборки мусора для очистки экземпляра класса, который больше не используется. Класс может реализовывать <xref:System.IDisposable> интерфейс предоставляет способ освободить ресурсы перед сборкой мусора. Класс, реализующий этот интерфейс предоставляет `Dispose` метод, который можно вызвать, чтобы принудительно ценных ресурсов освобождается сразу.  
  
 `Using` Инструкция автоматизирует процесс получения ресурса, выполнение набора операторов и последующего освобождения ресурса. Тем не менее, необходимо реализовать ресурса <xref:System.IDisposable> интерфейса. Дополнительные сведения см. в разделе [Оператор using](../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="example"></a>Пример  
 В следующем примере объявляется переменных с помощью `Dim` инструкции с различными параметрами.  
  
 [!code-vb[VbVbalrStatements#141](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_1.vb)]  
  
## <a name="example"></a>Пример  
 Приведенный ниже список простых чисел от 1 до 30. Область локальных переменных, описывается в комментариях к коду.  
  
 [!code-vb[VbVbalrStatements#142](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_2.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере `speedValue` переменная, объявленная на уровне класса. `Private` Ключевое слово используется для объявления переменной. Переменная может осуществляться в любую процедуру `Car` класса.  
  
 [!code-vb[VbVbalrStatements#144](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#145](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_4.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md)  
 [Оператор reDim](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [Оператор Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Страница "Компиляция" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)  
 [Объявление переменных](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Инициализаторы объектов. Именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Инициализаторы объектов. Именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Практическое руководство. Объявление объекта с помощью инициализатора объектов](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)  
 [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
