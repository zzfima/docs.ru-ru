---
title: Пользовательские привязки
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, endpoints
- Windows Communication Foundation, configuration
ms.assetid: 58532b6d-4eea-4a4f-854f-a1c8c842564d
ms.openlocfilehash: a4b3abfe9be25c9080a362eb4a6e4c7b070528f1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797234"
---
# <a name="custom-bindings"></a>Пользовательские привязки

Класс <xref:System.ServiceModel.Channels.CustomBinding> можно использовать, когда ни одна из системных привязок не соответствует требованиям службы. Все привязки создаются из упорядоченных наборов элементов привязки. Пользовательские привязки можно создавать из набора предоставляемых системой элементов привязки или в них можно включать определяемые пользователем элементы привязки. Пользовательские элементы привязки можно применять, например, для использования в конечной точке службы новых транспортов или кодировщиков. Рабочие примеры см. в разделе [образцы пользовательских привязок](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751479(v=vs.90)). Дополнительные сведения см. в разделе [ \<CustomBinding >](../../configure-apps/file-schema/wcf/custombinding.md).

## <a name="construction-of-a-custom-binding"></a>Создание пользовательской привязки

Пользовательские привязки создаются с использованием одного из конструкторов <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> из коллекции элементов привязки, которые располагаются в определенном порядке.

- Вверху расположен необязательный класс <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>, который разрешает поток транзакций.

- Далее следует необязательный класс <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>, который обеспечивает сеанс и механизмы сортировки, в соответствии со спецификацией WS-ReliableMessaging. Сеанс может включать посредников SOAP и транспорта.

- Далее следует необязательный класс <xref:System.ServiceModel.Channels.SecurityBindingElement>, который предоставляет возможности безопасности, такие как авторизация, проверка подлинности, защита и конфиденциальность.

- Далее следует необязательный класс <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>, который обеспечивает возможность двусторонней дуплексной связи с транспортным протоколом, изначально не поддерживающим дуплексную связь, таким как HTTP.

- Далее следует необязательный класс <xref:System.ServiceModel.Channels.OneWayBindingElement>), который обеспечивает одностороннюю связь.

- Далее следует обязательный элемент привязки безопасности потока, который может быть одним из следующих.

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- Далее следует обязательный элемент привязки для кодирования сообщений. Можно использовать свой кодировщик транспорта или одну из трех привязок кодировки сообщений:

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

Внизу расположен обязательный элемент транспорта. Вы можете использовать собственный транспорт или один из следующих элементов привязки транспорта Windows Communication Foundation (WCF) предоставляет следующие возможности.

- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>

В следующей таблице приведены сводные данные по параметрам каждого уровня.

|Уровень|Параметры|Обязательно|
|-----------|-------------|--------------|
|Транзакции|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|Нет|
|Надежность|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|Нет|
|Безопасность|<xref:System.ServiceModel.Channels.SecurityBindingElement>|Нет|
|кодировка|Текст, двоичное, механизм оптимизации передачи сообщений (MTOM), пользовательское|Да|
|Transport|TCP, HTTP, HTTPS, именованные каналы (также называются IPC), одноранговый (P2P), очередь сообщений (также называется MSMQ), пользовательский|Да|

Кроме того, можно определить собственные элементы привязки и вставить их между любыми из приведенных выше заданных уровней.

## <a name="see-also"></a>См. также

- [Общие сведения о создании конечных точек](../endpoint-creation-overview.md)
- [Использование привязок для настройки служб и клиентов](../using-bindings-to-configure-services-and-clients.md)
- [Привязки, предоставляемые системой](../system-provided-bindings.md)
- [Практическое руководство. Настройка привязки, предоставляемой системой](how-to-customize-a-system-provided-binding.md)
- [\<customBinding >](../../configure-apps/file-schema/wcf/custombinding.md)
- [Пользовательская привязка](../samples/custom-binding.md)
