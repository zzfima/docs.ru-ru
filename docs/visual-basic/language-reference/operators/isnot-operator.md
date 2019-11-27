---
title: Оператор IsNot
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 616506f64d20e1f150b443433f1b69040136a5ba
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336063"
---
# <a name="isnot-operator-visual-basic"></a>Оператор IsNot (Visual Basic)

Сравнивает две переменные ссылки на объект.

## <a name="syntax"></a>Синтаксис

```vb
result = object1 IsNot object2
```

## <a name="parts"></a>Части
 `result` Обязательный. Значение `Boolean`.

 `object1` Обязательный. Любая `Object` переменная или выражение.

 `object2` Обязательный. Любая `Object` переменная или выражение.

## <a name="remarks"></a>Примечания
 Оператор `IsNot` определяет, ссылаются ли две объектные ссылки на разные объекты. Однако сравнение значений не выполняется. Если `object1` и `object2` оба ссылаются на один и тот же экземпляр объекта, `result` `False`. в противном случае `result` `True`.

 `IsNot` является противоположностью оператора `Is`. Преимущество `IsNot` состоит в том, что можно избежать неудобного синтаксиса с `Not` и `Is`, который трудно читать.

 Операторы `Is` и `IsNot` можно использовать для тестирования объектов с ранней и поздней привязкой.

## <a name="example"></a>Пример
 В следующем примере кода используются как оператор `Is`, так и оператор `IsNot` для выполнения одинакового сравнения.

 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="see-also"></a>См. также

- [Оператор Is](is-operator.md)
- [Оператор TypeOf](typeof-operator.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Практическое руководство. Проверка совпадения двух объектов](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
