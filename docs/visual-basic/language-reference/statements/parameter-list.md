---
title: Список параметров
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic
- parameters [Visual Basic], lists
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures [Visual Basic], parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
ms.openlocfilehash: ec4ce0f12b540478d889832fb18f1ef008613f1f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346482"
---
# <a name="parameter-list-visual-basic"></a>Список параметров (Visual Basic)

Указывает параметры, которые должны быть вызваны процедурой при ее вызове. Несколько параметров разделяются запятыми. Ниже приведен синтаксис для одного параметра.

## <a name="syntax"></a>Синтаксис

```vb
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]
parametername[( )] [ As parametertype ] [ = defaultvalue ]
```

## <a name="parts"></a>Части

`attributelist`  
Необязательный элемент. Список атрибутов, применяемых к этому параметру. [Список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md) необходимо заключить в угловые скобки ("`<`" и "`>`").

`Optional`  
Необязательный элемент. Указывает, что этот параметр не является обязательным при вызове процедуры.

`ByVal`  
Необязательный элемент. Указывает, что процедура не может заменить или переназначить элемент переменной, лежащий в основе соответствующего аргумента в вызывающем коде.

`ByRef`  
Необязательный элемент. Указывает, что процедура может изменить базовый элемент Variable в вызывающем коде так же, как и сам вызывающий код.

`ParamArray`  
Необязательный элемент. Указывает, что последний параметр в списке параметров является необязательным массивом элементов указанного типа данных. Это позволяет вызывающему коду передавать процедуре произвольное число аргументов.

`parametername`  
Обязательно. Имя локальной переменной, представляющей параметр.

`parametertype`  
Требуется, если `Option Strict` `On`. Тип данных локальной переменной, представляющей параметр.

`defaultvalue`  
Требуется для `Optional` параметров. Любое константное или константное выражение, результатом которого является тип данных параметра. Если тип `Object`или класс, интерфейс, массив или структура, значение по умолчанию можно только `Nothing`.

## <a name="remarks"></a>Примечания

Параметры заключаются в круглые скобки и разделяются запятыми. Параметр может быть объявлен с любым типом данных. Если не указать `parametertype`, по умолчанию используется `Object`.

Когда вызывающий код вызывает процедуру, он передает *аргумент* в каждый обязательный параметр. Дополнительные сведения см. в разделе [различия между параметрами и аргументами](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).

Аргумент, который вызывающий код передает каждому параметру, является указателем на базовый элемент в вызывающем коде. Если этот элемент является *неизменяемым* (константой, литералом, перечислением или выражением), любой код изменить его невозможно. Если это элемент *переменной* (объявленная переменная, поле, свойство, элемент массива или элемент структуры), вызывающий код может изменить его. Дополнительные сведения см. в разделе [различия между изменяемыми и неизменяемыми аргументами](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).

Если элемент переменной передается `ByRef`, процедура также может изменить ее. Дополнительные сведения см. в разделе [различия между передачей аргумента по значению и по ссылке](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).

## <a name="rules"></a>Правила

- **Скобки.** Если указан список параметров, его необходимо заключить в круглые скобки. Если параметры отсутствуют, можно по-прежнему использовать круглые скобки, включающие пустой список. Это повышает удобочитаемость кода путем уточнения того, что элемент является процедурой.

- **Необязательные параметры.** При использовании модификатора `Optional` для параметра все последующие параметры в списке также должны быть необязательными и объявлены с помощью модификатора `Optional`.

     Каждое объявление необязательного параметра должно предоставлять предложение `defaultvalue`.

     Дополнительные сведения см. в разделе [необязательные параметры](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).

- **Массивы параметров.** Для параметра `ParamArray` необходимо указать `ByVal`.

     В одном списке параметров нельзя использовать как `Optional`, так и `ParamArray`.

     Дополнительные сведения см. в разделе [массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).

- **Механизм передачи.** Механизмом по умолчанию для каждого аргумента является `ByVal`, что означает, что процедура не может изменить базовый элемент Variable. Однако если элемент является ссылочным типом, процедура может изменить содержимое или члены базового объекта, даже если он не может заменить или переназначить сам объект.

- **Имена параметров.** Если тип данных параметра является массивом, следуйте указаниям, `parametername`, сразу после круглых скобок. Дополнительные сведения об именах параметров см. в разделе [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).

## <a name="example"></a>Пример

В следующем примере показана `Function` процедура, определяющая два параметра.

[!code-vb[VbVbalrStatements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#2)]

## <a name="see-also"></a>См. также

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
