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
ms.openlocfilehash: 396c76cbdb8eada881a5c87edfc2500dcdab3ad4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497169"
---
# <a name="reliable-sessions"></a>Надежные сеансы

В этом разделе описывается, какие Windows Communication Foundation (WCF) надежный сеанс, что он используется, как и когда следует использовать, какие конфигурации привязки поддерживают его, а также приведены ссылки на рекомендации. В следующей таблице собраны сведения о ключевых вопросах и связанных разделах.

Надежный сеанс WCF предоставляет функциям поддержки передаются через посредников SOAP и транспорта сообщений, пересылаемых между конечными точками и доставляются только один раз и, возможно, в том же порядке, в котором они были отправлены.

Чтобы использовать надежные сеансы с приложения WCF, используйте одну из предоставляемых системой привязок в WCF, поддерживающих надежный сеанс по умолчанию или в качестве параметра или создать собственную пользовательскую привязку, поддерживающую сеанса.

## <a name="in-this-section"></a>В этом разделе

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
