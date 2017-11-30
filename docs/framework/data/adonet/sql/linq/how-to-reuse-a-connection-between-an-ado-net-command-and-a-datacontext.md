---
title: "Практическое руководство. Повторное использование соединения между командой ADO.NET и контекстом DataContext"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 483a97817162140af61df6a58c3e9ab003235c74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a><span data-ttu-id="915c9-102">Практическое руководство. Повторное использование соединения между командой ADO.NET и контекстом DataContext</span><span class="sxs-lookup"><span data-stu-id="915c9-102">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>
<span data-ttu-id="915c9-103">Поскольку [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] является частью [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] семейства технологий и основан на службах, предоставленных [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], вы можете повторно использовать соединение между [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] команды и <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="915c9-103">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] is a part of the [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] family of technologies and is based on services provided by [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], you can reuse a connection between an [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] command and a <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="915c9-104">Пример</span><span class="sxs-lookup"><span data-stu-id="915c9-104">Example</span></span>  
 <span data-ttu-id="915c9-105">В следующем примере показано повторное использование подключения между командой [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] и <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="915c9-105">The following example shows how to reuse the same connection between an [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] command and the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="915c9-106">См. также</span><span class="sxs-lookup"><span data-stu-id="915c9-106">See Also</span></span>  
 [<span data-ttu-id="915c9-107">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="915c9-107">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="915c9-108">ADO.NET и LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="915c9-108">ADO.NET and LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)  
 [<span data-ttu-id="915c9-109">Взаимодействие с базой данных</span><span class="sxs-lookup"><span data-stu-id="915c9-109">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
