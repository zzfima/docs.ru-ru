---
title: Практическое руководство. Создание фабрики каналов и ее использование для создания каналов и управления ими
ms.date: 03/30/2017
ms.assetid: 018dcc30-9f61-419e-af8e-412a85e8d282
ms.openlocfilehash: 6ed10cb92af03440848bd29302f8240698d0cbae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62039394"
---
# <a name="how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels"></a>Практическое руководство. Создание фабрики каналов и ее использование для создания каналов и управления ими
Класс <xref:System.ServiceModel.DuplexChannelFactory%601> предоставляет средства для создания и управления дуплексными каналами различных типов, которые используются клиентами для передачи сообщений в конечные точки служб и приема сообщений из конечных точек служб.  
  
## <a name="example"></a>Пример  
 В следующем коде показано создание фабрики каналов и ее использование для создания каналов и управления ими.  
  
 [!code-csharp[S_CustomAuthentication#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_customauthentication/cs/instance.cs#1)]  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.DuplexChannelFactory%601>
