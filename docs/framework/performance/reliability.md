---
title: Надежность
ms.date: 03/30/2017
helpviewer_keywords:
- SQL Server [.NET Framework]
- managed code, reliability
- reliability [.NET Framework]
- writing reliable code
- code, reliability
ms.assetid: 294aa306-0afe-4cbe-b397-86ba9f1860f8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b00ba0fdf732a864fb4fb757c6012a3d36740b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33395415"
---
# <a name="reliability"></a>Надежность
Крайне важно обеспечить защиту кода, выполняющегося в серверных средах, таких как SQL Server, от асинхронных исключений. Вопросы, обсуждаемые в этой статье, относятся не только к SQL Server, но касаются общих принципов написания надежного кода для любого ведущего приложения, выполняющегося в среде .NET Framework версии 2.0. Тем не менее служба SQL Server приводится в качестве примера, поскольку именно в ней впервые стали широко использоваться новые возможности обеспечения надежности, представленные в версии 2.0.  
  
 В отношении кода, выполняемого в SQL Server, должны действовать более строгие правила надежности, чем для других серверных сред. Это связано с тем, что SQL Server постоянно функционирует на границе потребления ресурсов.  Исключения <xref:System.OutOfMemoryException> и <xref:System.Threading.ThreadAbortException> встречаются в среде SQL Server достаточно часто. Эти правила в целом ориентированы не столько на обеспечение надежности, сколько на гарантию корректного завершения сбоем полностью доверенного управляемого кода при повторном использовании на уровне <xref:System.AppDomain>, что является основным способом обеспечить согласованность и доступность сервера.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Программирование SQL Server и атрибуты защиты ведущего приложения](../../../docs/framework/performance/sql-server-programming-and-host-protection-attributes.md)  
 Описывает использование атрибута <xref:System.Security.Permissions.HostProtectionAttribute> в SQL Server для ограничения выполнения управляемого кода.  
  
 [Рекомендации по обеспечению надежности](../../../docs/framework/performance/reliability-best-practices.md)  
 Содержит рекомендации по написанию кода, отвечающего требованиям надежности.  
  
 [Области ограниченного выполнения](../../../docs/framework/performance/constrained-execution-regions.md)  
 Описывает функции и поведения областей ограниченного выполнения (CER).  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
  
 <xref:System.Security.Permissions.HostProtectionResource>
