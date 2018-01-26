---
title: "Практическое руководство. Создание фабрики каналов и ее использование для создания каналов и управления ими"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 018dcc30-9f61-419e-af8e-412a85e8d282
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d41dfc85df1b706028fd95465596a980c040d512
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels"></a>Практическое руководство. Создание фабрики каналов и ее использование для создания каналов и управления ими
Класс <xref:System.ServiceModel.DuplexChannelFactory%601> предоставляет средства для создания и управления дуплексными каналами различных типов, которые используются клиентами для передачи сообщений в конечные точки служб и приема сообщений из конечных точек служб.  
  
## <a name="example"></a>Пример  
 В следующем коде показано создание фабрики каналов и ее использование для создания каналов и управления ими.  
  
 [!code-csharp[S_CustomAuthentication#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_customauthentication/cs/instance.cs#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.DuplexChannelFactory%601>
