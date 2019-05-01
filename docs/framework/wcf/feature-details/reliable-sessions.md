---
title: Надежные сеансы
ms.date: 03/30/2017
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
ms.openlocfilehash: 9a2cd06c4c5a73d9fb5c4c7f09632e10c3eb0d87
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991163"
---
# <a name="reliable-sessions"></a>Надежные сеансы

В этом разделе описывается, какие Windows Communication Foundation (WCF) надежный сеанс, чего он используется, как и когда им воспользоваться, какие конфигурации привязки поддерживают его, и ссылки на рекомендации. В следующей таблице собраны сведения о ключевых вопросах и связанных разделах.

Надежные сеансы WCF предоставляет функции, то, что сообщения, которыми обмениваются конечные точки, передаются по SOAP или через транспортных посредников и доставляются только один раз и, возможно, в том же порядке, в котором они были отправлены.

Чтобы использовать надежные сеансы с приложения WCF, используйте один из предоставляемых системой привязок в WCF, которые поддерживают надежные сеансы, по умолчанию или в качестве параметра или создать собственную пользовательскую привязку, которая поддерживает сеанс.

## <a name="in-this-section"></a>В этом разделе

[Общие сведения о надежных сеансах](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) описание надежных сеансов, когда следует использовать их, различных привязок, которые поддерживают надежные сеансы, и как они работают.

[Практическое руководство. Exchange сообщения в рамках надежного сеанса](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) описывается, как создать надежный сеанс по протоколу HTTP с помощью пользовательской привязки, заданной в конфигурации.

[Практическое руководство. Защита сообщений с помощью надежных сеансов](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) описываются способы защиты надежного сеанса.

[Практическое руководство. Создать привязку Custom надежного сеанса с помощью протокола HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) описывается, как создать надежный сеанс по протоколу HTTPS.

[Советы и рекомендации для надежных сеансов](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) описывает некоторые рекомендации, связанные с использованием надежного сеанса.

## <a name="reference"></a>Ссылка

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a>См. также

- [Очереди и надежные сеансы](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
- [Сеансы, экземпляры и параллелизм](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
