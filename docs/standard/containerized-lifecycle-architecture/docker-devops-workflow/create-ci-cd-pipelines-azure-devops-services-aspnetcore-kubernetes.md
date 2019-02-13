---
title: Действия в рабочем процессе внешнего цикла DevOps для приложения Docker
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 7a98c34bfdbbdc9b34a04c891ca031f454ac4396
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221521"
---
# <a name="creating-cicd-pipelines-in-azure-devops-services-for-a-net-core-20-application-on-containers-and-deploying-to-a-kubernetes-cluster"></a>Создание конвейеров CI/CD в службах Azure DevOps для приложения .NET Core 2.0 для контейнеров и развертывание в кластер Kubernetes

На рисунке 5-12 показано сценарии DevOps end-to-end, охватывающий управления кода, компиляции кода, сборки образов Docker, отправьте образы Docker в реестр Docker и, наконец, развертывание в кластер Kubernetes в Azure.

![Рабочий процесс: Запускает на компьютере разработки. Отправка в репозиторий начинается задача сборки/непрерывной Интеграции, с помощью пользовательского образа, который отправляется в реестр Docker, а затем используется задачей компакт-диска или развернуть, и, наконец, отправка в AKS.](media/docker-workflow-ci-cd-aks.png)

**Рис. 5-12**. Сценарии Непрерывной интеграции и создание образов Docker, а также развертывание в кластер Kubernetes в Azure

Это важно обратить внимание, что два конвейера, сборки/непрерывной Интеграции и выпуска и непрерывной Доставки, подключены через реестр Docker (Docker Hub или реестра контейнеров Azure). Реестр Docker является одним из основных различий по сравнению с традиционной процесс Непрерывной интеграции и без Docker.

Как показано на рисунке 5-13, первый этап заключается в конвейер сборки и CI. В службах DevOps Azure можно создать конвейеры Непрерывной сборки, на которые будет скомпилировать код, создание образов Docker и отправки их в реестр Docker, например Docker Hub или реестра контейнеров Azure.

![](media/build-ci-pipeline-azure-devops-push-to-docker-registry.png)

**Рис. 5-13**. Конвейер сборки/непрерывной Интеграции в Azure DevOps, создание образов Docker и отправке образов в реестр Docker

Второй этап заключается в создании конвейера развертывания или выпуска. В службах Azure DevOps можно легко создать конвейер развертывания, предназначенные для кластера Kubernetes с помощью задач Kubernetes для служб Azure DevOps, как показано на рисунке 5-14.

![Развертывание MVC](media/release-cd-pipeline-azure-devops-deploy-to-kubernetes.png)

**Рис. 5-14**. Конвейер выпуска и непрерывного Развертывания в развертывание служб Azure DevOps в кластере Kubernetes

> [! Пошаговое руководство] развертывание eShopModernized Kubernetes:
>
> Подробное пошаговое руководство конвейеров Azure DevOps Непрерывной интеграции и развертывания в Kubernetes, см. запись блога: \
>[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

>[!div class="step-by-step"]
>[Назад](docker-application-outer-loop-devops-workflow.md)
>[Вперед](../run-manage-monitor-docker-environments/index.md)
