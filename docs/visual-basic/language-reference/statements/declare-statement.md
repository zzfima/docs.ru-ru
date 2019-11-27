---
title: Declare Statement
ms.date: 07/20/2015
f1_keywords:
- vb.Declare
- vb.Lib
- vb.Any
helpviewer_keywords:
- Lib keyword [Visual Basic]
- declaring procedures [Visual Basic], Declare statement
- functions [Visual Basic], function procedures
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- procedures [Visual Basic], external
- Alias keyword [Visual Basic]
- external references [Visual Basic], Visual Basic
- DLLs, declaring procedures
- Declare statement [Visual Basic]
- declarations [Visual Basic], external
- Visual Basic code, Function procedures
- As keyword [Visual Basic], in Declare statement
- resources [Visual Basic], declaring
- Public keyword [Visual Basic], Declare statement
- platform invoke, Visual Basic external references
- Sub procedures [Visual Basic], declarations
- APIs, declaring API functions
- Visual Basic code, Sub procedures
- Function procedures [Visual Basic], declaring
ms.assetid: d3f21fb0-b804-4c99-97ed-583b23894cf1
ms.openlocfilehash: 48a36e3ecdef40810ea7a3194e85b5b646154331
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354090"
---
# <a name="declare-statement"></a>Declare Statement

Объявляет ссылку на процедуру, реализованную во внешнем файле.

## <a name="syntax"></a>Синтаксис

```vb
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _
Declare [ charsetmodifier ] [ Sub ] name Lib "libname" _
[ Alias "aliasname" ] [ ([ parameterlist ]) ]
' -or-
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _
Declare [ charsetmodifier ] [ Function ] name Lib "libname" _
[ Alias "aliasname" ] [ ([ parameterlist ]) ] [ As returntype ]
```

## <a name="parts"></a>Части

