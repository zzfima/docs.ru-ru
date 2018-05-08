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
ms.openlocfilehash: bc6949c7b52e87b7b39dd2690cac915a5f0d15aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="declare-statement"></a>Declare Statement
Объявляет ссылку на процедуру, реализованную во внешнем файле.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
|`attributelist`|Необязательный. В разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Необязательный. Ниже указаны доступные значения.<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Защищенные](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Закрытый](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> В разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Необязательный. В разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`charsetmodifier`|Необязательный. Задает набор символов и файл поиска сведений. Ниже указаны доступные значения.<br /><br /> -   [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md) (по умолчанию)<br />-   [Юникод](../../../visual-basic/language-reference/modifiers/unicode.md)<br />-   [Авто](../../../visual-basic/language-reference/modifiers/auto.md)|  
|`Sub`|Необязательно, но либо `Sub` или `Function` должны отображаться. Указывает, что внешняя процедура не возвращает значение.|  
|`Function`|Необязательно, но либо `Sub` или `Function` должны отображаться. Указывает, что внешняя процедура возвращает значение.|  
|`name`|Обязательно. Имя этой внешней ссылки. Дополнительные сведения см. в разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Lib`|Обязательно. Представляет `Lib` предложение, которое идентифицирует внешний файл (DLL или код ресурса), содержащий внешнюю процедуру.|  
|`libname`|Обязательно. Имя файла, который содержит объявляемую процедуру.|  
|`Alias`|Необязательный. Указывает, что объявляемая процедура не может определяться в его файле имя, указанное в `name`. Необходимо указать его идентификацию в `aliasname`.|  
|`aliasname`|Является обязательным, если используется `Alias` ключевое слово. Строка, идентифицирующая процедуру одним из двух способов:<br /><br /> Имя точки входа в процедуру в файле в кавычках (`""`)<br /><br /> - или -<br /><br /> Знак решетки (`#`) за которым следует целое число, указывающее порядковый номер точки входа процедуры в его файле|  
|`parameterlist`|Требуется, если процедура принимает параметры. В разделе [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`returntype`|Обязателен, если `Function` указан и `Option Strict` — `On`. Тип данных значения, возвращаемого процедурой.|  
  
## <a name="remarks"></a>Примечания  
 Иногда возникает необходимость вызове процедуры, определенной в файле за пределами проекта (например, DLL или код ресурса). При этом компилятор Visual Basic нет доступа к сведениям, необходимым для корректного вызова процедуры, например которой находится процедура, ее идентификатор, последовательность вызова и тип возвращаемого значения и строки набор символов, которые он использует. `Declare` Инструкция создает ссылку на внешнюю процедуру и предоставляет необходимую информацию.  
  
 `Declare` можно использовать только на уровне модуля. Это означает *контекст объявления* для внешней ссылки должен быть классом, структурой или модуля и не может быть исходный файл, пространство имен, интерфейс, процедура или блок. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Внешние ссылки по умолчанию для [открытый](../../../visual-basic/language-reference/modifiers/public.md) доступа. Вы можете настроить уровни доступа с помощью модификаторов доступа.  
  
## <a name="rules"></a>Правила  
  
-   **Атрибуты.** Можно применить атрибуты к внешней ссылке. Любой применяемый атрибут действует только в проекте, но не во внешнем файле.  
  
-   **Модификаторы.** Внешние процедуры являются неявно [Shared](../../../visual-basic/language-reference/modifiers/shared.md). Нельзя использовать `Shared` ключевого слова при объявлении внешней ссылки и невозможно изменить ее статус общего доступа.  
  
     Внешнюю процедуру не может участвовать в переопределении, реализовывать члены интерфейса или обрабатывать события. Таким образом, нельзя использовать `Overrides`, `Overridable`, `NotOverridable`, `MustOverride`, `Implements`, или `Handles` ключевое слово в `Declare` инструкции.  
  
-   **Имя внешней процедуры.** Нет необходимости задавать этой внешней ссылке тем же именем (в `name`) в качестве имени точки входа процедуры во внешнем файле (`aliasname`). Можно использовать `Alias` предложение для указания имени точки входа. Это может быть полезно, если внешняя процедура имеет то же имя, что зарезервированный модификатор Visual Basic или переменной, процедура или любого другого элемента программирования в той же области.  
  
    > [!NOTE]
    >  В большинстве DLL имена точек входа учитывается регистр.  
  
-   **Номер внешней процедуры.** Кроме того, можно использовать `Alias` предложений, чтобы указать порядковый номер точки входа в пределах таблицы экспорта внешнего файла. Чтобы сделать это, следует начать `aliasname` со знака номера (`#`). Это полезно в том случае, если любой символ в имени внешней процедуры не допускается в Visual Basic, или внешний файл экспортирует процедуру без указания имени.  
  
## <a name="data-type-rules"></a>Правила типов данных  
  
-   **Типы данных параметров.** Если `Option Strict` — `On`, необходимо указать тип данных каждого параметра в `parameterlist`. Это может быть любой тип данных или имя перечисления, структуры, класса или интерфейса. В пределах `parameterlist`, используется `As` предложений, чтобы указать тип данных аргумента для передачи каждого параметра.  
  
    > [!NOTE]
    >  Если внешняя процедура не была написана для платформы .NET Framework, необходимо соблюдать осторожность, соответствующие типы данных. Например, если объявляется внешняя ссылка на процедуру Visual Basic 6.0 с `Integer` параметра (16 бит в Visual Basic 6.0), необходимо определить соответствующий аргумент как `Short` в `Declare` инструкции, так как это 16 - целое число типа bit в Visual Basic. Аналогичным образом `Long` имеет другой размер в Visual Basic 6.0 и `Date` реализуется по-разному.  
  
-   **Тип данных возвращаемого значения.** Если внешняя процедура является `Function` и `Option Strict` — `On`, необходимо указать тип данных значения, возвращаемого в вызывающий код. Это может быть любой тип данных или имя перечисления, структуры, класса или интерфейса.  
  
    > [!NOTE]
    >  Компилятор Visual Basic не проверяет, что типы данных совместимы с файлами внешней процедуры. Если имеется несоответствие, общеязыковая среда выполнения создает <xref:System.Runtime.InteropServices.MarshalDirectiveException> исключений во время выполнения.  
  
-   **Типы данных по умолчанию.** Если `Option Strict` — `Off` и задают тип данных параметра в `parameterlist`, компилятор Visual Basic преобразует соответствующего аргумента в [тип данных объекта](../../../visual-basic/language-reference/data-types/object-data-type.md). Аналогично Если вы не укажете `returntype`, компилятор принимает тип возвращаемых данных для `Object`.  
  
    > [!NOTE]
    >  Поскольку вы имеете дело с внешней процедуре, которая может быть записана на другой платформе, его небезопасно делать никаких предположений о типах данных или оставлять их по умолчанию. Это гораздо более безопасной указать тип данных каждого параметра и возвращаемого значения, если таковые имеются. Это также повышает удобочитаемость кода.  
  
## <a name="behavior"></a>Поведение  
  
-   **Область действия.** Область действия его класса, структуры или модуля является внешней ссылкой.  
  
-   **Время существования.** Внешняя ссылка имеет то же время существования, как класс, структура или модуль, в котором она объявлена.  
  
-   **Вызов внешних процедур.** Вызов внешней процедуры так же, как `Function` или `Sub` процедуры — с помощью его в выражении, если он возвращает значение, или путем задания его в [инструкции Call](../../../visual-basic/language-reference/statements/call-statement.md) , если он не возвращает значение.  
  
     Передайте аргументы внешней процедуры точно в соответствии с `parameterlist` в `Declare` инструкции. Не учитывать как параметры были изначально объявлены во внешнем файле. Аналогичным образом, если возвращаемое значение отсутствует, использовать его точно в соответствии с `returntype` в `Declare` инструкции.  
  
-   **Наборы знаков.** Можно указать в `charsetmodifier` как Visual Basic должен маршалировать строки при вызове внешней процедуры. `Ansi` Модификатор указывает Visual Basic маршалировать все строки в значения ANSI и `Unicode` модификатор направляет его в маршалировать все строки в значения Юникода. `Auto` Направляет модификатор Visual Basic для маршалинга строк в соответствии с .NET Framework правила на основе внешней ссылки `name`, или `aliasname` Если указано. Значение по умолчанию — `Ansi`.  
  
     `charsetmodifier` также указывает, как Visual Basic следует искать внешней процедуры во внешнем файле. `Ansi` и `Unicode` оба направления Visual Basic для поиска без изменения имени во время поиска. `Auto` Указывает Visual Basic, чтобы определить базовый набор символов платформы во время выполнения и возможно, изменить имя внешней процедуры следующим образом:  
  
    -   На платформе ANSI, таких как Windows 95, Windows 98 или Windows Millennium Edition сначала найдите внешнюю процедуру без изменения имени. В случае неудачи добавляется в конец имени внешней процедуры «A», и повторный поиск.  
  
    -   На платформе Юникода, например Windows NT, Windows 2000 или Windows XP сначала найдите внешнюю процедуру без изменения имени. Если это не удается добавить «W» в конец внешней процедуре имя и повторный поиск.  
  
-   **Механизм.** Visual Basic использует .NET Framework *неуправляемого* (PInvoke) механизм для разрешения и доступ к внешней процедуры. `Declare` Инструкции и <xref:System.Runtime.InteropServices.DllImportAttribute> класс оба используют этот механизм автоматически и не требуются сведения о PInvoke. Дополнительные сведения см. в разделе [Пошаговое руководство: вызов API Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).  
  
> [!IMPORTANT]
>  Если внешняя процедура выполняется за пределами общеязыковой среды выполнения (CLR), это *неуправляемого кода*. При вызове процедуры, например функции Win32 API или метода COM, могут сделать ваше приложение к угрозам безопасности. Дополнительные сведения см. в разделе [правила написания безопасного кода для неуправляемого кода](../../../framework/security/secure-coding-guidelines-for-unmanaged-code.md).  
  
## <a name="example"></a>Пример  
 В следующем примере объявляется внешняя ссылка на `Function` процедуру, которая возвращает имя текущего пользователя. Затем он вызывает внешней процедуры `GetUserNameA` как часть `getUser` процедуры.  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_1.vb)]  
  
## <a name="example"></a>Пример  
 <xref:System.Runtime.InteropServices.DllImportAttribute> Предоставляет альтернативный способ использования функций в неуправляемом коде. В следующем примере объявляется импортированной функции без использования `Declare` инструкции.  
  
 [!code-vb[VbVbalrStatements#16](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_2.vb)]  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_3.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>  
 [Оператор Imports (пространство имен и тип .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Список параметров](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [Оператор Call](../../../visual-basic/language-reference/statements/call-statement.md)  
 [Пошаговое руководство. Вызов API-интерфейсов Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
