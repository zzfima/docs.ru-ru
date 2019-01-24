---
title: '* Справочник по C#. Оператор -'
ms.custom: seodec18
ms.date: 04/04/2018
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: f4490c4632d9344eb879ea55c20787b838781d91
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333737"
---
# <a name="-operator-c-reference"></a>Справочник по C#. Оператор *

Оператор умножения (`*`) вычисляет произведение операндов. Все числовые типы имеют предопределенные операторы умножения.

Кроме того, `*` служит оператором разыменования, позволяющим выполнять чтение указателя и запись в него.

## <a name="remarks"></a>Примечания

Оператор `*` также используется для объявления типов указателей и для разыменования указателей. Этот оператор может использоваться только в небезопасных контекстах, обозначенных с помощью ключевого слова [unsafe](../keywords/unsafe.md) и требующих параметр компилятора [/unsafe](../compiler-options/unsafe-compiler-option.md).  Оператор разыменования также известен как оператор косвенного обращения.

Определяемые пользователем типы могут вызвать перегрузку бинарного оператора `*` (см. раздел [operator](../keywords/operator.md)) . При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.

## <a name="example"></a>Пример

[!code-csharp-interactive[csRefOperators#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#50)]

## <a name="example"></a>Пример

[!code-csharp[csRefOperators#51](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#51)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Небезопасный код и указатели](../../programming-guide/unsafe-code-pointers/index.md)
- [Операторы в C#](index.md)