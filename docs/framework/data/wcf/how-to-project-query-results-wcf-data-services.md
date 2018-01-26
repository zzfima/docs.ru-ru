---
title: "Практическое руководство. Проекция результатов запроса (WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- projection [WCF Data Services]
- WCF Data Services, projection
- query projection [WCF Data Services]
- WCF Data Services, querying
ms.assetid: 474ac625-8770-43ba-8320-d3315ea9530f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 80c6216315ca1fb1200e12bca89ae8ef27652947
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-project-query-results-wcf-data-services"></a>Практическое руководство. Проекция результатов запроса (WCF Data Services)
Проекция представляет собой механизм уменьшения объема возвращаемых запросом данных путем указания того, что в ответе возвращаются только определенные свойства сущности. Можно выполнить проекции результатов [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] запросов или с помощью `$select` параметра запроса или с помощью [выберите](~/docs/csharp/language-reference/keywords/select-clause.md) предложение ([выберите](~/docs/visual-basic/language-reference/queries/select-clause.md) в Visual Basic) в запросе LINQ. Дополнительные сведения см. в разделе [запросы к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и клиентские классы данных создаются после выполнения [краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показан запрос LINQ, проецирующий сущности Customers в новый тип CustomerAddress, который содержит только зависящие от адреса свойства плюс свойство- идентификатор. Этот класс `CustomerAddress` определен на клиенте и помечается с помощью атрибута, таким образом библиотека клиентов может распознать его как тип сущности.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddress)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddress)]  
  
## <a name="example"></a>Пример  
 В следующем примере показан запрос LINQ, который проецирует возвращаемые сущности Customer в новый тип CustomerAddressNonEntity, который содержит только зависящие от адреса свойства и не содержит свойство-идентификатор. Этот класс `CustomerAddressNonEntity` определен на клиенте и не помечается с помощью атрибута как тип сущности.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddressnonentity)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddressnonentity)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано определение `CustomerAddress``CustomerAddressNonEntity` типов, используемых в предыдущих примерах.  
  
 [!code-csharp[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customeraddress.cs#customeraddressdefinition)]
 [!code-vb[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customeraddress.vb#customeraddressdefinition)]
