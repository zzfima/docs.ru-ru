---
title: Учебник. Начало работы с приложениями Windows Communication Foundation
description: Эти учебники предоставляет вводные сведения по созданию приложений WCF.
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: d4613edefeb8db2c0d1e11e925f8ac41329efb0d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137934"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a>Учебник. Начало работы с приложениями Windows Communication Foundation
Следующие учебники представлена в Windows Communication Foundation (WCF) опыт программирования. Работе с этими руководствами, в порядке обеспечит начальное понимание шагов, необходимых для создания приложений WCF. После завершения, вы получите работающей службы WCF и клиент WCF, который вызывает службу. 

В учебнике предполагается, что вы используете Visual Studio в качестве среды разработки. Если используется другая среда разработки, игнорировать инструкции конкретных Visual Studio. 

Образцы приложений WCF, которые можно загрузить и запустить, см. в разделе [образцов Windows Communication Foundation](samples/index.md). Общие сведения о примерах, см. в разделе [Приступая к работе образца](samples/getting-started-sample.md).

Дополнительные сведения о создании служб и клиентов см. в разделе [базовое Программирование WCF](basic-wcf-programming.md).

## <a name="wcf-tutorials"></a>Учебники по WCF

Первые три руководства описывают, как определить контракт службы WCF, как реализовать его и как разместить его. Создаваемая служба является резидентной в консольном приложении. Вы также можете разместить службы в группе Microsoft Internet Information Services (IIS). Дополнительные сведения см. в разделе [Как Размещение службы WCF в IIS](feature-details/how-to-host-a-wcf-service-in-iis.md). Несмотря на то, что для настройки службы в этом руководстве используется код, вы также можете [настраивать службы в файле конфигурации](configuring-services-using-configuration-files.md). 

- [Учебник. Определите контракт службы](how-to-define-a-wcf-service-contract.md)

    Создание контракта WCF с интерфейсом, определяемые пользователем. Этот контракт определяет функциональность, предоставленную службой.

- [Учебник. Реализация контракта службы](how-to-implement-a-wcf-contract.md)

    После определения контракта, должен быть реализован классом службы.

- [Учебник. Размещение и запуск базовой службы](how-to-host-and-run-a-basic-wcf-service.md)

    Настройте конечную точку для службы и разместите службу в консольном приложении. Для службы станет активным необходимо настроить его и разместить ее внутри среды выполнения. Эта среда выполнения создает службу и управляет ее контекстом и временем существования.

Следующие два руководства описывается, как создавать, настраивать, а предоставляет используйте клиентское приложение для вызова операций службы. Службы публикуют доступные метаданные, определяющие сведения, необходимые клиентским приложениям для взаимодействия со службой. Visual Studio автоматизирует процесс доступа к этим метаданным и использует его для создания клиентского приложения для службы. Если вы решили не использовать Visual Studio, можно использовать [средство ServiceModel Metadata Utility (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) вместо этого.

- [Учебник. Создание клиента](how-to-create-a-wcf-client.md)

    Получение метаданных для создания прокси клиента WCF из службы WCF. Получить метаданные с помощью Visual Studio для добавления ссылки на службу, или можно использовать средство ServiceModel Metadata Utility. Можно указать конечную точку, клиент использует для доступа к службе.

- [Учебник. Использование клиента](how-to-use-a-wcf-client.md)

    Используйте прокси клиента WCF для вызова операций службы.

## <a name="reference"></a>Ссылка

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a>См. также

- [Общие сведения](conceptual-overview.md)
- [Руководство по документации](guide-to-the-documentation.md)
- [Что такое Windows Communication Foundation](whats-wcf.md)
- [Подробные сведения о возможностях WCF](feature-details/index.md)
- [Базовый жизненный цикл программирования](basic-programming-lifecycle.md)
- [Создание клиентов](building-clients.md)
- [Базовое Программирование WCF](basic-wcf-programming.md)
- [Практическое руководство. Создание дуплексного контракта](feature-details/how-to-create-a-duplex-contract.md)
- [Практическое руководство. Службы доступа с дуплексным контрактом](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [Служебное средство ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Практическое руководство. Использование Svcutil.exe для загрузки документов метаданных](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [Практическое руководство. Публикация метаданных для службы с помощью файла конфигурации](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Использование привязок для настройки служб и клиентов](using-bindings-to-configure-services-and-clients.md)
- [Пример для начала работы](samples/getting-started-sample.md)
- [Примеры Windows Communication Foundation](samples/index.md)
- [Резидентное размещение](samples/self-host.md)
