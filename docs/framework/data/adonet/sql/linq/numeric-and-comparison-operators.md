---
title: Числовые операторы и операторы сравнения
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: b29f78a13d6d0313e0ad29754f6d13ac08be1092
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973347"
---
# <a name="numeric-and-comparison-operators"></a>Числовые операторы и операторы сравнения

Арифметические операторы и операторы сравнения работают в среде (CLR) соответствующим образом, за исключением следующих моментов.

- SQL не поддерживает оператор modulus для чисел с плавающей запятой.

- SQL не поддерживает непроверяемые арифметические операции.

- Операторы инкремента или декремента вызывают побочные эффекты, если используются в выражениях, которые не могут быть реплицированы в SQL и поэтому не поддерживаются.

## <a name="supported-operators"></a>Поддерживаемые операторы

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает следующие операторы.

- Основные арифметические операторы

  - `+`

  - `-` (вычитание)

  - `*`

  - `/`

  - Оператор целочисленного деления Visual Basic (`\`)

  - `%` (Visual Basic `Mod`)

  - `<<`

  - `>>`

  - `-` (унарное отрицание)

- Основные операторы сравнения

  - Visual Basic `=` и C# `==`

  - Visual Basic `<>` и C# `!=`

  - Visual Basic `Is/IsNot`

  - `<`

  - `<=`

  - `>`

  - `>=`

## <a name="see-also"></a>См. также

- [Типы данных и функции](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
- [Операторы в C#](../../../../../../docs/csharp/language-reference/operators/index.md)
- [Инструкции](../../../../../visual-basic/language-reference/operators/index.md)
