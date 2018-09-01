---
title: N-уровневые и удаленные приложения и LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 854a1cdd-53cb-45f5-83ca-63962a9b3598
ms.openlocfilehash: 7af17500df9a0038ac4fa1eb3ad07a4c07190fa0
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43384264"
---
# <a name="n-tier-and-remote-applications-with-linq-to-sql"></a>N-уровневые и удаленные приложения и LINQ to SQL
Существует возможность создания многоуровневых приложений, использующих [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Как правило [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] контекст данных, классы сущностей и логики конструкций запросов расположены на среднем уровне доступа к данным (DAL). Бизнес-логика и непостоянные данные могут быть полностью реализованы в разделяемых классах, методах сущностей, контексте данных либо в отдельных классах.  
  
 Уровень клиента или представления вызывает методы в удаленном интерфейсе среднего уровня; DAL в этом интерфейсе выполнит запросы или хранимые процедуры, сопоставленные методам <xref:System.Data.Linq.DataContext>. Обычно средний уровень возвращает данные клиентам в виде XML-представлений сущностей или прокси-объектов.  
  
 На среднем уровне сущности создаются при помощи контекста данных, который отслеживает их состояние и управляет отложенной загрузкой из базы данных и передачей изменений в базу данных. Эти сущности присоединены к `DataContext`. Однако после отправки сущностей на другой уровень с помощью сериализации происходит их отсоединение, означающее, что `DataContext` больше не отслеживает их состояние. Сущности, отправляемые клиентом обратно для обновлений, следует повторно присоединить к контексту данных, прежде чем [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сможет отправить изменения в базу данных. Если для проверок оптимистической блокировки требуются исходные значения и/или метки времени, клиент должен предоставить их обратно на средний уровень.  
  
 В приложениях ASP.NET <xref:System.Web.UI.WebControls.LinqDataSource> управляет большей частью данного сложного процесса. Дополнительные сведения см. в разделе [NIB: Обзор элемента управления веб-сервера LinqDataSource](https://msdn.microsoft.com/library/104cfc3f-7385-47d3-8a51-830dfa791136).  
  
## <a name="additional-resources"></a>Дополнительные ресурсы  
 Дополнительные сведения о развертывании многоуровневого приложения, использующего [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], см. в следующих разделах.  
  
-   [N-уровневое использование LINQ to SQL с ASP.NET](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-aspnet.md)  
  
-   [N-уровневое использование LINQ to SQL с веб-службами](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md)  
  
-   [LINQ to SQL и тесно связанные клиентские/серверные приложения](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-with-tightly-coupled-client-server-applications.md)  
  
-   [Реализация N-уровневой бизнес-логики](../../../../../../docs/framework/data/adonet/sql/linq/implementing-business-logic-linq-to-sql.md)  
  
-   [Получение данных и операции создания, обновления и удаления в N-уровневых приложениях (LINQ to SQL)](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md)  
  
 Дополнительные сведения о многоуровневых приложениях, использующих ADO.NET DataSets, см. в разделе [работа с наборами данных в n уровневых приложениях](/visualstudio/data-tools/work-with-datasets-in-n-tier-applications).  
  
## <a name="see-also"></a>См. также  
 [Основные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
