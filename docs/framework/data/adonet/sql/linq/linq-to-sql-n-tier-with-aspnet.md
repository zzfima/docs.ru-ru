---
title: N-уровневое использование LINQ to SQL с ASP.NET
ms.date: 03/30/2017
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
ms.openlocfilehash: 1770d84053b57e05d1a4e41919a3eb4122dc73a3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793032"
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a>N-уровневое использование LINQ to SQL с ASP.NET
В приложениях ASP.NET, использующих [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], <xref:System.Web.UI.WebControls.LinqDataSource> используется серверный веб-элемент управления. Этот элемент управления обрабатывает большую часть логики, необходимой для выполнения запросов в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], передает данные в браузер, извлекает их и отправляет классу [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> , который затем обновляет базу данных. Чтобы элемент управления полностью обрабатывал передачу данных между [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и браузером, достаточно настроить его в разметке. Поскольку элемент управления обрабатывает взаимодействие с уровнем представления и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] обрабатывает связь с уровнем данных, основное внимание в ASP.NET многоуровневых приложениях заключается в написании пользовательской бизнес-логики.  
  
 Дополнительные сведения о `LINQDataSource`см. в разделе [Общие сведения о серверном веб-элементе управления LinqDataSource](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100)).  
  
## <a name="see-also"></a>См. также

- [N-уровневые и удаленные приложения и LINQ to SQL](n-tier-and-remote-applications-with-linq-to-sql.md)
