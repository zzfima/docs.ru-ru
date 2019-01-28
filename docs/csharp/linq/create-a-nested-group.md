---
title: Создание вложенной группы (LINQ в C#)
description: Узнайте, как создать вложенную группу в выражении запроса LINQ в C#.
ms.date: 12/01/2016
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.openlocfilehash: 7d056c9e215ccc7ca24d621b64e2328bed79f22e
ms.sourcegitcommit: 5dcfeb59179e81071f54840d4902cbe00b184294
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2019
ms.locfileid: "54857675"
---
# <a name="create-a-nested-group"></a>Создание вложенной группы

В следующем примере демонстрируется создание вложенных групп в выражении запроса LINQ. Каждая группа, созданная в соответствии с годом обучения или курсом учащегося, затем подразделяется на группы по именам учащихся.

## <a name="example"></a>Пример

> [!NOTE]
> Этот пример содержит ссылки на объекты, определенные в примере кода в разделе [Запрос коллекции объектов](query-a-collection-of-objects.md).

[!code-csharp[csProgGuideLINQ#24](~/samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]

Обратите внимание, что для выполнения итерации по внутренним элементам вложенной группы необходимо три вложенных цикла `foreach`.

## <a name="see-also"></a>См. также

- [LINQ](index.md)
