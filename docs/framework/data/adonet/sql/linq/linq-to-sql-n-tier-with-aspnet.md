---
title: N-уровневое использование LINQ to SQL с ASP.NET
ms.date: 03/30/2017
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
ms.openlocfilehash: 435f24a0f105a24bbec91a7e70dc5aaaa25e5649
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a>N-уровневое использование LINQ to SQL с ASP.NET
В приложениях [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] , использующих [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], применяется серверный веб-элемент управления <xref:System.Web.UI.WebControls.LinqDataSource> . Этот элемент управления обрабатывает большую часть логики, необходимой для выполнения запросов в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], передает данные в браузер, извлекает их и отправляет классу [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> , который затем обновляет базу данных. Чтобы элемент управления полностью обрабатывал передачу данных между [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и браузером, достаточно настроить его в разметке. Поскольку элемент управления обрабатывает взаимодействия с уровнем представления, а [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] обрабатывает взаимодействие с уровнем данных, то в многоуровневых приложениях [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] особое внимание следует уделять написанию пользовательской бизнес-логики.  
  
 Дополнительные сведения о `LINQDataSource`, в разделе [NIB: Обзор элемента управления веб-сервера LinqDataSource](http://msdn.microsoft.com/library/104cfc3f-7385-47d3-8a51-830dfa791136).  
  
## <a name="see-also"></a>См. также  
 [N-уровневые и удаленные приложения и LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)
