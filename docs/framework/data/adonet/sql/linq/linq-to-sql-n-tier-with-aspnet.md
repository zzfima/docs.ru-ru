---
title: "N-уровневое использование LINQ to SQL с ASP.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 9b71113ca76eec5888aed2123ec9c55ad66a72bf
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a>N-уровневое использование LINQ to SQL с ASP.NET
В приложениях [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] , использующих [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], применяется серверный веб-элемент управления <xref:System.Web.UI.WebControls.LinqDataSource> . Этот элемент управления обрабатывает большую часть логики, необходимой для выполнения запросов в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], передает данные в браузер, извлекает их и отправляет классу [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> , который затем обновляет базу данных. Чтобы элемент управления полностью обрабатывал передачу данных между [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и браузером, достаточно настроить его в разметке. Поскольку элемент управления обрабатывает взаимодействия с уровнем представления, а [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] обрабатывает взаимодействие с уровнем данных, то в многоуровневых приложениях [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] особое внимание следует уделять написанию пользовательской бизнес-логики.  
  
 Дополнительные сведения о `LINQDataSource`см. в разделе [NIB. Обзор элемента управления веб-сервера LinqDataSource](http://msdn.microsoft.com/en-us/104cfc3f-7385-47d3-8a51-830dfa791136).  
  
## <a name="see-also"></a>См. также  
 [N-уровневые и удаленные приложения и LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)
