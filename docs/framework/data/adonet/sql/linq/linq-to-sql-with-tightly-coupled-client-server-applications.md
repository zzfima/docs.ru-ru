---
title: "LINQ to SQL и тесно связанные клиентские/серверные приложения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e083d805-dcf6-459d-b9af-9ef0563f2dd7
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e3879d8eeec498f2855ee2b540f77570ee91109f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="linq-to-sql-with-tightly-coupled-client-server-applications"></a>LINQ to SQL и тесно связанные клиентские/серверные приложения
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]может использоваться на среднем уровне с тесно связанными интеллектуальными клиентами на уровне представления данных. Реализация сценариев, в которых используется доступ к данным только для чтения и не выполняются проверки оптимистического параллелизма на основе исходных значений или меток времени, представляет собой не более сложную задачу, чем сценарии без удаленного взаимодействия. Однако, если база данных требует выполнения проверки оптимистического параллелизма на основе исходных значений, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не предоставляет того уровня поддержки кругового пути данных, который обеспечивается DataSets. Тем не менее, средний уровень [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] может обмениваться данными с клиентами на любой платформе.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]в [!INCLUDE[vs_orcas_long](../../../../../../includes/vs-orcas-long-md.md)] не предоставляет инфраструктуру для отслеживания состояния сущностей после их сериализации в клиента. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]включает ориентированных на службы архитектуры, в где взаимодействия между уровнями данных и представлений невелики и относительно атомарны, но не выполняет никаких обратных преобразований исходных значений. Поэтому, если вместе с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] требуется использовать тесно связанный интеллектуальный клиент, а в базе данных используются проверки оптимистического параллелизма на основе исходных значений, необходимо реализовать собственный механизм обмена изменениями между уровнем представления данных и средним уровнем. Стоит ли выполнять эту дополнительную работу ради преимуществ, которые предоставляет [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] на среднем уровне, должен решить разработчик системы. С другой стороны, если в базе данных содержатся метки времени, то нет необходимости разрабатывать пользовательскую логику отслеживания изменений.  
  
## <a name="see-also"></a>См. также  
 [N-уровневые и удаленные приложения и LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)  
 [LINQ to SQL N-уровневые веб-службы](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md)  
 [Работа с наборами данных в N-уровневых приложениях](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20)
