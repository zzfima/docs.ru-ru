---
title: Настройка операций за счет исключительного использования хранимых процедур
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
ms.openlocfilehash: 61230ffc5cd055ee64de9d519cdfb4d76c856ca3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62038055"
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a>Настройка операций за счет исключительного использования хранимых процедур
Распространенным сценарием является доступ к данным с использованием только хранимых процедур.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 Можно изменить пример, приведенный в [Настройка операций за счет хранимых процедур](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md) , заменив первый запрос (который вызывает динамическое выполнение SQL) на вызов метода, который создает оболочку для хранимой процедуры.  
  
 Предположим, что `CustomersByCity` является методом, как в следующем примере.  
  
### <a name="code"></a>Код  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 Следующий код выполняется без динамического SQL.  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>См. также

- [Ответственность разработчика при переопределении поведения по умолчанию](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)
