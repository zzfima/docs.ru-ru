---
title: 'Учебник: Начало работы с приложениями Windows Communication Foundation'
description: Эти учебники дают представление о создании приложений WCF.
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: df73f953372202796cebce9d3e3f28bd617c67ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184114"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a>Учебник: Начало работы с приложениями Windows Communication Foundation
Следующие учебники познакомят вас с опытом программирования Фонда коммуникаций Windows (WCF). Работа явивая эти учебники для того, чтобы дать вам вводное понимание шагов, необходимых для создания приложений WCF. После завершения работы у вас будет запущенная служба WCF и клиент WCF, который звонит в службу.

Учебник предполагает, что вы используете Visual Studio в качестве среды разработки. Если вы используете другую среду разработки, игнорируйте инструкции Visual Studio.

Для примера приложений WCF, которые можно загрузить и запустить, [см.](samples/index.md) Для введения в образцы, [см. Начало образца](samples/getting-started-sample.md).

Для получения более подробной информации о создании сервисов и клиентов, [см.](basic-wcf-programming.md)

## <a name="wcf-tutorials"></a>Учебники WCF

В первых трех учебниках описывается, как определить контракт на обслуживание WCF, как его реализовать и как его разместить. Создаваемый сервис является самоуправляемым в приложении консоли. Вы также можете размещать услуги в рамках служб ы информации о Интернете (IIS). Для получения дополнительной информации [см.](feature-details/how-to-host-a-wcf-service-in-iis.md) Хотя вы используете код для настройки службы в учебнике, вы также можете [настроить службы в файле конфигурации.](configuring-services-using-configuration-files.md)

- [Учебник: Определить контракт на обслуживание](how-to-define-a-wcf-service-contract.md)

    Вы создаете контракт WCF с пользовательским интерфейсом. Этот контракт определяет функциональность, которую предоставляет служба.

- [Учебник: Реализация сервисного контракта](how-to-implement-a-wcf-contract.md)

    После определения контракта необходимо реализовать его с помощью класса обслуживания.

- [Учебник: Хост и запустить базовую услугу](how-to-host-and-run-a-basic-wcf-service.md)

    Настройте конечную точку для службы и разместите службу в консольном приложении. Чтобы служба стала активной, необходимо настроить ее и разместить в среде выполнения времени. Эта среда времени выполнения создает службу и контролирует ее контекст и срок службы.

Следующие два учебника описывают, как создавать, настраивать и использовать клиентское приложение для вызова операций, которые предоставляет служба. Службы публикуют доступные метаданные, определяющие сведения, необходимые клиентским приложениям для взаимодействия со службой. Visual Studio автоматизирует процесс доступа к этим метаданным и использует их для построения клиентского приложения для службы. Если вы решите не использовать Visual Studio, вы можете использовать [инструмент ServiceModel Metadata Utility (*Svcutil.exe)*](servicemodel-metadata-utility-tool-svcutil-exe.md) вместо этого.

- [Учебник: Создание клиента](how-to-create-a-wcf-client.md)

    Извлекать метаданные для создания прокси-сервера клиента WCF из службы WCF. Вы получаете метаданные с помощью Visual Studio для добавления ссылки на услуги или можете использовать инструмент ServiceModel Metadata Utility. Вы указываете конечную точку, которую клиент использует для доступа к службе.

- [Учебник: Используйте клиента](how-to-use-a-wcf-client.md)

    Используйте прокси-сервер клиента WCF для вызова службы операций.

## <a name="reference"></a>Справочник

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a>См. также раздел

- [Общие сведения](conceptual-overview.md)
- [Руководство по документации](guide-to-the-documentation.md)
- [Что такое Фонд коммуникации Windows](whats-wcf.md)
- [Подробные сведения о возможностях WCF](feature-details/index.md)
- [Базовый жизненный цикл программирования](basic-programming-lifecycle.md)
- [Создание клиентов](building-clients.md)
- [Базовое программирование WCF](basic-wcf-programming.md)
- [Как: Создать дуплексный контракт](feature-details/how-to-create-a-duplex-contract.md)
- [Как: Услуги доступа с дуплексным контрактом](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [СервисМодель Метадата Утилита инструмент (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Как: Используйте Svcutil.exe для загрузки метаданных документов](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [Как: Публикация метаданных для службы с помощью файла конфигурации](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Использование привязок для настройки служб и клиентов](using-bindings-to-configure-services-and-clients.md)
- [Начало образца](samples/getting-started-sample.md)
- [Образцы Фонда связи Windows](samples/index.md)
- [Резидентное размещение](samples/self-host.md)
