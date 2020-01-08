---
title: Инструкция INSERT
ms.date: 12/13/2019
description: Советы по повышению производительности, которые можно использовать при внесении многочисленных изменений в базу данных.
ms.openlocfilehash: 9d87d5c8d70f8e70479f9aa02b7802f73b88de9e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450300"
---
# <a name="bulk-insert"></a>Инструкция INSERT

SQLite не имеет специального способа для выполнения операций вставки данных. Чтобы обеспечить оптимальную производительность при вставке или обновлении данных, необходимо выполнить следующие действия.

- Используйте транзакцию.
- Повторно используйте ту же параметризованную команду. Последующие выполнения будут повторно использовать компиляцию первого из них.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BulkInsertSample/Program.cs?name=snippet_BulkInsert)]
