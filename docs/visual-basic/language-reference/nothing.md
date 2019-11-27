---
title: Nothing - ключевое слово
ms.date: 07/20/2015
f1_keywords:
- Nothing
- vb.Nothing
helpviewer_keywords:
- Nothing keyword [Visual Basic]
- Nothing keyword [Visual Basic], syntax
ms.assetid: 06176e2d-bbf7-4a37-afaa-a86ad21ee99f
ms.openlocfilehash: 3bd4681341a33cc8db4ecbc2b284be243db56549
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344167"
---
# <a name="nothing-keyword-visual-basic"></a>Ключевое слово Nothing (Visual Basic)

Представляет значение по умолчанию для любого типа данных. Для ссылочных типов значением по умолчанию является ссылка на `null`. Для типов значений значение по умолчанию зависит от того, допускает ли тип значения значение null.

> [!NOTE]
> Для типов значений, не допускающих значения NULL, `Nothing` в Visual Basic отличаются C#от `null` в. В Visual Basic, если для переменной типа значения, не допускающего значения NULL, задано значение `Nothing`, для переменной задается по умолчанию для объявленного типа. В C#при присвоении `null`переменной типа значения, не допускающего значения NULL, возникает ошибка времени компиляции.

## <a name="remarks"></a>Примечания

`Nothing` представляет значение по умолчанию для типа данных. Значение по умолчанию зависит от того, имеет ли переменная тип значения или ссылочный тип.

Переменная *типа значения* напрямую содержит его значение. Типы значений включают все числовые типы данных, `Boolean`, `Char`, `Date`, все структуры и все перечисления. Переменная *ссылочного типа* хранит ссылку на экземпляр объекта в памяти. Ссылочные типы включают классы, массивы, делегаты и строки. Для получения дополнительной информации см. [Value Types and Reference Types](../programming-guide/language-features/data-types/value-types-and-reference-types.md).

Если переменная имеет тип значения, поведение `Nothing` зависит от того, имеет ли переменная тип данных, допускающий значение null. Чтобы представить тип значения, допускающий значение null, добавьте модификатор `?` к имени типа. Присвоение `Nothing` переменной, допускающей значение null, присваивает значение `null`. Дополнительные сведения и примеры см. в разделе [типы значений, допускающие значения NULL](../programming-guide/language-features/data-types/nullable-value-types.md).

Если переменная имеет тип значения, не допускающий значения NULL, при присвоении `Nothing` ей присваивается значение по умолчанию для его объявленного типа. Если этот тип содержит члены переменных, все они устанавливаются в значения по умолчанию. Следующий пример иллюстрирует это для скалярных типов.

[!code-vb[VbVbalrKeywords#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class2.vb#7)]

Если переменная имеет ссылочный тип, то при присвоении `Nothing` переменной ей присваивается `null` ссылка на тип переменной. Переменная, для которой задана ссылка `null`, не связана ни с одним объектом. Следующий пример демонстрирует это:

[!code-vb[VbVbalrKeywords#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class3.vb#8)]

При проверке того, является ли переменная ссылки (или типа значения Nullable) `null`, не используйте `= Nothing` или `<> Nothing`. Всегда используйте `Is Nothing` или `IsNot Nothing`.

Для строк в Visual Basic пустая строка равна `Nothing`. Таким образом, `"" = Nothing` имеет значение true.

В следующем примере показаны сравнения, в которых используются операторы `Is` и `IsNot`.

[!code-vb[VbVbalrKeywords#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class4.vb#9)]

Если переменная объявляется без использования предложения `As` и для нее задано значение `Nothing`, переменная имеет тип `Object`. Примером этого является `Dim something = Nothing`. В этом случае возникает ошибка времени компиляции, когда `Option Strict` находится в состоянии on и `Option Infer` отключена.

При назначении `Nothing` переменной объекта она больше не ссылается ни на один экземпляр объекта. Если переменная ранее ссылалась на экземпляр, присвоение ей значения `Nothing` не приводит к завершению самого экземпляра. Экземпляр завершается, и связанные с ним память и системные ресурсы освобождаются, только если сборщик мусора (GC) обнаружит, что активные ссылки не остались.

`Nothing` отличается от объекта <xref:System.DBNull>, который представляет неинициализированный вариант или несуществующий столбец базы данных.

## <a name="see-also"></a>См. также

- [Оператор Dim](./statements/dim-statement.md)
- [Время существования. Создание и уничтожение объектов](../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Время существования в Visual Basic](../programming-guide/language-features/declared-elements/lifetime.md)
- [Оператор Is](./operators/is-operator.md)
- [Оператор IsNot](./operators/isnot-operator.md)
- [Типы значений, допускающие значение NULL](../programming-guide/language-features/data-types/nullable-value-types.md)
