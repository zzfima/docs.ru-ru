---
title: '- Справочник по C#. Оператор -'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -_CSharpKeyword
helpviewer_keywords:
- '- operator [C#]'
- subtraction operator (-) [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: 8cf6e8871a88e2b37b9531ecbd616289523473c7
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333763"
---
# <a name="--operator-c-reference"></a>Справочник по C#. Оператор -

Оператор `-` может функционировать как унарный или как бинарный оператор.

## <a name="remarks"></a>Примечания

Унарные операторы `-` предварительно определены для всех числовых типов. Результатом использования унарного оператора `-` для числового типа является числовое отрицание операнда.

Бинарные операторы `-`, предопределенные для всех числовых типов и типов перечисления, обеспечивают вычитание второго операнда из первого.

Для типов делегатов также используется бинарный оператор `-`, который выполняет удаление делегатов.

Пользовательские типы могут перегружать унарный оператор `-` и бинарный оператор `-`. См. дополнительные о [ключевом слове operator](../keywords/operator.md).

## <a name="example"></a>Пример

[!code-csharp[csRefOperators#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#40)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)