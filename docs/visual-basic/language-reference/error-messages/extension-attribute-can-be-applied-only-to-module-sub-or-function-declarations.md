---
title: Атрибут Extension может быть применен только к объявлениям Module, Sub или Function
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: 2ed3a10cdf941bb8d1d7c00379736e04e8cad4d7
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583185"
---
# <a name="extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a>Атрибут Extension может быть применен только к объявлениям Module, Sub или Function

Единственным способом расширения типа данных в Visual Basic является определение метода расширения внутри стандартного модуля. Метод расширения может быть `Sub` процедурой или `Function`ой процедурой. Все методы расширения должны быть помечены атрибутом расширения `<Extension()>` из пространства имен <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>. При необходимости модуль, содержащий метод расширения, может быть помечен таким же образом. Использование атрибута расширения другим образом не допускается.

**Идентификатор ошибки:** BC36550

## <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите атрибут расширения.

- Перепроектирование расширения как метода, определенного во внешнем модуле.

## <a name="example"></a>Пример

В следующем примере определяется метод `Print` для `String`ного типа данных.

```vb
Imports StringUtility
Imports System.Runtime.CompilerServices
Namespace StringUtility
    <Extension()>
    Module StringExtensions
        <Extension()>
        Public Sub Print (ByVal str As String)
            Console.WriteLine(str)
        End Sub
    End Module
End Namespace
```

## <a name="see-also"></a>См. также

- [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Методы расширения](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)
