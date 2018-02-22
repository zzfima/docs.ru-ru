---
title: "Общие рекомендации"
description: "Архитектура микрослужб .NET для контейнерных приложений .NET | Общие рекомендации"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: fa58d1d81b2d1523baf123d4963db2ca00fee15d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="general-guidance"></a>Общие рекомендации

В этом разделе представлена сводка относительно выбора .NET Core или .NET Framework. Дополнительные сведения об этих вариантах представлены в последующих разделах.

Следует использовать .NET Core с контейнерами Windows или Linux для контейнерного серверного приложения Docker в следующих случаях.

-   для создания кроссплатформенных решений; Например, вы хотите использовать контейнеры и Windows, и Linux.

-   Архитектура приложения основана на микрослужбах.

-   Вам нужно быстро запустить контейнеры, и вы хотите использовать небольшой объем памяти на каждый контейнер, чтобы получить более высокую плотность или больше контейнеров на единицу оборудования для снижения затрат.

Вкратце, при создании новых контейнерных приложений .NET следует рассматривать .NET Core как вариант по умолчанию. Он имеет множество преимуществ и лучше соответствует концепции и стилю работы с контейнерами.

Дополнительное преимущество использования .NET Core заключается в том, что можно параллельно запускать версии .NET для приложений на одной и той же машине. Данное преимущество более важно для серверов или виртуальных машин, которые не используют контейнеры, так как контейнеры изолируют версии .NET, нужные приложению. (При условии, что они совместимы с базовой ОС.)

Следует использовать .NET Framework с контейнерами Windows или Linux для контейнерного серверного приложения Docker в следующих случаях.

-   В настоящее время приложение использует .NET Framework и имеет строгие зависимости от Windows.

-   Необходимо использовать API Windows, которые не поддерживаются .NET Core.

-   Требуются сторонние библиотеки .NET или пакеты NuGet, недоступные для .NET Core.

Использование .NET Framework в Docker может улучшить качество развертывания, сводя к минимуму проблемы развертывания. Данный сценарий [*"подъема и смены"*](https://aka.ms/liftandshiftwithcontainersebook) важен для контейнеризации приложений прежних версий, которые изначально были разработаны с использованием классической платформы .NET Framework, например ASP.NET WebForms, веб-приложений MVC или служб WCF (Windows Communication Foundation).

### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Электронная книга: Modernize existing .NET Framework applications with Azure and Windows Containers**
    [*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)

-   **Примеры приложений: Modernization of legacy ASP.NET web apps by using Windows Containers**
    [*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)


>[!div class="step-by-step"]
[Назад] (index.md) [Далее] (net-core-container-scenarios.md)
