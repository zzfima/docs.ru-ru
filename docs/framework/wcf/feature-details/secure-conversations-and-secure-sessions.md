---
title: Безопасные диалоги и безопасные сеансы
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
caps.latest.revision: 13
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 502064ce30f6e117168834643a116d3983811fb8
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="secure-conversations-and-secure-sessions"></a>Безопасные диалоги и безопасные сеансы
Функцией [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] является возможность установления безопасных сеансов между двумя конечными точками, проверяющими подлинность друг друга и согласующими процесс шифрования и цифровой подписи. Например, конечная точка службы может требовать, чтобы клиентская конечная точка передавала для проверки подлинности маркер безопасности, основанный на сертификате X.509. После завершения проверки подлинности клиента конечная точка службы возвращает клиенту маркер контекста безопасности (SCT), который затем используется для обеспечения безопасности всех последующих сообщений в сеансе. Установление такого безопасного сеанса повышает эффективность набора сообщений, которыми обмениваются эти две конечные точки, так как маркер SCT имеет симметричный ключ. При создании цифровой подписи или шифровании набора данных асимметричные ключи, на которых основаны сертификаты X.509, требуют значительно большей вычислительной мощности, чем симметричные ключи.  
  
 Политика начальной загрузки (заданные в разделе 6.2.7 [WS-SecurityPolicy](http://go.microsoft.com/fwlink/?LinkId=99817) стандартные) содержит утверждения безопасности сообщений, используемый для защиты канала и проверки подлинности клиента до обмена RST/SCT и RSTR/SCT. Определенные стандартные привязки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обладают свойством `Security.Message.EstablishSecurityContext`, управляющим использованием безопасного диалога. При использовании пользовательских привязок программу начальной загрузки обозначается вложенности элементов привязки безопасности, либо с помощью [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) в файле конфигурации или вызвав <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> в коде.  
  
 Дополнительные сведения о сеансах см. в разделе [с использованием сеансов](../../../../docs/framework/wcf/using-sessions.md).  
  
## <a name="see-also"></a>См. также  
 [Сеансы, экземпляры и параллелизм](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [Практическое руководство. Создание службы, для которой требуются сеансы](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
