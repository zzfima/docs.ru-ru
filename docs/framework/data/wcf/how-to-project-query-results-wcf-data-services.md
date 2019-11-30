---
title: Практическое руководство. Проекция результатов запроса (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- projection [WCF Data Services]
- WCF Data Services, projection
- query projection [WCF Data Services]
- WCF Data Services, querying
ms.assetid: 474ac625-8770-43ba-8320-d3315ea9530f
ms.openlocfilehash: 1e94b5f65229887b2d310f15499a2b14ef7c0536
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569002"
---
# <a name="how-to-project-query-results-wcf-data-services"></a>Практическое руководство. Проекция результатов запроса (WCF Data Services)
Проекция представляет собой механизм уменьшения объема возвращаемых запросом данных путем указания того, что в ответе возвращаются только определенные свойства сущности. Проекции результатов WCF Data Services запроса можно выполнять либо с помощью параметра запроса `$select`, либо с помощью предложения [SELECT](../../../csharp/language-reference/keywords/select-clause.md) ([выберите](../../../visual-basic/language-reference/queries/select-clause.md) в Visual Basic) в запросе LINQ. Дополнительные сведения см. [в разделе запросы к службе данных](querying-the-data-service-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и классы данных клиента создаются при завершении [краткого руководства по WCF Data Services](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показан запрос LINQ, проецирующий сущности Customer в новый тип CustomerAddress, который содержит только зависящие от адреса свойства плюс свойство идентификатора. Этот класс `CustomerAddress` определен на клиенте и помечается с помощью атрибута, таким образом библиотека клиентов может распознать его как тип сущности.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#selectcustomeraddress)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#selectcustomeraddress)]  
  
## <a name="example"></a>Пример  
 В следующем примере показан запрос LINQ, который проецирует возвращаемые сущности Customer в новый тип CustomerAddressNonEntity, который содержит только зависящие от адреса свойства и не содержит свойства идентификатора. Этот класс `CustomerAddressNonEntity` определен на клиенте и не помечается с помощью атрибута как тип сущности.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#selectcustomeraddressnonentity)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#selectcustomeraddressnonentity)]  
  
## <a name="example"></a>Пример  
 В следующем примере показаны определения типов `CustomerAddress` и `CustomerAddressNonEntity`, которые используются в предыдущих примерах.  
  
 [!code-csharp[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customeraddress.cs#customeraddressdefinition)]
 [!code-vb[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customeraddress.vb#customeraddressdefinition)]
