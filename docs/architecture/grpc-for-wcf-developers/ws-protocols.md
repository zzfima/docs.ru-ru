---
title: Протоколы WS-* — gRPC для разработчиков WCF
description: Ознакомьтесь с протоколами WS-*, поддерживаемыми WCF, и альтернативами, доступными в gRPC
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: c8c06a5e23a4d7859165e1c562032055d63d76f7
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503300"
---
# <a name="ws--protocols"></a>Протоколы WS-\*

Одним из реальных преимуществ работы с Windows Communication Foundation (WCF) было поддержка множества существующих стандартных протоколов _WS-\*_ . В этом разделе кратко рассматривается, как gRPC управляет одними и теми же протоколами WS-\* и обсуждает, какие варианты доступны, когда нет альтернативы.

## <a name="metadata-exchange-ws-policy-ws-discovery-and-so-on"></a>Обмен метаданными: WS-Policy, WS-Discovery и т. д.

Службы SOAP предоставляют документы схемы языка описания веб-служб (WSDL) со сведениями, такими как форматы данных, операции или варианты обмена данными. Эту схему можно использовать для создания клиентского кода.

gRPC лучше всего подходит, когда серверы и клиенты создаются из одних и тех же `.proto` файлов, но дополнительное расширение серверного отражения предоставляет способ предоставления динамической информации с работающего сервера. Дополнительные сведения см. в статье пакет NuGet [GRPC. Reflection](https://nuget.org/packages/Grpc.Reflection) и [ C# GRPC Server Reflection](https://github.com/grpc/grpc/blob/master/doc/csharp/server_reflection.md) .

Протокол WS-Discovery используется для поиска служб в локальной сети. службы gRPC обычно находятся в DNS или в реестре службы, например Consul или ZooKeeper.

## <a name="security-ws-security-ws-federation-xml-encryption-and-so-on"></a>Безопасность: WS-Security, WS-Federation, шифрование XML и т. д.

Сведения о безопасности, проверке подлинности и авторизации более подробно описаны в [главе 6](security.md). Но стоит отметить, что, в отличие от WCF, gRPC не поддерживает шифрование WS-Security, WS-Federation или XML. Несмотря на это, gRPC обеспечивает отличную безопасность. Весь сетевой трафик gRPC автоматически шифруется при использовании HTTP/2 через TLS. Сертификаты X509 можно использовать для взаимной проверки подлинности клиента или сервера.

## <a name="ws-reliablemessaging"></a>WS-ReliableMessaging

gRPC не предоставляет эквивалент WS-ReliableMessaging. Семантика повторных попыток должна обрабатываться в коде, возможно, с такой библиотекой, как [Polly](https://github.com/App-vNext/Polly). При работе в Kubernetes или аналогичных средах оркестрации [сети служб](service-mesh.md) также могут помочь обеспечить надежный обмен сообщениями между службами.

## <a name="ws-transaction-ws-coordination"></a>WS-Transaction, WS-координация

Реализация распределенных транзакций в WCF использует Microsoft координатор распределенных транзакций (MSDTC). Он работает с диспетчерами ресурсов, которые специально поддерживают такие службы, как SQL Server, MSMQ или файловые системы Windows. В современных микрослужбах нет эквивалента, часть из-за широкого спектра используемых технологий. Обсуждение транзакций см. [в приложении а](appendix.md).

>[!div class="step-by-step"]
>[Назад](error-handling.md)
>[Вперед](migrate-wcf-to-grpc.md)
