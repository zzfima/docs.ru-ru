---
title: Пошаговые руководства и Технический обзор работы
description: Модернизация существующих приложений .NET с помощью облака Azure и контейнеров Windows | Пошаговые руководства и Технический обзор работы
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 41fbeb3abc201ef03cf0c237a069e7687c98dd18
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45594015"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a>Пошаговые руководства и Технический обзор работы

Чтобы ограничить размер этой электронной книге, Дополнительная техническая документация и полные руководства содержат были доступны в репозитории GitHub. Online ряд пошаговых руководств, описанный в этой главе рассматриваются пошаговой настройки нескольких сред, основанных на контейнеры Windows и развертывания в Azure.

Что каждого пошагового руководства о его цели и высокоуровневые концепции и предоставляет схему задачи, которые участвуют в следующих разделах. Вы можете получить пошаговые руководства, самостоятельно в *eShopModernizing* вики-сайт репозитория GitHub приложения в [ https://github.com/dotnet-architecture/eShopModernizing/wiki ](https://github.com/dotnet-architecture/eShopModernizing/wiki).

## <a name="technical-walkthrough-list"></a>Список техническим руководством

Следующие пошаговые руководства начало предоставить согласованный и всесторонний обзор Технические рекомендации для примеров приложений, которые можно перенести и shift с помощью контейнеров, а затем переместите с помощью нескольких вариантов развертывания в Azure.

Каждый из приведенных ниже пошаговых руководств использует новые примеры eShopLegacy и eShopModernizing приложений, которые можно найти на сайте GitHub [ https://github.com/dotnet-architecture/eShopModernizing ](https://github.com/dotnet-architecture/eShopModernizing).

- **Обзор eShop устаревших приложений (приложения для базовых показателей для модернизации)**

- **Контейнеризация существующего веб-приложений ASP.NET (веб-форм и MVC) с контейнерами Windows**

- **Контейнеризация существующего служб WCF (N-уровневого приложения) с контейнерами Windows**

- **Развертывание приложения на базе контейнеров Windows в виртуальных машинах Azure**

- **Развертывание приложений на базе контейнеров Windows в Kubernetes в службе контейнеров Azure**

- **Развертывание приложений на базе контейнеров Windows в Azure Service Fabric**


## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a>Пошаговое руководство 1: Обзор eShop работоспособности приложений прежних версий

### <a name="technical-walkthrough-availability"></a>Доступность техническим руководством

Полной технической руководство доступно в репозитории GitHub eShopModernizing вики-сайте:

[Пошаговые руководства вики-сайте eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing/wiki)


### <a name="overview"></a>Обзор

В этом пошаговом руководстве вы можете изучить начальная реализация из трех примеров приложений прежних версий. Первые два примера веб-приложений имеют монолитная архитектура и были созданы с помощью Классическая ASP.NET. Одно приложение на базе ASP.NET 4.x MVC; второе приложение зависит от веб-форм ASP.NET 4.x. Третий приложение является приложением уровня 3, состоящих из клиентского приложения WinForms и на стороне сервера [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) службы.

Все эти приложения можно найти по адресу [репозиторий GitHub eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).

### <a name="goals"></a>Цели

Основная цель этого пошагового руководства, достаточно ознакомиться с этими приложениями и с их кода и конфигурации. Можно настроить приложения, создавать и использовать фиктивные данные без использования базы данных SQL, для целей тестирования. Это необязательная конфигурация основана на внедрение зависимостей, несвязанно.

### <a name="scenario-1-aspnet-web-apps"></a>Сценарий 1: Веб-приложений ASP.NET

На рисунке ниже показан простой сценарий исходного устаревших веб-приложений ASP.NET.

> ![Простая архитектура сценария исходного устаревших веб-приложений ASP.NET](./media/image5-1.png)
>

С точки зрения бизнеса домена оба приложения предлагают одного каталога функции управления. Члены группы enterprise eShop использует приложение для просмотра и изменения каталога товаров. 

На следующем рисунке показано на снимках экрана первоначального приложения.

![Приложения ASP.NET MVC и веб-форм ASP.NET (существующими или устаревшими технологии)](./media/image5-2.png)

Зависимости в ASP.NET 4.x или более ранних версий (либо для MVC или веб-форм) означает, что эти приложения не будут работать на .NET Core, если код полностью переписан с помощью ASP.NET Core MVC. 

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a>Сценарий 2: Служба WCF и клиентское приложение WinForms (3-уровневое приложение)

На рисунке ниже показан простой сценарий исходного 3-уровневого приложения прежних версий.

> ![Сценарий простой архитектуры оригинальное прежних версий 3-уровневое приложение со службой WCF и клиентского приложения WinForms](./media/image5-1.5.png)
>

### <a name="benefits"></a>Преимущества

Преимущества в этом пошаговом руководстве просты: просто ознакомиться с кодом и начального приложения.

### <a name="next-steps"></a>Следующие шаги

Это содержимое более подробный обзор на вики-сайте GitHub:

  - [Обзор на базовых ASP.NET MVC и веб-форм «устаревшего» приложений](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
  - [Обзор базовая служба WCF и «устаревшего» приложение WinForms (3-уровневой)](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)


## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a>Пошаговое руководство 2: Контейнеризовать существующие приложения .NET с контейнерами Windows

### <a name="overview"></a>Обзор

Используйте контейнеры Windows для улучшения развертывания существующих приложений .NET, как на основе MVC, веб-форм или WCF, в рабочей среде, разработки, среды и тестирования.

### <a name="goals"></a>Цели

Цель данного руководства — Показать, несколько вариантов для запуска существующего приложения .NET Framework в контейнерах. Можно выполнить следующие действия: 

- Упаковывайте приложения в контейнеры с помощью [инструменты Visual Studio 2017 для Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 или более поздних версий).

- Упаковывайте приложения в контейнеры, вручную добавив [Dockerfile](https://docs.docker.com/engine/reference/builder/), а затем с помощью [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).

- Упаковывайте приложения в контейнеры с помощью [Img2Docker](https://github.com/docker/communitytools-image2docker-win) инструмента (инструмент с открытым кодом от Docker).

В этом пошаговом руководстве рассматриваются инструменты Visual Studio 2017 для Docker подхода, но эти два подхода довольно похожи отношении с помощью файлов Dockerfile.

### <a name="scenario-1-containerized-aspnet-web-apps"></a>Сценарий 1: Контейнерных ASP.NET веб-приложений

На следующем рисунке показан сценарий для контейнерных eShop устаревших веб-приложений, приложений.

> ![Схема упрощенной архитектуры контейнерных приложений ASP.NET в среде разработки](./media/image5-3.png)
>


### <a name="scenario-2-containerized-wcf-service"></a>Сценарий 2: Службы WCF контейнерных

На следующем рисунке показан сценарий для трехуровневого приложения с контейнерная служба WCF. 

> ![Упрощенная схема архитектуры контейнерные службы WCF в среде разработки](./media/image5-3.5.png)
>

### <a name="benefits"></a>Преимущества

Существуют преимущества запуска монолитного приложения в контейнере. Во-первых можно создать образ для приложения. С этого момента каждое развертывание будет производиться в одной среде. Каждый контейнер использует одну и ту же версию ОС, имеет ту же версию установить зависимости, использует ту же версию .NET framework и создается с тем же способом. По сути вы управляете зависимости приложения с помощью образа Docker. Зависимости перемещаются вместе с приложением при развертывании контейнеров.

Дополнительным преимуществом является то, что разработчики могут запустить приложение в согласованную среду, которая предоставляется в контейнерах Windows. Проблемы, которые отображаются только в определенных версиях может быть замечена немедленно, а не отображать в промежуточной или рабочей среде. Различия в средах разработки, используемых членами группы разработки так важны при запуске приложения в контейнерах.

Контейнерные приложения также имеют flatter кривую горизонтального масштабирования. Контейнерных приложений обеспечивают возможность иметь несколько экземпляров приложения и службы (с учетом контейнеры) на виртуальной Машине или физическом компьютере, по сравнению с развертываниями обычное приложение на каждом компьютере. Это преобразуется в более поздней версии плотность и требуется меньше ресурсов, особенно в том случае, при использовании оркестраторов, таком как Kubernetes или Service Fabric.

Создание контейнеров, в идеальной ситуации, не требует внесения изменений в код приложения (C\#). В большинстве случаев нужно просто Docker развертывания метаданных файлов (файлов Dockerfile и Docker Compose).

### <a name="next-steps"></a>Следующие шаги

Это содержимое более подробный обзор на вики-сайте GitHub:

  - [Как контейнеризовать веб-приложения .NET Framework с контейнерами Windows и Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
  - [Добавление поддержки Docker для службы WCF](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)



## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a>Пошаговое руководство 3: Развертывание приложения на базе контейнеров Windows в виртуальных машинах Azure

### <a name="technical-walkthrough-availability"></a>Доступность техническим руководством

Полной технической руководство доступно в репозитории GitHub eShopModernizing вики-сайте: [https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

### <a name="overview"></a>Обзор

Развертывание на узле Docker на Windows Server 2016 виртуальной машины (ВМ) в Azure позволяет быстро настроить разработки, тестирования и промежуточной сред. Она также предоставляет чаще всего для тест-инженеров или бизнес-пользователей, для проверки приложения. Виртуальные машины также могут быть допустимым приблизительные как услуги (IaaS) рабочих средах.

### <a name="goals"></a>Цели

Цель данного руководства — Показать, несколько альтернативных вариантов, которые возникают при развертывании контейнеров Windows на виртуальных машинах Azure, которые основаны на Windows Server 2016 или более поздней версии.

### <a name="scenarios"></a>Сценарии

В этом пошаговом руководстве рассматриваются несколько сценариев.

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a>Сценарий а. развертывание на виртуальных машинах Azure из dev ПК через подключение подсистемы Docker

![Развертывание виртуальной Машины Azure из dev ПК через подключение к подсистеме Docker](./media/image5-4.png)

> **Рис. 5-4.** Развертывание виртуальной Машины Azure из dev ПК через подключение к подсистеме Docker

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a>Сценарий б: развертывание на виртуальной Машине Azure через реестр Docker

![Развертывание на виртуальной Машине Azure через реестр Docker](./media/image5-5.png)

> **Рис. 5-5.** Развертывание на виртуальной Машине Azure через реестр Docker

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a>Сценарий C: развертывание на виртуальных машинах Azure из конвейеров CI/CD в службах Azure DevOps

![Развертывание виртуальной Машины Azure из конвейеров CI/CD в службах Azure DevOps](./media/image5-6.png)

> **Рис. 5-6**. Развертывание виртуальной Машины Azure из конвейеров CI/CD в службах Azure DevOps

### <a name="azure-vms-for-windows-containers"></a>Виртуальные машины Azure для контейнеров Windows

Под управлением Azure виртуальные машины для контейнеров Windows на основе Windows Server 2016, Windows 10 или более поздних версий, оба с модулем Docker, настроить. В большинстве случаев используется Windows Server 2016, на виртуальных машинах Azure.

Azure в настоящее время предоставляет виртуальная машина с именем **Windows Server 2016 с контейнерами**. Для испытания функции нового контейнера Windows Server с Windows Server Core или Windows Nano Server можно использовать эту виртуальную Машину. Образы ОС контейнеров устанавливаются, и затем виртуальная машина готова к использованию с помощью Docker.

### <a name="benefits"></a>Преимущества

Несмотря на то, что контейнеры Windows можно развернуть для локальных Windows Server 2016 виртуальных машин, при развертывании в Azure, вы получаете более простой способ начать работу с виртуальными машинами контейнер готовые к использованию Windows Server. Вы также получаете распространенных сетевом расположении, доступном для инженеров-испытателей и автоматического масштабирования через наборы масштабирования виртуальных машин Azure.

### <a name="next-steps"></a>Следующие шаги

Это содержимое более подробный обзор на вики-сайте GitHub:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a>Пошаговое руководство 4: Развертывание приложений на базе контейнеров Windows в экземпляры контейнеров Azure (ACI)

### <a name="technical-walkthrough-availability"></a>Доступность техническим руководством

Полной технической руководство доступно в репозитории GitHub eShopModernizing вики-сайте:

[Развертывание приложений в ACI (экземпляры контейнеров Azure)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

### <a name="overview"></a>Обзор

[Экземпляры контейнеров Azure (ACI)](https://docs.microsoft.com/en-us/azure/container-instances/) — это самый быстрый способ в среде разработки, тестирования и промежуточной контейнеры, где можно развернуть отдельные экземпляры контейнеров.

### <a name="goals"></a>Цели

В этом пошаговом руководстве показаны основные сценарии, при развертывании контейнеров Windows в экземпляры контейнеров Azure (ACI) и как можно развертывать приложения eShopModernizing в ACI.

### <a name="scenarios"></a>Сценарии

Может существовать варианты о развертывании приложений eShopModernizing в ACI, таких как развертывание одного или всех приложений (приложение MVC, веб-форм приложение или служба WCF). В следующем сценарии показано ниже вы увидите приложение ASP.NET MVC, а также контейнер SQL Server, из них развертываются как контейнеры в ACI (экземпляры контейнеров Azure).

![Развертывания в ACI из среды разработки](./media/image5-3.5.6.png)

### <a name="benefits"></a>Преимущества

Экземпляры контейнеров Azure позволяет легко создавать и управлять ими контейнеры Docker в Azure, без необходимости подготавливать виртуальные машины или службы более высокого уровня. Экземпляры контейнеров Azure можно напрямую развернуть контейнер Windows в Azure и предоставите к нему доступ в Интернете по полное доменное имя (FQDN) за считанные секунды (при условии, что у вас Готово образа контейнера Windows в реестр Docker, например центр Docker или контейнера Azure Реестр).

### <a name="considerations"></a>Особенности

Развертывание контейнеров Windows с помощью либо полной версии .NET Framework или ASP.NET или SQL Server в экземплярах контейнеров Azure (ACI) не является довольно быстро, как развертывание обычный узел Docker (например, Windows Server 2016 с контейнерами Windows), так как это должно быть образ Docker загружаются (вытащенные из реестра Docker) каждый раз, и размеры образа контейнера SQL (15.1 ГБ) и образ контейнера ASP.NET (13.9 ГБ) по значительно больших, однако гораздо дешевле, чем сохранение (без возможности восстановления через собственный узел docker Windows Server 2016 с виртуальной Машиной контейнеры Windows в Azure) тем более всего orchestrator как Kubernetes в Azure (AKS или ACS) или Azure Service Fabric, то есть, с другой стороны, отличный выбор для развертывания в рабочей среде.

Как основной заключение экземпляры контейнеров Azure является очень привлекательным вариантом для сценариев разработки и тестирования, а также для конвейеров CI/CD.

## <a name="next-steps"></a>Следующие шаги

Это содержимое более подробный обзор на вики-сайте GitHub: 

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)TBD)


## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a>Пошаговое руководство. 5: Развертывание приложений на базе контейнеров Windows в Kubernetes в службе контейнеров Azure

### <a name="technical-walkthrough-availability"></a>Доступность техническим руководством

Полной технической руководство доступно в репозитории GitHub eShopModernizing вики-сайте:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

### <a name="overview"></a>Обзор

Приложения, основанный на контейнеры Windows быстро потребуется использовать платформы, еще больше сейчас переход от виртуальных машин IaaS. Это требуется легко достичь высокого уровня масштабируемости и лучше автоматизировать масштабируемость и для значительное улучшение автоматического развертывания и управления версиями. Эти цели можно добиться с помощью оркестратора [Kubernetes](https://kubernetes.io/), которые доступны в [службы контейнеров Azure](https://azure.microsoft.com/services/container-service/).

### <a name="goals"></a>Цели

Цель этого пошагового руководства — Узнайте, как развернуть приложение на основе контейнера Windows в Kubernetes (также называется *K8s*) в службе контейнеров Azure. Развертывание в Kubernetes с нуля осуществляется в два этапа.

1.  Развертывание кластера Kubernetes в службе контейнеров Azure.

2.  Развертывание приложения и связанные ресурсы в кластере Kubernetes.

### <a name="scenarios"></a>Сценарии

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a>Сценарий а. развертывание непосредственно в кластер Kubernetes из среды разработки

![Развертывание непосредственно в кластере Kubernetes из среды разработки](./media/image5-7.png)

> **Рис. 5-7.** Развертывание непосредственно в кластере Kubernetes из среды разработки

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a>Сценарий б: развертывание в кластере Kubernetes из непрерывной Интеграции и Развертывания конвейеров в службах Azure DevOps

![Развертывание кластера Kubernetes из конвейеров CI/CD в службах Azure DevOps](./media/image5-8.png)

> **Рис. 5-8.** Развертывание кластера Kubernetes из конвейеров CI/CD в службах Azure DevOps

### <a name="benefits"></a>Преимущества

Существует множество преимуществ для развертывания в кластере Kubernetes. Самое большое преимущество заключается в получении производственную среду, в которой можно масштабировать приложения, основанного на количество экземпляров контейнера, вы хотите использовать (inner масштабируемости в существующие узлы) и на основе числа узлов или виртуальных машин в кластере ( глобальную масштабируемость кластера).

Служба контейнеров Azure оптимизирует популярных средств с открытым исходным кодом и технологий специально для Azure. Вы получаете открытое решение, которое обеспечивает переносимость, как для контейнеров, так и для конфигурации приложения. Выберите размер, количество узлов, и средства orchestrator-контейнера службы обрабатывает все остальное.

С помощью Kubernetes разработчики могут изменяться думать о физических и виртуальных машин, планирования ориентированную на контейнеры инфраструктуру, которая обеспечивает следующие возможности, среди прочего:

- Приложений, основанную на несколько контейнеров

- Репликация экземпляров контейнеров и автоматическое масштабирование по горизонтали

- Именование и обнаружения (например, внутренняя служба DNS)

- Балансировка нагрузки

- Последовательные обновления

- Распространение секретов

- Проверки работоспособности приложения

## <a name="next-steps"></a>Следующие шаги

Это содержимое более подробный обзор на вики-сайте GitHub: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a>Пошаговое руководство. 6: Развертывание приложений на базе контейнеров Windows в Azure Service Fabric

### <a name="technical-walkthrough-availability"></a>Доступность техническим руководством

Полной технической руководство доступно в репозитории GitHub eShopModernizing вики-сайте:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

### <a name="overview"></a>Обзор

Приложение быстро по контейнерам Windows должен использовать платформы, еще больше сейчас переход от виртуальных машин IaaS. Это требуется легко достичь высокого уровня масштабируемости и лучше автоматизировать масштабируемость и для значительное улучшение автоматического развертывания и управления версиями. С помощью оркестратора Azure Service Fabric, которая находится в облаке Azure, но также можно использовать в локальной, или даже в разных общедоступного облака, можно достичь этих целей.

### <a name="goals"></a>Цели

В этом пошаговом руководстве предназначена для того, чтобы узнать, как развернуть приложение на основе контейнера Windows в кластер Service Fabric в Azure. Развертывание в Service Fabric с нуля осуществляется в два этапа.

1.  Развертывание кластера Service Fabric в Azure (или другую среду).

2.  Развертывание приложения и связанные ресурсы в кластере Service Fabric.

### <a name="scenarios"></a>Сценарии

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a>Сценарий а. развертывание непосредственно в кластер Service Fabric из среды разработки

![Развертывание непосредственно в кластере Service Fabric из среды разработки](./media/image5-9.png)

> **Рис. 5-9.** Развертывание непосредственно в кластере Service Fabric из среды разработки

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-azure-devops-services"></a>Сценарий б: развертывание кластера Service Fabric из непрерывной Интеграции и Развертывания конвейеров в службах Azure DevOps

![Развертывание кластера Service Fabric из конвейеров CI/CD в службах Azure DevOps](./media/image5-10.png)

> **Рис. 5-10.** Развертывание кластера Service Fabric из конвейеров CI/CD в службах Azure DevOps

## <a name="benefits"></a>Преимущества

Преимущества развертывания в кластере Service Fabric аналогичны преимущества использования Kubernetes. Одно различие заключается в что Service Fabric — более развитым рабочей среде для приложений Windows, по сравнению с Kubernetes, который находится на этапе бета-версии для контейнеров Windows в Kubernetes версии 1.9 (декабрь 2017 г.). Kubernetes — это более развитым среда для Linux.

Является основным преимуществом использования Azure Service Fabric, вы получаете производственную среду, в которой можно масштабировать приложения, основанного на количество экземпляров контейнера, вы хотите использовать (inner масштабируемости в существующие узлы) и на основе числа узлы или виртуальные машины в кластере (глобальную масштабируемость кластера).

Azure Service Fabric обеспечивает переносимость как контейнеров, так и для конфигурации приложения. Может иметь Service Fabric в кластере в Azure, либо установить локально в собственном центре обработки данных. Кластер Service Fabric можно даже установить в другом облаке, например [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).

С Service Fabric разработчики могут изменяться думать о физических и виртуальных машин планирования ориентированную на контейнеры инфраструктуру, которая обеспечивает следующие возможности, среди прочего:

- Приложений, основанную на несколько контейнеров.

- Репликация экземпляров контейнеров и автоматическое масштабирование по горизонтали.

- Присвоение имени и обнаружения (например, внутренняя служба DNS).

- Балансировка нагрузки.

- Последовательного обновления.

- Распространение секреты.

- Проверки работоспособности приложения.

Следующие возможности являются взаимоисключающими в Service Fabric (по сравнению с других оркестраторов):

- Возможности служб с отслеживанием состояния, через модель приложения Reliable Services.

- Шаблон субъектов, с помощью модели приложения Reliable Actors.

- Развертывание базовую процессов, а также контейнеры Windows или Linux.

- Расширенные последовательные обновления и проверки работоспособности.

### <a name="next-steps"></a>Следующие шаги

Это содержимое более подробный обзор на вики-сайте GitHub:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

>[!div class="step-by-step"]
[Назад](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Вперед](conclusions.md)
