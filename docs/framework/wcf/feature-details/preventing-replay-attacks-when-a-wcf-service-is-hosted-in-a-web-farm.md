---
title: "Предотвращение атак воспроизведения, когда служба WCF размещена на веб-ферме"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c2ed695-7a31-4257-92bd-9e9731b886a5
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ba1a511442fead369fca7ca1e04a26dfacdde53b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="preventing-replay-attacks-when-a-wcf-service-is-hosted-in-a-web-farm"></a>Предотвращение атак воспроизведения, когда служба WCF размещена на веб-ферме
При использовании безопасности сообщений служба WCF предотвращает атаки путем воспроизведения NONCE из входящего сообщения и проверки внутренней`InMemoryNonceCache` на наличие созданного NONCE. Если он есть, то сообщение удаляется как повторное. Когда служба WCF размещается в веб-ферме, свойство `InMemoryNonceCache` не разделяется всеми узлами веб-фермы и служба уязвима для атак с повторением пакетов.  Для устранения подобной угрозы данный сценарий WCF 4.5 предоставляет точку расширяемости, которая позволяет реализовать собственный кэш NONCE. Это осуществляется наследованием класса от абстрактного класса <xref:System.ServiceModel.Security.NonceCache>.  
  
## <a name="noncecache-implementation"></a>Реализация NonceCache  
 Чтобы реализовать собственный кэш общего NONCE, унаследуйте класс от <xref:System.ServiceModel.Security.NonceCache> и переопределите метод <xref:System.ServiceModel.Security.NonceCache.CheckNonce%2A> и <xref:System.ServiceModel.Security.NonceCache.TryAddNonce%2A>. <xref:System.ServiceModel.Security.NonceCache.CheckNonce%2A> будет проверять, существует ли указанный NONCE в кэше. <xref:System.ServiceModel.Security.NonceCache.TryAddNonce%2A> будет пытаться добавить NONCE в кэш. После реализации класса создается его экземпляр, который назначается объекту <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.NonceCache%2A> для обнаружения повторных сообщений на стороне клиента и назначается объекту <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NonceCache%2A> для обнаружения подобных атак на стороне сервера. Для этой возможности нет стандартной конфигурации параметров.  
  
## <a name="see-also"></a>См. также  
 [Безопасность сообщений](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 [SymmetricSecurityBindingElement](../../../../docs/framework/wcf/diagnostics/wmi/symmetricsecuritybindingelement.md)
