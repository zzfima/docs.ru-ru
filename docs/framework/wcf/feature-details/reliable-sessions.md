---
title: "Надежные сеансы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 53bb63fbbcf92650085514118a5e9464ab2dea30
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="reliable-sessions"></a>Надежные сеансы

В этом разделе рассказывается, что [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] надежного сеанса является то, что он используется, как и когда следует использовать, какие конфигурации привязки поддерживают его, а также приведены ссылки на рекомендации. В следующей таблице собраны сведения о ключевых вопросах и связанных разделах.

Надежный сеанс [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предоставляет функциям поддержки передаются через посредников SOAP и транспорта сообщений, пересылаемых между конечными точками и доставляются только один раз и, возможно, в том же порядке, в котором они были отправлены.

Для применения надежных сеансов в приложении [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] следует использовать предоставляемые системой привязки в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], которые по умолчанию поддерживают надежные сеансы, либо можно создать собственную пользовательскую привязку, которая бы поддерживала такие сеансы.

## <a name="in-this-section"></a>Содержание

[Общие сведения о надежных сеансов](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)   
Описание надежных сеансов, ситуаций, в которых они используются, различных привязок, которые поддерживают надежные сеансы, и принципы их работы.

[Как: обмена сообщениями в ходе надежного сеанса](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)   
Описание процесса создания надежного сеанса через протокол HTTP с помощью пользовательской привязки, заданной в конфигурации.

[Как: защита сообщений с помощью надежных сеансов](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md)   
Обеспечение защиты надежного сеанса.

[Как: Создание пользовательской привязки надежного сеанса с использованием HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)   
Создание надежного сеанса через протокол HTTPS.

[Советы и рекомендации для надежных сеансов](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md)   
Описание некоторых рекомендаций по использованию надежных сеансов.

## <a name="reference"></a>Ссылка

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a>См. также

[Очереди и надежные сеансы](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)   
[Сеансы, экземпляры и параллелизм](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
