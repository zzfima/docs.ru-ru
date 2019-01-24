---
title: Оператор Dim (Visual Basic)
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
ms.openlocfilehash: 487e2ff55f256bc06a463043dd2849a404eb82cd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567741"
---
# <a name="dim-statement-visual-basic"></a>Оператор Dim (Visual Basic)
Объявляет и выделяет область хранения для одной или нескольких переменных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]   
Dim [ WithEvents ] variablelist  
```  
  
## <a name="parts"></a>Части  
  
-   `attributelist`  
  
     Необязательный параметр. См. в разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
-   `accessmodifier`  
  
     Необязательный параметр. Ниже указаны доступные значения.  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   [Protected Friend](../../language-reference/modifiers/protected-friend.md)
    
    - [Private Protected](../../language-reference/modifiers/private-protected.md)

     См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `Shared`  
  
     Необязательный параметр. См. в разделе [общих](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Необязательный параметр. См. в разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `Static`  
  
     Необязательный параметр. См. в разделе [статических](../../../visual-basic/language-reference/modifiers/static.md).  
  
-   `ReadOnly`  
  
     Необязательный параметр. См. в разделе [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
-   `WithEvents`  
  
     Необязательный параметр. Указывает, что они объектные переменные, которые ссылаются на экземпляры класса, который может порождать события. См. в разделе [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).  
  
-   `variablelist`  
  
     Обязательный. Список переменных, объявляемых в этом операторе.  
  
     `variable [ , variable ... ]`  
  
     Каждый элемент `variable` имеет перечисленные ниже синтаксис и компоненты.  
  
     `variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`  
  
    |Отделение|Описание:|  
    |---|---|  
    |`variablename`|Обязательный. Имя переменной. См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
    |`boundslist`|Необязательный параметр. Список границ для каждого измерения массива.|  
    |`New`|Необязательный параметр. Создает новый экземпляр класса при `Dim` выполняется инструкция.|  
    |`datatype`|Необязательный параметр. Тип данных переменной.|  
    |`With`|Необязательный параметр. Представляет список инициализаторов объектов.|  
    |`propertyname`|Необязательный параметр. Имя свойства в классе создании экземпляра.|  
    |`propinitializer`|После `propertyname` =. Выражение, которое вычисляется и назначено имя свойства.|  
    |`initializer`|Необязателен при `New` не указан. Выражение, которое вычисляется и присваивается переменной при ее создании.|  
  
## <a name="remarks"></a>Примечания  
 Компилятор Visual Basic использует `Dim` инструкцию, чтобы определить тип данных переменной и другие сведения, например какой код может обращаться к переменной. В следующем примере объявляется переменная для хранения `Integer` значение.  
  
```vb  
Dim numberOfStudents As Integer  
```  
  
 Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.  
  
```vb  
Dim finished As Boolean  
Dim monitorBox As System.Windows.Forms.Form  
```  
  
 Для ссылочного типа, используйте `New` ключевое слово, чтобы создать новый экземпляр класса или структуры, задается тип данных. Если вы используете `New`, вы не используете выражения инициализатора. Вместо этого аргументы, если они требуются, чтобы конструктор класса, из которого вы создаете переменную.  
  
```vb  
Dim bottomLabel As New System.Windows.Forms.Label  
```  
  
 Можно объявить переменную в процедуре, блок, класса, структуры или модуля. Невозможно объявить переменную в исходный файл, пространство имен или интерфейс. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Является переменной, объявленной на уровне модуля, вне любых процедур *переменной-члена* или *поле*. Переменные-члены находятся в области всего их класса, структуры или модуля. Переменная, объявленная на уровне процедуры, является *локальной переменной*. Локальные переменные находятся в области действия только в их процедуры или блока.  
  
 Следующие модификаторы доступа используются для объявления переменных вне процедуры: `Public`, `Protected`, `Friend`, `Protected Friend`, и `Private`. Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `Dim` Ключевое слово является необязательным и обычно опускается, если указать один из следующих модификаторов: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, или `WithEvents`.  
  
```vb  
Public maximumAllowed As Double  
Protected Friend currentUserName As String  
Private salary As Decimal  
Static runningTotal As Integer  
```  
  
 Если `Option Explicit` является on (по умолчанию), компилятор требует объявления для каждой переменной, можно использовать. Дополнительные сведения см. в разделе [оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md).  
  
## <a name="specifying-an-initial-value"></a>Указание начального значения  
 Можно присвоить значение переменной при ее создании. Для типа значения, используйте *инициализатор* позволяет указать выражение, назначаемое переменной. Выражение должно возвращать константой, может быть вычислено во время компиляции.  
  
```vb  
Dim quantity As Integer = 10  
Dim message As String = "Just started"  
```  
  
 Если указан инициализатор, и тип данных не указан в `As` предложение, *вывод типа* используется для определения типа данных из инициализатора. В следующем примере оба `num1` и `num2` являются строго типизированными как целые числа. Во втором объявлении вывод типа определяет тип значение 3.  
  
```vb  
' Use explicit typing.  
Dim num1 As Integer = 3  
  
