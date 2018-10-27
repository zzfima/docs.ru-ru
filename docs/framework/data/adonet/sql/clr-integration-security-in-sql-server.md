---
title: Безопасность интеграции CLR в SQL Server
ms.date: 03/30/2017
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
ms.openlocfilehash: dfd99155e42f426eeb01c89c433955cc2e3f0178
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2018
ms.locfileid: "49454360"
---
# <a name="clr-integration-security-in-sql-server"></a>Безопасность интеграции CLR в SQL Server
Microsoft SQL Server обеспечивает интеграцию компонентов среды CLR платформы .NET Framework. Интеграция со средой CLR позволяет записывать хранимые процедуры, триггеры, определяемые пользователем типы, определяемые пользователем функции и потоковые возвращающие табличное значение функции, используя любой язык NET Framework, например Microsoft Visual Basic .NET или Microsoft Visual C#.  
  
 Среда CLR поддерживает модель безопасности, называемую управлением доступом для кода (CAS). В этой модели разрешения предоставляются сборкам на основе свидетельства, поставляемого кодом в метаданных. SQL Server интегрирует пользовательскую модель безопасности SQL Server с кодом модели безопасности на основе доступа среды CLR.  
  
## <a name="external-resources"></a>Внешние ресурсы  
 Дополнительные сведения об интеграции со средой CLR в SQL Server см. в следующих ресурсах.  
  
|Ресурс|Описание|  
|--------------|-----------------|  
|[Управление доступом для кода](../../../../../docs/framework/misc/code-access-security.md)|Содержит подразделы, описывающие средства CAS на платформе .NET Framework.|  
|[Безопасность интеграции со средой CLR](/sql/relational-databases/clr-integration/security/clr-integration-security)|Содержит обсуждение модели безопасности для управляемого кода, выполняемого внутри SQL Server.|  
  
## <a name="see-also"></a>См. также  
 [Защита приложений ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Сценарии безопасности приложений в SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [Интеграция среды CLR и SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)  
 [Общие сведения об ADO.NET](../../../../../docs/framework/data/adonet/ado-net-overview.md)
