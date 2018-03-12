---
title: "Пошаговые руководства и технические получить обзор работы"
description: "Модернизировать существующие приложения .NET с облако Azure и контейнеров Windows | Пошаговые руководства и технические получить обзор работы"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6a2abda3949c1fffc4d731b01e35e58e7c56dac0
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2018
---
# <a name="walkthroughs-and-technical-get-started-overview"></a>Пошаговые руководства и технические получить обзор работы

Для ограничения размера эта электронная книга, дополнительную техническую документацию и полный пошаговые руководства были доступны в репозитории GitHub. Online ряд пошаговых руководств, описанный в этой главе описываются пошаговые установки нескольких сред, которые основаны на контейнеры Windows и развертывания в Azure.

Что каждого пошагового руководства о его целями и высокоуровневые концепции и предоставляет схему задачи, которые участвуют в следующих разделах. Вы можете получить пошаговые руководства, сами в *eShopModernizing* wiki репозитория GitHub приложений на [https://github.com/dotnet-architecture/eShopModernizing/wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki).

## <a name="technical-walkthrough-list"></a>Список примеров технические

Следующие пошаговые руководства работы get содержат согласованное и комплексное техническое руководство для образца приложения, которые можно точности прогнозов и с помощью контейнеры shift, а затем переместите с помощью нескольких вариантов развертывания в Azure.

Для каждой из указанных ниже пошаговых руководствах используется новый образец eShopLegacy и eShopModernizing приложений, которые можно найти на github на сайте [https://github.com/dotnet-architecture/eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).

- **Обзор приложений прежних версий eShop**

- **Упаковываете существующие приложения .NET с помощью контейнеров Windows**

- **Развертывание приложения на основе контейнеров Windows на виртуальных машинах Azure**

- **Развертывание приложений на основе контейнеров Windows на Kubernetes в службе контейнера Azure**

- **Развернуть приложения на основе контейнеров Windows Azure Service Fabric**

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a>Пошаговое руководство 1: Обзор eShop приложений прежних версий

### <a name="technical-walkthrough-availability"></a>Технические руководства доступности

Полные технические пошагового руководства можно найти в репозитории GitHub eShopModernizing вики-сайте:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code)

### <a name="overview"></a>Обзор

В этом пошаговом руководстве можно исследовать начальной реализацию двух примеров приложений прежних версий. Оба образца приложения монолитные архитектуры и были созданы с помощью классической платформе ASP.NET. Одно приложение на базе ASP.NET 4.x MVC; второе приложение зависит от веб-форм ASP.NET 4.x. Оба приложения находятся в [eShopModernizing в репозитории GitHub](https://github.com/dotnet-architecture/eShopModernizing).

Можно упаковываете оба образца приложения, подобно тому, как можно упаковываете классические [Windows Communication Foundation](../../framework/wcf/whats-wcf.md) приложения (WCF) в качестве классического приложения. Пример см. в разделе [eShopModernizingWCFWinForms](https://github.com/dotnet-architecture/eShopModernizingWCFWinForms).

### <a name="goals"></a>Цели

Основная цель данного пошагового руководства, достаточно ознакомиться с этими приложениями и их кода и конфигурации. Можно настроить приложения, которые они создания и фиктивных данных без использования базы данных SQL в целях тестирования. Это необязательная конфигурация основана на внедрение зависимостей несвязанной способом.

### <a name="scenario"></a>Сценарий

Рис. 5-1 показывает простой сценарий исходного приложений прежних версий.

> ![Сценарий простой архитектуры исходного прежних версий приложений](./media/image5-1.png)
>
> **Рис. 5-1**. Сценарий простой архитектуры исходного прежних версий приложений

С точки зрения бизнеса домен оба приложения обеспечивают одного каталога функции управления. Члены команды enterprise eShop будет использовать приложение для просмотра и изменения каталога продуктов. Рис. 5-2 показано на снимках экрана начального приложения.

![Приложения ASP.NET MVC и веб-форм ASP.NET (существующих устаревших технологии)](./media/image5-2.png)

> **Рис. 5-2.** Приложения ASP.NET MVC и веб-форм ASP.NET (существующих устаревших технологии)

Это веб-приложений, которые используются для просмотра и изменения записей каталога. Тот факт, что оба приложения поставлять же бизнеса и функциональные возможности не просто для сравнения. Вы увидите аналогичный процесс изменения для приложений, созданных с помощью платформы ASP.NET MVC и веб-форм ASP.NET.

Зависимости в ASP.NET 4.x или более ранних версий (либо для MVC для веб-форм) означает, эти приложения, которые не будут работать в .NET Core, если код полностью переписан с помощью ASP.NET Core MVC. Этот пример демонстрирует точки, если вы не хотите повторно создать архитектуру или переписать код, можно упаковываете существующих приложений и по-прежнему использовать те же технологии .NET и тот же код. Вы увидите, как запустить такие контейнеры, без изменений для устаревшего кода приложения.

### <a name="benefits"></a>Преимущества

Преимущества этого пошагового руководства, простой: просто ознакомиться с конфигурацией код и приложения, в зависимости от внедрения зависимостей. Затем можно поэкспериментировать с такой подход при упаковываете и развертывания в различных средах, в будущем.

### <a name="next-steps"></a>Следующие шаги

Это содержимое более подробное изучение на вики-сайте GitHub.

[https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a>Пример 2: Упаковываете существующие приложения .NET с помощью контейнеров Windows

### <a name="technical-walkthrough-availability"></a>Технические руководства доступности

Полные технические пошагового руководства можно найти в репозитории GitHub eShopModernizing вики-сайте:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)

### <a name="overview"></a>Обзор

Контейнеры Windows используются для улучшения существующих приложений .NET, как и на базе MVC, веб-формы или WCF, производства, разработки и тестовой среды развертывания.

### <a name="goals"></a>Цели

Цель данного руководства — Показать несколько вариантов containerizing существующего приложения .NET Framework. Можно выполнить следующие действия.

- Упаковываете приложение с помощью [2017 г средств Visual Studio для Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 г. или более поздней версии).

- Упаковываете приложение, вручную добавив [Dockerfile](https://docs.docker.com/engine/reference/builder/), а затем с помощью [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).

- Упаковываете приложение с помощью [Img2Docker](https://github.com/docker/communitytools-image2docker-win) инструмента (инструмент открытым исходным кодом из Docker).

В этом пошаговом руководстве уделяется средств Visual Studio 2017 г. для Docker подход, но другие два способа реализации во многом аналогичны отношении с помощью файлов Dockerfile.

### <a name="scenario"></a>Сценарий

Рис. 5-3 показан сценарий, для приложений прежних версий контейнерного eShop.

> ![Схема упрощенной архитектуры приложений в контейнерах в среде разработки](./media/image5-3.png)
>
> **Рис.** Схема упрощенной архитектуры приложений в контейнерах в среде разработки

### <a name="benefits"></a>Преимущества

Существуют преимущества для запуска монолитные приложения в контейнере. Во-первых можно создать изображение приложения. С этого момента каждое развертывание выполняется в той же среде. Каждый контейнер использует ту же версию операционной системы, имеет ту же версию установить зависимости, использует ту же версию .NET framework и создается с помощью тот же процесс. По сути вы управляете зависимости приложения с помощью образа Docker. Зависимости перемещаются вместе с приложением при развертывании контейнеров.

Дополнительным преимуществом является разработчикам возможность выполнения приложения в среде согласованной, предоставляемая контейнеров Windows. Проблемы, которые отображаются только в определенных версиях можно заметили немедленно, вместо распределение результатов в промежуточной или рабочей среде. Различия в средах разработки, членам команды разработчиков имеет меньше значения при запуске приложений в контейнерах.

Контейнерного приложения также имеют плоское кривой горизонтального масштабирования. Контейнерного приложения позволяют имеют несколько приложений и экземпляров службы (с учетом контейнеров) в виртуальной Машины или физического компьютера, по сравнению с развертывания регулярных приложений на компьютере. Это приводит к более поздней версии плотность и меньше требуется ресурсов, особенно при использовании orchestrators как Kubernetes или Service Fabric.

Создание контейнеров в ситуациях, идеальным, не требует внесения изменений в код приложения (C\#). В большинстве случаев необходимо просто Docker развертывания метаданных файлы (файлы Dockerfile и Docker Compose).

### <a name="next-steps"></a>Следующие шаги

Просмотр этого содержимого углубленные на вики-сайте GitHub: [https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a>Пример 3: Развертывание приложения Windows контейнеры на виртуальных машинах Azure

### <a name="technical-walkthrough-availability"></a>Технические руководства доступности

Полные технические пошагового руководства можно найти в репозитории GitHub eShopModernizing вики-сайте:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

### <a name="overview"></a>Обзор

Развертывание на узле Docker в Windows Server 2016 виртуальной машины (VM) в Azure позволяет быстро настроить разработки, тестирования и промежуточные среды. Он также предоставляет единый механизм для тест-инженеры или бизнес-пользователей, для проверки приложения. Виртуальные машины также может быть допустимым Infrastucture как услуги (IaaS) рабочих средах.

### <a name="goals"></a>Цели

Цель данного руководства — Показать несколькими альтернативами вами при развертывании контейнеров Windows на виртуальных машинах Azure, которые основаны на Windows Server 2016 или более поздней версии.

### <a name="scenarios"></a>Сценарии

В этом пошаговом руководстве рассмотрены несколько сценариев.

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a>Сценарий а развернуть в виртуальной Машине Azure из разработки ПК через подключение подсистемы Docker

![Развертывание на Виртуальной машине Azure из разработки ПК через подключение подсистемы Docker](./media/image5-4.png)

> **Рис.** Развертывание на Виртуальной машине Azure из разработки ПК через подключение подсистемы Docker

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a>Сценарий б. развертывание на Виртуальной машине Azure через реестр Docker

![Развертывание на Виртуальной машине Azure через реестр Docker](./media/image5-5.png)

> **Рис.** Развертывание на Виртуальной машине Azure через реестр Docker

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-visual-studio-team-services"></a>Сценарий C: развертывание на Виртуальной машине Azure из элемента конфигурации/CD конвейеры в Visual Studio Team Services

![Развертывание на Виртуальной машине Azure из элемента конфигурации/CD конвейеры в Visual Studio Team Services](./media/image5-6.png)

> **Рис. 5-6**. Развертывание на Виртуальной машине Azure из элемента конфигурации/CD конвейеры в Visual Studio Team Services

### <a name="azure-vms-for-windows-containers"></a>Виртуальные машины Azure для контейнеров Windows

Azure виртуальные машины для контейнеров Windows — это виртуальные машины на основе Windows Server 2016, Windows 10 или более поздних версий, и с подсистемой Dосker Настройка. В большинстве случаев в виртуальных машинах Azure используется Windows Server 2016.

В настоящее время в Azure предоставляет Виртуальную машину с именем **Windows Server 2016 с контейнерами**. Можно использовать эту виртуальную Машину для испытания функции нового контейнера Windows Server с Windows Server Core или Nano Windows Server. Образы ОС контейнеров устанавливаются, и затем виртуальная машина будет готова для использования с помощью Docker.

### <a name="benefits"></a>Преимущества

Несмотря на то, что контейнеры Windows можно развернуть для локальных 2016 виртуальных машин Windows Server, при развертывании в Azure, вы получаете более простой способ начать с виртуальных машин контейнера готовые к использованию Windows Server. Можно также получить расположение общей сети, доступной для инженеров-испытателей и автоматического масштабируемости с помощью набора масштабирования виртуальной машины Azure.

### <a name="next-steps"></a>Следующие шаги

Это содержимое более подробное изучение на вики-сайте GitHub.

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a>Пошаговое руководство по 4 развертывания приложений на основе контейнеров Windows на Kubernetes в контейнер Azure службы

### <a name="technical-walkthrough-availability"></a>Технические руководства доступности

Полные технические пошагового руководства можно найти в репозитории GitHub eShopModernizing вики-сайте:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

### <a name="overview"></a>Обзор

Приложения, основанный на контейнеры Windows быстро нужно будет использовать платформ отсутствовали еще более перемещение из ВМ IaaS. Это требуется для легко обеспечить высокую масштабируемость лучше автоматического масштабирования и значительные улучшения в автоматического развертывания и управления версиями. Эти цели можно добиться с помощью orchestrator [Kubernetes](https://kubernetes.io/), которые доступны в [контейнера служб Azure](https://azure.microsoft.com/services/container-service/).

### <a name="goals"></a>Цели

В этом пошаговом руководстве предназначена для того, чтобы узнать о способах развертывания приложения на основе контейнера Windows на Kubernetes (также называемый *K8s*) в службе контейнера Azure. Развертывание с нуля Kubernetes состоит из двух этапов:

1.  Развертывание кластера Kubernetes контейнера службы Azure.

2.  Развертывание приложения и связанные ресурсы в кластере Kubernetes.

### <a name="scenarios"></a>Сценарии

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a>Сценарий а развернуть напрямую к кластеру Kubernetes из среды разработки

![Развертывание непосредственно на кластере Kubernetes из среды разработки](./media/image5-7.png)

> **Рис.** Развертывание непосредственно на кластере Kubernetes из среды разработки

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-team-services"></a>Сценарий б. развертывание кластера Kubernetes из элемента конфигурации/CD конвейеров в Team Services

![Развертывание кластера Kubernetes из элемента конфигурации/CD конвейеры в Team Services](./media/image5-8.png)

> **Рис.** Развертывание кластера Kubernetes из элемента конфигурации/CD конвейеры в Team Services

### <a name="benefits"></a>Преимущества

Есть множество преимуществ для развертывания на кластере в Kubernetes. Главное преимущество заключается в, чтобы получить готовый среды, в котором можно масштабировать приложение на основе количества экземпляров контейнера, необходимо использовать (inner масштабируемость в существующих узлов) и на основе количества узлов или виртуальных машин в кластере ( глобальные масштабируемость кластера).

Служба Azure контейнера оптимизирует популярных средств с открытым исходным кодом и технологии специально для Azure. Вы получаете открытое решение, который обеспечивает совместимость для вашего контейнеров и конфигурации приложения. Выберите размер, количество узлов, и средства orchestrator-контейнера службы обрабатывает все остальное.

С Kubernetes разработчики можно перейти от обдумывания физических и виртуальных машин к планирования это ориентированное на контейнер инфраструктура, которая обеспечивает следующие возможности, в частности:

- Приложений, основанных на несколько контейнеров

- Репликация экземпляров контейнера и горизонтальной автоматического масштабирования

- Именование и обнаружения (например, внутренние DNS)

- Балансировка нагрузки

- Последовательные обновления

- Распространение секретов

- Проверку работоспособности приложения

## <a name="next-steps"></a>Следующие шаги

Просмотр этого содержимого углубленные на вики-сайте GitHub: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-() Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a>Пошаговое руководство по 5 развертывания приложений на основе контейнеров Windows для Azure Service Fabric

### <a name="technical-walkthrough-availability"></a>Технические руководства доступности

Полные технические пошагового руководства можно найти в репозитории GitHub eShopModernizing вики-сайте:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

### <a name="overview"></a>Обзор

Приложение по контейнерам Windows быстро должен использовать платформ отсутствовали еще более перемещение из ВМ IaaS. Это требуется для легко обеспечить высокую масштабируемость лучше автоматического масштабирования и значительные улучшения в автоматического развертывания и управления версиями. Эти цели можно добиться с помощью orchestrator Azure Service Fabric доступны в облаке Azure, но также можно использовать в локальной среде, или даже в разных общедоступное облако.

### <a name="goals"></a>Цели

В этом пошаговом руководстве предназначена для того, чтобы узнать, как развертывание приложения на основе контейнера Windows в кластер Service Fabric в Azure. Развертывание Service Fabric с нуля состоит из двух этапов:

1.  Развертывание кластера Service Fabric в Azure (или в другой среде).

2.  Развертывание приложения и связанные ресурсы в кластере Service Fabric.

### <a name="scenarios"></a>Сценарии

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a>Сценарий а развернуть напрямую к кластеру Service Fabric из среды разработки

![Развертывание непосредственно к кластеру Service Fabric из среды разработки](./media/image5-9.png)

> **Рис. 5-9.** Развертывание непосредственно к кластеру Service Fabric из среды разработки

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-team-services"></a>Сценарий б. развертывание кластера Service Fabric из элемента конфигурации/CD конвейеров в Team Services

![Развертывание кластера Service Fabric из элемента конфигурации/CD конвейеры в Visual Studio Team Services](./media/image5-10.png)

> **Рис. 5-10.** Развертывание кластера Service Fabric из элемента конфигурации/CD конвейеры в Visual Studio Team Services

## <a name="benefits"></a>Преимущества

Преимущества развертывания на кластере в Service Fabric аналогичны преимущества использования Kubernetes. Различие, однако является Service Fabric более развитым рабочей среде для приложений Windows, по сравнению с Kubernetes, который находится на этапе бета-версии для контейнеров Windows в Kubernetes версия 1.9 (декабрь 2017 г.). Kubernetes представляет собой более развитым среду для Linux.

Является основным преимуществом использования Azure Service Fabric, чтобы получить готовый среды, в котором можно масштабировать приложение на основе количества экземпляров контейнера, необходимо использовать (inner масштабируемость в существующих узлов) и на основе количества узлы или виртуальные машины в кластере (глобальный масштабируемость кластера).

Azure Service Fabric обеспечивает совместимость для вашего контейнеров и конфигурации приложения. Может иметь Service Fabric кластера в Azure, и устанавливается локально в собственном центре обработки данных. Можно даже установке кластера Service Fabric в другом облаке, например [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).

В Service Fabric разработчики можно перейти от обдумывания физических и виртуальных машин к планирования это ориентированное на контейнер инфраструктура, которая обеспечивает следующие возможности, в частности:

- Приложений на основании несколько контейнеров.

- Репликация экземпляров контейнера и горизонтальной автоматическое масштабирование.

- Присвоение имени и обнаружения (например, внутренние DNS).

- Балансировка нагрузки.

- Развертывание обновлений.

- Распространение секретные данные.

- Проверяет работоспособность приложения.

Следующие возможности являются взаимоисключающими в Service Fabric (по сравнению с другими orchestrators):

- Возможности служб с отслеживанием состояния через модель надежные службы приложения.

- Шаблон субъекты, с помощью службы Reliable Actor модели приложения.

- Развертывание без операционной системы костей процессов, в дополнение к контейнерам Windows или Linux.

- Расширенные последовательного обновления и проверки работоспособности.

### <a name="next-steps"></a>Следующие шаги

Это содержимое более подробное изучение на вики-сайте GitHub.

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

>[!div class="step-by-step"]
[Назад](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Вперед](conclusions.md)