' Use local type inference.  
Dim num2 = 3  
```  
  
 Определение типов применяется на уровне процедуры. Он не применяется вне процедур в класс, структура, модуль или интерфейс. Дополнительные сведения о выводе типа см. в разделе [оператор Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) и [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
 Чтобы узнать, что произойдет, если не указан тип данных или инициализатор, см. в разделе [типами данных по умолчанию и значения](../../../visual-basic/language-reference/statements/dim-statement.md#default) далее в этом разделе.  
  
 Можно использовать *инициализатора объекта* для объявления экземпляры именованных и анонимных типов. Следующий код создает экземпляр `Student` класса и использует инициализатор объекта для инициализации свойств.  
  
```vb  
Dim student1 As New Student With {.First = "Michael",   
                                  .Last = "Tucker"}  
```  
  
 Дополнительные сведения об инициализаторах объектов см. в разделе [как: Объявление объекта с помощью инициализатора объектов](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [инициализаторы объектов: Именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), и [анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="declaring-multiple-variables"></a>Объявление нескольких переменных  
 Можно объявить несколько переменных в одном операторе объявления, указав имя переменной для каждого из них, а также имя массива в круглые скобки. Переменные разделяются запятыми.  
  
```vb  
Dim lastTime, nextTime, allTimes() As Date  
```  
  
 Если объявляется несколько переменных с одним `As` предложение, невозможно указать инициализатор для этой группы переменных.  
  
 Можно указать различные типы данных для переменных с помощью отдельного `As` предложение для каждой объявляемой переменной. Каждая переменная имеет тип данных, указанный в первом `As` предложения возникли после его `variablename` часть.  
  
```vb  
Dim a, b, c As Single, x, y As Double, i As Integer  
' a, b, and c are all Single; x and y are both Double  
```  
  
## <a name="arrays"></a>Массивы  
 Можно объявить переменную для хранения *массив*, который может содержать несколько значений. Чтобы указать, что переменная содержит массив, выполните его `variablename` немедленно со скобками. Дополнительные сведения о массивах см. в разделе [массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
 Можно указать нижнюю и верхнюю границу каждого измерения массива. Чтобы сделать это, включите `boundslist` в скобках. Для каждого измерения `boundslist` указывает верхнюю границу и при необходимости нижняя граница. Нижняя граница всегда равно нулю, задания или нет. Каждый индекс может изменяться от нуля до значения верхней границы.  
  
 Следующие две инструкции эквивалентны. Каждый оператор объявляет массив 21 `Integer` элементов. Когда вы обращаетесь массива, индекс может изменяться от 0 до 20.  
  
```vb  
Dim totals(20) As Integer  
Dim totals(0 To 20) As Integer  
```  
  
 Следующий оператор объявляет двухмерный массив типа `Double`. Массив имеет 4 строки (3 + 1) 6 столбцов (5 + 1) каждого. Обратите внимание, что верхняя граница представляет наибольшее возможное значение для индекса, но не длину измерения. Длина измерения равна верхней границе плюс один.  
  
```vb  
Dim matrix2(3, 5) As Double  
```  
  
 Массив может быть от 1 до 32 измерений.  
  
 Можно оставить все границы в объявлении массива. После этого, массив содержит число измерений, которые вы указали, но он не инициализирован. Он имеет значение `Nothing` до инициализации по крайней мере некоторые из его элементов. `Dim` Инструкции необходимо указать границы для всех измерений или нет измерений.  
  
```vb  
' Declare an array with blank array bounds.  
Dim messages() As String  
' Initialize the array.  
ReDim messages(4)  
```  
  
 Если массив имеет более одного измерения, должно включать запятые заключено в круглые скобки, чтобы указать число измерений.  
  
```vb  
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte  
```  
  
 Можно объявить *массив нулевой длины* , объявив одно из измерений массива равным – 1. Переменная, содержащая массив нулевой длины не имеет значение `Nothing`. Массивы нулевой длины необходимы определенные функции среды CLR. При попытке получить доступ к таким массивам, возникает исключение времени выполнения. Дополнительные сведения см. в разделе [массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
 С помощью литерала массива можно инициализировать значения массива. Чтобы сделать это, заключите начальных значений в фигурные скобки (`{}`).  
  
```vb  
Dim longArray() As Long = {0, 1, 2, 3}  
```  
  
 Для многомерных массивов инициализации для каждой отдельной размерности заключается в фигурные скобки, в измерении «внешнее». Элементы указываются в строкам.  
  
```vb  
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}  
```  
  
 Дополнительные сведения о литералах массива см. в разделе [массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
##  <a name="default"></a> Типы данных по умолчанию и значения  
 В следующей таблице перечислены результаты различных сочетаний заданных типов данных и инициализаторов в операторе `Dim`.  
  
|Указан тип данных?|Указан инициализатор?|Пример|Результат|  
|---|---|---|---|  
|Нет|Нет|`Dim qty`|Если [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) — off (по умолчанию), переменной присваивается `Nothing`.<br /><br /> Если параметр `Option Strict` включен, возникает ошибка времени компиляции.|  
|Нет|Да|`Dim qty = 5`|Если [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) включен (по умолчанию), переменная получает тип данных инициализатора. См. в разделе [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Если параметры `Option Infer` и `Option Strict` отключены, переменная получает тип данных `Object`.<br /><br /> Если параметр `Option Infer` отключен, а параметр `Option Strict` включен, при компиляции возникает ошибка.|  
|Да|Нет|`Dim qty As Integer`|Переменная инициализируется со значением по умолчанию для типа данных. См. в таблице ниже в данном разделе.|  
|Да|Да|`Dim qty  As Integer = 5`|Если тип данных инициализатора нельзя преобразовать в указанный тип данных, возникает ошибка времени компиляции.|  
  
 Если указать тип данных, но не указан инициализатор, Visual Basic инициализирует переменную со значением по умолчанию для типа данных. Следующая таблица показывает значение по умолчанию значения инициализации.  
  
|Тип данных|Значение по умолчанию|  
|---|---|  
|Все числовые типы (включая `Byte` и `SByte`)|0|  
|`Char`|Двоичный 0|  
|Все ссылочные типы (включая `Object`, `String`и все массивы)|`Nothing`|  
|`Boolean`|`False`|  
|`Date`|00:00:00 1 января 1 года (01/01/0001 12:00:00 AM)|  
  
 Каждый элемент структуры инициализируется, как если бы он был отдельной переменной. Если вы объявите длину массива, но не инициализировать его элементы, каждый элемент инициализируется, как если бы он был отдельной переменной.  
  
## <a name="static-local-variable-lifetime"></a>Время существования статической локальной переменной  
 Объект `Static` локальная переменная имеет дольше процедуры, в котором она объявлена. Пределы существования переменной зависят от того, где объявлен процедуру и является ли он `Shared`.  
  
|Объявление процедуры|Переменная, инициализированная|Переменная прекращает существующие|  
|---|---|---|  
|В модуле|При первом вызове процедуры|Когда программа останавливает выполнение|  
|В классе или структуре процедура является `Shared`|Первый раз при вызове процедуры в определенном экземпляре или на классе или структуре самой|Когда программа останавливает выполнение|  
|В классе или структуре не процедуры `Shared`|При первом вызове процедуры в определенном экземпляре|Когда экземпляр освобождается для сборки мусора (GC)|  
  
## <a name="attributes-and-modifiers"></a>Атрибуты и модификаторы  
 Можно применять атрибуты только для переменных-членов, не для локальных переменных. Атрибут вносит сведения для метаданных сборки, которая не имеет смысла для временного хранения, такие как локальные переменные.  
  
 На уровне модуля нельзя использовать `Static` модификатор для объявления переменных-членов. На уровне процедуры, нельзя использовать `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, или любой доступ модификаторы для объявления локальных переменных.  
  
 Можно указать, какой код может обращаться к переменной, указав `accessmodifier`. Класс модуля члены и переменные (за пределами любых процедур) по умолчанию закрытый доступ и переменные-члены структуры по умолчанию общий доступ. Вы можете настроить уровни доступа с помощью модификаторов доступа. Нельзя использовать модификаторы доступа для локальных переменных (внутри процедуры).  
  
 Можно указать `WithEvents` только для переменных-членов, а не на локальные переменные внутри процедуры. Если указать `WithEvents`, тип данных переменной должен быть определенный тип класса, не `Object`. Можно объявить массив, содержащий `WithEvents`. Дополнительные сведения о событиях см. в разделе [события](../../../visual-basic/programming-guide/language-features/events/index.md).  
  
