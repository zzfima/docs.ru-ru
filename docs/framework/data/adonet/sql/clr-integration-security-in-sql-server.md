---
title: Безопасность интеграции CLR в SQL Server
ms.date: 03/30/2017
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
ms.openlocfilehash: 4756d13ff52a4c55b48c3ea56d26111029c8a7e4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794568"
---
# <a name="clr-integration-security-in-sql-server"></a>Безопасность интеграции CLR в SQL Server
Microsoft SQL Server обеспечивает интеграцию компонентов среды CLR платформы .NET Framework. Интеграция со средой CLR позволяет записывать хранимые процедуры, триггеры, определяемые пользователем типы, определяемые пользователем функции и потоковые возвращающие табличное значение функции, используя любой язык NET Framework, например Microsoft Visual Basic .NET или Microsoft Visual C#.  
  
 Среда CLR поддерживает модель безопасности, называемую управлением доступом для кода (CAS). В этой модели разрешения предоставляются сборкам на основе свидетельства, поставляемого кодом в метаданных. SQL Server интегрирует пользовательскую модель безопасности SQL Server с кодом модели безопасности на основе доступа среды CLR.  
  
## <a name="external-resources"></a>Внешние ресурсы  
 Дополнительные сведения об интеграции со средой CLR в SQL Server см. в следующих ресурсах.  
  
|Resource|Описание|  
|--------------|-----------------|  
|[Управление доступом для кода](../../../misc/code-access-security.md)|Содержит подразделы, описывающие средства CAS на платформе .NET Framework.|  
|[Безопасность интеграции со средой CLR](/sql/relational-databases/clr-integration/security/clr-integration-security)|Содержит обсуждение модели безопасности для управляемого кода, выполняемого внутри SQL Server.|  
  
## <a name="see-also"></a>См. также

- [Защита приложений ADO.NET](../securing-ado-net-applications.md)
- [Сценарии безопасности приложений в SQL Server](application-security-scenarios-in-sql-server.md)
- [Интеграция среды CLR и SQL Server](sql-server-common-language-runtime-integration.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
