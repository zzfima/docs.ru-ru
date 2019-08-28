---
title: Операции вставки, обновления и удаления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 26a43a4f-83c9-4732-806d-bb23aad0ff6b
ms.openlocfilehash: 662abcba5fb2fbdbef3ae804d8d96498c34303e0
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044177"
---
# <a name="insert-update-and-delete-operations"></a>Операции вставки, обновления и удаления

В `Insert` операции `Update`, `Delete` и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] выполняются путем добавления, изменения и удаления объектов в объектной модели. По умолчанию [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует действия в язык SQL и отправляет изменения в базу данных.

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]обеспечивает максимальную гибкость при манипуляции и сохранении изменений, внесенных в объекты. Как только будут доступны объекты сущности (либо при извлечении их с помощью запроса, либо при создании заново), их можно изменить как обычные объекты в приложении. Это значит, что можно изменить их значения, добавить их в коллекции и удалить из коллекций. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] отслеживает изменения и готов отправить их обратно в базу данных, когда будет вызван метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.

> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает или не распознает операции каскадного удаления. Если необходимо удалить строку в таблице с ограничениями, необходимо либо задать `ON DELETE CASCADE` правило в ограничении внешнего ключа в базе данных, либо использовать собственный код, чтобы сначала удалить дочерние объекты, препятствующие удалению родительского объекта. В противном случае создается исключение. Дополнительные сведения см. в разделе [Практическое руководство. Удаляет строки из базы данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).

В следующих фрагментах используются классы `Customer` и `Order` из образца базы данных "Борей". Для краткости определения классов не показаны.

[!code-csharp[DLinqCRUDOps#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCRUDOps/cs/Program.cs#1)]
[!code-vb[DLinqCRUDOps#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCRUDOps/vb/Module1.vb#1)]

При вызове метода <xref:System.Data.Linq.DataContext.SubmitChanges%2A>[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] автоматически создает и выполняет команды SQL, необходимые для передачи изменений обратно в базу данных.

> [!NOTE]
> Это поведение можно переопределить использованием собственной настраиваемой логики, обычно за счет хранимой процедуры. Дополнительные сведения см. [в разделе обязанности разработчика при переопределении поведения по умолчанию](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md).
>
> Разработчики, использующие Visual Studio, могут использовать реляционный конструктор объектов для разработки хранимых процедур для этой цели.

## <a name="see-also"></a>См. также

- [Загрузка примеров баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [Настройка операций вставки, обновления и удаления](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