> [!NOTE]
>  Код вне класса, структуры или модуля необходимо указать имя переменной-члена с именем этого класса, структуры или модуля. Код за пределами процедуры или блока не может ссылаться на всех локальных переменных в рамках этой процедуры или блока.  
  
## <a name="releasing-managed-resources"></a>Освобождение управляемых ресурсов  
 Сборщик мусора .NET Framework освобождает управляемые ресурсы без дополнительного кодирования со стороны пользователя. Тем не менее вы можете принудительно реализации управляемых ресурсов, а не ждать, пока сборщик мусора.  
  
 Если класс удерживает особо ценный и редкий ресурс (например, дескриптор подключения или файл базы данных), может не потребоваться дождаться следующей сборки мусора для очистки экземпляра класса, который больше не используется. Класс может реализовывать <xref:System.IDisposable> интерфейс, который позволит освободить ресурсы перед сборкой мусора. Класс, реализующий этот интерфейс предоставляет `Dispose` метод, который может быть вызван для принудительного полезные материалы, которые немедленно высвобождены.  
  
 `Using` Инструкции автоматизирует процесс получения ресурса, выполнения набора инструкций и последующего освобождения ресурса. Тем не менее, необходимо реализовать ресурса <xref:System.IDisposable> интерфейс. Дополнительные сведения см. в разделе [Оператор using](../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="example"></a>Пример  
 В следующем примере объявляется переменных с помощью `Dim` инструкции с различными параметрами.  
  
 [!code-vb[VbVbalrStatements#141](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере перечисляются простых чисел от 1 до 30. Область локальных переменных описан в комментариях к коду.  
  
 [!code-vb[VbVbalrStatements#142](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_2.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере `speedValue` переменная, объявленная на уровне класса. `Private` Ключевое слово используется для объявления переменной. Переменная может осуществляться в любой процедурой `Car` класса.  
  
 [!code-vb[VbVbalrStatements#144](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#145](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_4.vb)]  
  
## <a name="see-also"></a>См. также
- [Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md)
- [Оператор reDim](../../../visual-basic/language-reference/statements/redim-statement.md)
- [Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Оператор Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Страница "Компиляция" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [Объявление переменных](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Инициализаторы объектов. Именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Инициализаторы объектов. Именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Практическое руководство. Объявление объекта с помощью инициализатора объектов](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
- [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