|Термин|Определение|
|---|---|
|`attributelist`|Необязательный элемент. См. [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).|
|`accessmodifier`|Необязательный элемент. Ниже указаны доступные значения.<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />[защищенный](../../../visual-basic/language-reference/modifiers/protected.md) -   <br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [закрытый](../../../visual-basic/language-reference/modifiers/private.md)<br />- [защищенный дружественный](../../language-reference/modifiers/protected-friend.md)<br />- [частный защищенный](../../language-reference/modifiers/private-protected.md)<br /><br /> См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|
|`Shadows`|Необязательный элемент. См. раздел [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|
|`charsetmodifier`|Необязательный элемент. Указывает набор символов и сведения для поиска файлов. Ниже указаны доступные значения.<br /><br /> -   [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md) (по умолчанию)<br />-   [Юникод](../../../visual-basic/language-reference/modifiers/unicode.md)<br />-   [Auto](../../../visual-basic/language-reference/modifiers/auto.md)|
|`Sub`|Необязательно, но должен появиться либо `Sub`, либо `Function`. Указывает, что внешняя процедура не возвращает значение.|
|`Function`|Необязательно, но должен появиться либо `Sub`, либо `Function`. Указывает, что внешняя процедура возвращает значение.|
|`name`|Обязательно. Имя этой внешней ссылки. Дополнительные сведения см. в разделе [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|
|`Lib`|Обязательно. Вводит предложение `Lib`, которое определяет внешний файл (DLL или ресурс кода), содержащий внешнюю процедуру.|
|`libname`|Обязательно. Имя файла, содержащего объявленную процедуру.|
|`Alias`|Необязательный элемент. Указывает, что объявляемая процедура не может быть идентифицирована в файле по имени, указанному в `name`. Его идентификация указывается в `aliasname`.|
|`aliasname`|Требуется, если используется ключевое слово `Alias`. Строка, идентифицирующая процедуру одним из двух способов:<br /><br /> Имя точки входа процедуры внутри файла в кавычках (`""`)<br /><br /> \- или -<br /><br /> Знак решетки (`#`), за которым следует целое число, указывающее порядковый номер точки входа процедуры в пределах файла|
|`parameterlist`|Требуется, если процедура принимает параметры. См. [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).|
|`returntype`|Требуется, если указан `Function` и `Option Strict` `On`. Тип данных значения, возвращаемого процедурой.|

## <a name="remarks"></a>Примечания

Иногда требуется вызвать процедуру, определенную в файле (например, в библиотеке DLL или ресурсе кода) за пределами проекта. При этом компилятор Visual Basic не имеет доступа к информации, которая необходима для корректного вызова процедуры, например, где находится процедура, как она идентифицируется, ее вызывающая последовательность и возвращаемый тип, а также используемая Кодировка строки. Инструкция `Declare` создает ссылку на внешнюю процедуру и предоставляет эту необходимую информацию.

`Declare` можно использовать только на уровне модуля. Это означает, что *контекст объявления* для внешней ссылки должен быть классом, структурой или модулем и не может быть исходным файлом, пространством имен, интерфейсом, процедурой или блоком. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).

По умолчанию внешние ссылки имеют [открытый](../../../visual-basic/language-reference/modifiers/public.md) доступ. Уровни доступа можно изменить с помощью модификаторов доступа.

## <a name="rules"></a>Правила

- **Атрибута.** К внешней ссылке можно применять атрибуты. Любой применяемый атрибут действует только в проекте, а не во внешнем файле.

- **Модификаторы.** Внешние процедуры являются неявно [общими](../../../visual-basic/language-reference/modifiers/shared.md). Нельзя использовать ключевое слово `Shared` при объявлении внешней ссылки, и изменить его общее состояние нельзя.

  Внешняя процедура не может участвовать в переопределении, реализации членов интерфейса или обработке событий. Соответственно, нельзя использовать ключевое слово `Overrides`, `Overridable`, `NotOverridable`, `MustOverride`, `Implements`или `Handles` в инструкции `Declare`.

- **Имя внешней процедуры.** Нет необходимости присваивать этой внешней ссылке то же имя (в `name`) в качестве имени точки входа процедуры во внешнем файле (`aliasname`). Для указания имени точки входа можно использовать предложение `Alias`. Это может быть полезно, если внешняя процедура имеет то же имя, что и зарезервированный модификатор Visual Basic, или переменную, процедуру или любой другой программный элемент в той же области.

  > [!NOTE]
  > В большинстве DLL имена точек входа чувствительны к регистру.

- **Номер внешней процедуры.** Кроме того, можно использовать предложение `Alias`, чтобы указать порядковый номер точки входа в таблице экспорта внешнего файла. Для этого начните `aliasname` со знаком номера (`#`). Это может быть полезно, если в Visual Basic не допускается любой символ из имени внешней процедуры или если внешний файл экспортирует процедуру без имени.

## <a name="data-type-rules"></a>Правила типов данных

- **Типы данных параметров.** Если `Option Strict` `On`, необходимо указать тип данных каждого параметра в `parameterlist`. Это может быть любой тип данных или имя перечисления, структуры, класса или интерфейса. В `parameterlist`используется предложение `As` для указания типа данных аргумента, который должен быть передан в каждый параметр.

  > [!NOTE]
  > Если внешняя процедура не была написана для .NET Framework, необходимо соблюдать осторожность в соответствии с типами данных. Например, если объявить внешнюю ссылку на процедуру Visual Basic 6,0 с параметром `Integer` (16 бит в Visual Basic 6,0), необходимо определить соответствующий аргумент как `Short` в инструкции `Declare`, так как это 16-разрядный целочисленный тип в Visual Basic. Аналогичным образом `Long` имеет разную ширину данных в Visual Basic 6,0, а `Date` реализуется по-разному.

- **Тип возвращаемых данных.** Если внешняя процедура является `Function` и `Option Strict` `On`, необходимо указать тип данных значения, возвращаемого в вызывающий код. Это может быть любой тип данных или имя перечисления, структуры, класса или интерфейса.

  > [!NOTE]
  > Компилятор Visual Basic не проверяет совместимость типов данных с параметрами внешней процедуры. В случае несоответствия среда CLR создает исключение <xref:System.Runtime.InteropServices.MarshalDirectiveException> во время выполнения.

- **Типы данных по умолчанию.** Если `Option Strict` имеет `Off` и не указан тип данных параметра в `parameterlist`, компилятор Visual Basic преобразует соответствующий аргумент в [тип данных Object](../../../visual-basic/language-reference/data-types/object-data-type.md). Аналогично, если не указать `returntype`, компилятор принимает тип возвращаемых данных для `Object`.

  > [!NOTE]
  > Поскольку вы работаете с внешней процедурой, которая могла бы быть написана на другой платформе, небезопасно делать какие-либо предположения о типах данных или разрешать их по умолчанию. Намного безопаснее указывать тип данных каждого параметра и возвращаемого значения, если таковые имеются. Это также повышает удобочитаемость кода.

## <a name="behavior"></a>Поведение

- **Которых.** Внешняя ссылка находится в области действия класса, структуры или модуля.

- **Контролиру.** Внешняя ссылка имеет то же время существования, что и класс, структура или модуль, в котором он объявлен.

- **Вызов внешней процедуры.** Вызов внешней процедуры происходит точно так же, как `Function` или `Sub` процедура — с помощью ее в выражении, если она возвращает значение, или путем указания в [инструкции Call](../../../visual-basic/language-reference/statements/call-statement.md) , если она не возвращает значение.

  Аргументы для внешней процедуры передаются точно так же, как указано в `parameterlist` в инструкции `Declare`. Не следует учитывать, как параметры были первоначально объявлены во внешнем файле. Аналогично, если имеется возвращаемое значение, используйте его точно так же, как указано в `returntype` в инструкции `Declare`.

- **Кодировки.** Можно указать в `charsetmodifier`, как Visual Basic должен маршалировать строки при вызове внешней процедуры. Модификатор `Ansi` направляет Visual Basic для маршалирования всех строк в значения ANSI, а модификатор `Unicode` указывает, что необходимо маршалировать все строки в значения Юникода. Модификатор `Auto` направляет Visual Basic для маршалирования строк в соответствии с правилами .NET Framework, основанными на `name`внешней ссылки, или `aliasname`, если они заданы. Значение по умолчанию — `Ansi`.

  `charsetmodifier` также указывает, как Visual Basic должен выполнять поиск внешней процедуры во внешнем файле. `Ansi` и `Unicode` непосредственно Visual Basic, чтобы найти его без изменения имени во время поиска. `Auto` направляет Visual Basic определить базовый набор символов платформы времени выполнения и, возможно, изменить имя внешней процедуры следующим образом:

  - На платформе ANSI, такой как Windows 95, Windows 98 или Windows Millennium Edition, сначала следует найти внешнюю процедуру без изменения имени. Если это не удается, добавьте "A" в конец имени внешней процедуры и повторите поиск.

  - На платформе с поддержкой Юникода, например Windows NT, Windows 2000 или Windows XP, сначала ищете внешнюю процедуру без изменения имени. Если это не удается, добавьте "W" в конец имени внешней процедуры и повторите поиск.

- **Механизм.** Visual Basic использует механизм *вызова платформы* .NET Framework (PInvoke) для разрешения и доступа к внешним процедурам. Оператор `Declare` и класс <xref:System.Runtime.InteropServices.DllImportAttribute> используют этот механизм автоматически, и вам не требуется знание PInvoke. Дополнительные сведения см. в разделе [Пошаговое руководство. вызов интерфейсов API Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).

> [!IMPORTANT]
> Если внешняя процедура выполняется вне среды CLR, это *неуправляемый код*. При вызове такой процедуры, например, функции Windows API или COM-метода, приложение может представлять угрозу безопасности. Дополнительные сведения см. в разделе [рекомендации по безопасному кодированию для неуправляемого кода](../../../framework/security/secure-coding-guidelines-for-unmanaged-code.md).

## <a name="example"></a>Пример

В следующем примере объявляется внешняя ссылка на `Function` процедуру, которая возвращает имя текущего пользователя. Затем она вызывает внешнюю процедуру `GetUserNameA` как часть процедуры `getUser`.

[!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]

## <a name="example"></a>Пример

<xref:System.Runtime.InteropServices.DllImportAttribute> предоставляет альтернативный способ использования функций в неуправляемом коде. В следующем примере импортируемая функция объявляется без использования оператора `Declare`.

[!code-vb[VbVbalrStatements#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#16)]

[!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]

## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [Оператор Imports (пространство имен и тип .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Список параметров](../../../visual-basic/language-reference/statements/parameter-list.md)
- [Оператор Call](../../../visual-basic/language-reference/statements/call-statement.md)
- [Пошаговое руководство. Вызов API-интерфейсов Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
