---
title: Операнд IsNot типа  можно сравнить только с Nothing, так как  является типом, допускающим значение NULL
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 06dc6f1532fecefba4e507bd0cc24aadc936d137
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524368"
---
# <a name="isnot-operand-of-type-typename-can-only-be-compared-to-nothing-because-typename-is-a-nullable-type"></a>Операнд IsNot типа  можно сравнить только с Nothing, так как  является типом, допускающим значение NULL

Переменная, объявленная как допускающая значение null, сравнивается с выражением, отличным от `Nothing` с помощью оператора `IsNot`.

**Идентификатор ошибки:** BC32128

## <a name="to-correct-this-error"></a>Исправление ошибки

Чтобы сравнить тип, допускающий значение null, с выражением, отличным от `Nothing` , с помощью оператора `IsNot` , вызовите метод `GetType` для типа, допускающего значение null, и сравните результат с выражением, как показано в следующем примере.

```vb
Dim number? As Integer = 5

If number IsNot Nothing Then
  If number.GetType() IsNot Type.GetType("System.Int32") Then

  End If
End If
```

## <a name="see-also"></a>См. также

- [Типы значений, допускающие значение NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Оператор IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)
