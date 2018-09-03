---
title: Declare Statement (Visual Basic)
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
ms.openlocfilehash: 343ee168809fc63ef63559eda0fd018abde684e7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485746"
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
|`attributelist`|Необязательный. См. в разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Необязательный. Ниже указаны доступные значения.<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [защищенные](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [закрытый](../../../visual-basic/language-reference/modifiers/private.md)<br />- [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br />- [Частный защищенный](../../language-reference/modifiers/private-protected.md)<br /><br /> См. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Необязательный. См. в разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`charsetmodifier`|Необязательный. Определяет набор символов и файл поиска. Ниже указаны доступные значения.<br /><br /> -   [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md) (по умолчанию)<br />-   [Юникод](../../../visual-basic/language-reference/modifiers/unicode.md)<br />-   [Авто](../../../visual-basic/language-reference/modifiers/auto.md)|  
|`Sub`|Необязательно, но либо `Sub` или `Function` должен присутствовать. Указывает, что внешняя процедура не возвращает значение.|  
|`Function`|Необязательно, но либо `Sub` или `Function` должен присутствовать. Указывает, что внешняя процедура возвращает значение.|  
|`name`|Обязательно. Имя этой внешней ссылки. Дополнительные сведения см. в разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Lib`|Обязательно. Представляет `Lib` предложение, которое идентифицирует внешний файл (DLL или код ресурса), содержащий внешнюю процедуру.|  
|`libname`|Обязательно. Имя файла, которая содержит объявленные процедуру.|  
|`Alias`|Необязательный. Указывает, что процедуры невозможно определить в файле с именем, указанным в `name`. Необходимо указать его идентификацию в `aliasname`.|  
|`aliasname`|Требуется при использовании `Alias` ключевое слово. Строка, определяющая процедуру, описанную в одним из двух способов:<br /><br /> Имя точки входа в процедуру в файле в кавычках (`""`)<br /><br /> - или -<br /><br /> Знак решетки (`#`) за которым следует целое число, указывающее порядковый номер точки входа процедуры в файле|  
|`parameterlist`|Требуется, если процедура принимает параметры. См. в разделе [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`returntype`|Обязателен, если `Function` указан и `Option Strict` является `On`. Тип данных значения, возвращаемые процедурой.|  
  
## <a name="remarks"></a>Примечания  
 Иногда необходимо вызвать процедуру, определенную в файле (например, DLL или код ресурса) вне данного проекта. При этом компилятор Visual Basic нет доступа к сведениям, необходимым для корректного вызова процедуры, такие как местонахождения процедуры, ее идентификатор, последовательность вызова и тип возвращаемого значения и набор символов строки, которые он использует. `Declare` Инструкция создает ссылку на внешнюю процедуру и предоставляет необходимую информацию.  
  
 `Declare` можно использовать только на уровне модуля. Это означает, что *контекст объявления* для внешней ссылки должен быть класс, структура или модуль, а не может быть исходный файл, пространство имен, интерфейс, процедура или блок. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Внешние ссылки по умолчанию для [открытый](../../../visual-basic/language-reference/modifiers/public.md) доступа. Вы можете настроить уровни доступа с помощью модификаторов доступа.  
  
## <a name="rules"></a>Правила  
  
-   **Атрибуты.** Можно применять атрибуты к внешней ссылке. Любой атрибут действует только в проекте, а не во внешнем файле.  
  
-   **Модификаторы.** Внешние процедуры являются неявно [Shared](../../../visual-basic/language-reference/modifiers/shared.md). Нельзя использовать `Shared` ключевое слово, когда объявление внешнюю ссылку и вы не сможете изменить его состояние общего доступа.  
  
     Внешнюю процедуру не может участвовать в переопределении, реализовывать члены интерфейса или обрабатывать события. Соответственно, нельзя использовать `Overrides`, `Overridable`, `NotOverridable`, `MustOverride`, `Implements`, или `Handles` ключевое слово в `Declare` инструкции.  
  
-   **Имя внешней процедуры.** Нет необходимости задавать этой внешней ссылке тем же именем (в `name`) в качестве имени точки входа процедуры во внешнем файле (`aliasname`). Можно использовать `Alias` предложение для указания имени точки входа. Это может быть полезно, если внешняя процедура имеет то же имя, что зарезервированный модификатор Visual Basic или переменной, процедура или любого другого элемента программирования в той же области.  
  
    > [!NOTE]
    >  В большинстве DLL точки входа имена учитывается регистр.  
  
-   **Номер внешней процедуры.** Кроме того, можно использовать `Alias` предложение, чтобы указать порядковый номер точки входа в таблице экспорта внешнего файла. Чтобы сделать это, началом `aliasname` со знака номера (`#`). Это полезно в том случае, если любой символ в имени внешней процедуры не допускается в Visual Basic или внешний файл экспортирует процедуру без указания имени.  
  
## <a name="data-type-rules"></a>Правила для типа данных  
  
-   **Типы данных параметров.** Если `Option Strict` — `On`, необходимо указать тип данных каждого параметра в `parameterlist`. Это может быть любой тип данных или имя перечисления, структуры, класса или интерфейса. В рамках `parameterlist`, использовании `As` предложение, чтобы указать тип данных аргумента передается каждого параметра.  
  
    > [!NOTE]
    >  Если внешняя процедура не была написана для платформы .NET Framework, необходимо соблюдать осторожность, соответствующие типы данных. Например, если вы объявляете внешняя ссылка на процедуру Visual Basic 6.0 с `Integer` параметра (16 бит в Visual Basic 6.0), необходимо определить, что соответствующий аргумент как `Short` в `Declare` инструкции, потому что это 16 - бит целочисленного типа в Visual Basic. Аналогичным образом `Long` имеет другой размер в Visual Basic 6.0 и `Date` реализуется по-разному.  
  
-   **Тип данных возвращаемого значения.** Если внешняя процедура, является `Function` и `Option Strict` является `On`, необходимо указать тип данных значения, возвращаемого в вызывающий код. Это может быть любой тип данных или имя перечисления, структуры, класса или интерфейса.  
  
    > [!NOTE]
    >  Компилятор Visual Basic не проверяет, что типы данных совместимы с файлами внешней процедуры. Если существует несоответствие, среда CLR создает <xref:System.Runtime.InteropServices.MarshalDirectiveException> исключения во время выполнения.  
  
-   **Типы данных по умолчанию.** Если `Option Strict` — `Off` и вы не укажете тип данных параметра в `parameterlist`, компилятор Visual Basic преобразует соответствующий аргумент в [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md). Аналогично Если вы не укажете `returntype`, компилятор принимает тип возвращаемых данных, чтобы быть `Object`.  
  
    > [!NOTE]
    >  Так как при работе с внешней процедуре, может быть записана на другой платформе, его небезопасно делать никаких предположений о типах данных или разрешить их по умолчанию. Гораздо безопаснее для указания типа данных каждого параметра и возвращаемого значения, если таковые имеются. Это также повышает удобочитаемость кода.  
  
## <a name="behavior"></a>Поведение  
  
-   **Область.** Область действия его класса, структуры или модуля — внешняя ссылка.  
  
-   **Время существования.** Внешняя ссылка имеет то же время существования, как класс, структура или модуль, в котором она объявлена.  
  
-   **Вызов внешних процедур.** Так же, как вызов внешней процедуры `Function` или `Sub` процедуры — с помощью его в выражении, если он возвращает значение, или путем указания его в [инструкции Call](../../../visual-basic/language-reference/statements/call-statement.md) если он не возвращает значение.  
  
     Передача аргументов в внешнюю процедуру точно в соответствии с `parameterlist` в `Declare` инструкции. Не учитывать как параметры были изначально объявленный во внешнем файле. Аналогичным образом, если возвращаемое значение, использовать его точно в соответствии с `returntype` в `Declare` инструкции.  
  
-   **Наборы знаков.** Можно указать в `charsetmodifier` как Visual Basic должен маршалировать строки при вызове внешней процедуры. `Ansi` Модификатор указывает маршалировать все строки в значения ANSI, Visual Basic и `Unicode` модификатор, то она маршалировать все строки в значениях Юникод. `Auto` Направляет модификатор Visual Basic для маршалинга строк в соответствии с .NET Framework правила на основе внешней ссылки `name`, или `aliasname` Если указано. Значение по умолчанию — `Ansi`.  
  
     `charsetmodifier` также указывает, как Visual Basic должен найти внешнюю процедуру во внешнем файле. `Ansi` и `Unicode` оба направления Visual Basic для поиска без изменения имени во время поиска. `Auto` Указывает Visual Basic, чтобы определить базовый набор символов платформы во время выполнения и возможно, изменить имя внешней процедуры следующим образом:  
  
    -   На платформе ANSI, таких как Windows 95, Windows 98 или Windows Millennium Edition сначала производится поиск внешней процедуры без изменения имени. В случае неудачи добавляется «A» в конец имени внешней процедуры и повторный поиск.  
  
    -   На платформе Юникода, например Windows NT, Windows 2000 или Windows XP сначала производится поиск внешней процедуры без изменения имени. Если это не удается добавить «W» в конец внешней процедуры имя и повторный поиск.  
  
-   **Механизм.** Visual Basic использует .NET Framework *неуправляемого* (PInvoke) механизм для разрешения и доступа к внешней процедуры. `Declare` Инструкции и <xref:System.Runtime.InteropServices.DllImportAttribute> класс оба используют этот механизм автоматически и не обязательно знать PInvoke. Дополнительные сведения см. в разделе [Пошаговое руководство: вызов API Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).  
  
> [!IMPORTANT]
>  Если внешняя процедура выполняется вне общеязыковой среды выполнения (CLR), это *неуправляемый код*. При вызове процедуры, например функции Win32 API или метода COM, может предоставлять приложения угрозам безопасности. Дополнительные сведения см. в разделе [правил написания безопасного кода для неуправляемого кода](../../../framework/security/secure-coding-guidelines-for-unmanaged-code.md).  
  
## <a name="example"></a>Пример  
 В следующем примере объявляется внешняя ссылка на `Function` процедуру, которая возвращает имя текущего пользователя. Затем он вызывает внешнюю процедуру `GetUserNameA` как часть `getUser` процедуры.  
  
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
