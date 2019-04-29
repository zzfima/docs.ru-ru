---
title: Примеры - WCF служб
ms.date: 03/30/2017
ms.assetid: 462a2218-f8c6-4fb7-95bc-64765459c429
ms.openlocfilehash: 3fbca09a7b50a15299cb8e805ac84c60e4b78fa7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967548"
---
# <a name="services"></a>Службы

Этот раздел содержит образцы, демонстрирующие службы Windows Communication Foundation (WCF).

## <a name="in-this-section"></a>Содержание раздела

- [Размещение](../../../../docs/framework/wcf/feature-details/hosting.md)\
Демонстрирует размещение служб WCF.

- [Взаимодействие со службой](service-interoperability.md)\
Показывает взаимодействие между WCF и другими технологиями служб.

- [Поведения](behaviors.md)\
Демонстрирует поведение службы WCF.

- [Безопасность службы](service-security.md)\
Демонстрирует безопасность службы WCF.

- [Упрощенная конфигурация служб WCF](simplified-configuration-for-wcf-services.md)\
Показано, как реализовать и настроить типизированные службы и клиента с помощью WCF.

- [Использование стандартных конечных точек](usage-of-standard-endpoints.md)\
Демонстрирует использование стандартных конечных точек в файлах конфигурации службы.

- [Расширенная политика защиты](extended-protection-policy.md)\
Демонстрирует расширенную защиту, защитную инициативу, направленную на отражение атак типа «злоумышленник в середине».

- [Производство канала настройки](configuration-channel-factory.md)\
Демонстрирует использование действия класса <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>.

- [Адресация](addressing.md)\
Показаны различные аспекты и функции адресов конечных точек.

- [Императивные](imperative.md)\
Показывает, как определить привязку <xref:System.ServiceModel.WSHttpBinding> для службы в коде, вместо того чтобы определять привязку `wsHttpBinding` в конфигурации.

- [Несколько контрактов](multiple-contracts.md)\
Демонстрируется способ реализации нескольких контрактов в службе и способ настройки конечных точек для взаимодействия с каждым из реализованных контрактов.

- [Несколько конечных точек](multiple-endpoints.md)\
Показано, как настроить несколько конечных точек на службе и как взаимодействовать с каждой конечной точкой со стороны клиента.

- [Несколько конечных точек по одному ListenUri](multiple-endpoints-at-a-single-listenuri.md)\
Показана служба, в которой размещается несколько конечных точек по одному адресу `ListenUri`.

- [OperationContextScope](operationcontextscope.md)\
Демонстрируется способ отправки дополнительной информации при вызове функции WCF с помощью заголовков.

- [Описание службы](service-description.md)\
Демонстрируется процесс извлечения службой данных описания службы в среде выполнения.

- [ConcurrencyMode.Reentrant](concurrencymode-reentrant.md)\
Демонстрируется использование повторного входа режима параллелизма в реализации службы.