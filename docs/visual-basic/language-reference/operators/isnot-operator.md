---
title: Оператор IsNot (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 7e1ac1004e671f592c03bd44ee7ec2e8cc572933
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71331628"
---
# <a name="isnot-operator-visual-basic"></a>Оператор IsNot (Visual Basic)
Сравнивает две переменные ссылки на объект.

## <a name="syntax"></a>Синтаксис

```vb
result = object1 IsNot object2
```

## <a name="parts"></a>Части
 `result` Обязательный. Значение `Boolean`.

 `object1` Обязательный. Любая переменная или выражение `Object`.

 `object2` Обязательный. Любая переменная или выражение `Object`.

## <a name="remarks"></a>Примечания
 Оператор `IsNot` определяет, ссылаются ли две объектные ссылки на разные объекты. Однако сравнение значений не выполняется. Если `object1` и `object2` ссылаются на один и тот же экземпляр объекта, `result` — `False`; в противном случае `result` — `True`.

 `IsNot` является противоположностью оператора `Is`. Преимущество `IsNot` состоит в том, что вы можете избежать неудобного синтаксиса с `Not` и `Is`, что может быть трудно читать.

 Для тестирования объектов с ранней и поздней привязкой можно использовать операторы `Is` и `IsNot`.

## <a name="example"></a>Пример
 В следующем примере кода используются как оператор `Is`, так и оператор `IsNot` для выполнения одинакового сравнения.

 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="see-also"></a>См. также

- [Оператор Is](is-operator.md)
- [Оператор TypeOf](typeof-operator.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Практическое руководство. Проверка того, что два объекта одинаковы, @ no__t-0
