---
title: Практическое руководство. Переход по отношениям с помощью оператора Navigate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79996d2d-9b03-4a9d-82cc-7c5e7c2ad93d
ms.openlocfilehash: c8c23e00112859ffa9949d268c3263f73d3a714f
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251435"
---
# <a name="how-to-navigate-relationships-with-the-navigate-operator"></a>Практическое руководство. Переход по отношениям с помощью оператора Navigate
В этом подразделе показано выполнение команды для концептуальной модели с помощью объекта <xref:System.Data.EntityClient.EntityCommand>, а также получение результатов <xref:System.Data.Metadata.Edm.RefType> с помощью <xref:System.Data.EntityClient.EntityDataReader>.  
  
### <a name="to-run-the-code-in-this-example"></a>Выполнение кода в этом примере  
  
1. Добавьте [модель AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) в проект и настройте проект для использования [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Дополнительные сведения см. в разделе [Практическое руководство. Используйте мастер](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))EDM.  
  
2. На странице кода приложения добавьте следующие инструкции `using` (`Imports` в Visual Basic):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как перемещаться по [!INCLUDE[esql](../../../../../includes/esql-md.md)] связям в с помощью оператора [navigate](./language-reference/navigate-entity-sql.md) . `Navigate` Оператор принимает следующие параметры: экземпляр сущности, тип связи, окончание связи и начало связи между ними. При необходимости можно передать `Navigate` оператору только экземпляр сущности и тип связи.  
  
 [!code-csharp[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#navigatewithnavoperatorwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#navigatewithnavoperatorwithentitycommand)]  
  
## <a name="see-also"></a>См. также

- [Поставщик EntityClient для Entity Framework](entityclient-provider-for-the-entity-framework.md)
- [Язык Entity SQL](./language-reference/entity-sql-language.md)
