---
title: Создание вложенной группы (LINQ в C#)
description: Узнайте, как создать вложенную группу в выражении запроса LINQ в C#.
ms.date: 12/1/2016
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.openlocfilehash: 82b07c303215200fa974ce614a2d5a77882dcf4c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509972"
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
