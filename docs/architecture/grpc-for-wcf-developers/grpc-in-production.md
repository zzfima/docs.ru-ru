---
title: gRPC в рабочей среде — gRPC для разработчиков WCF
description: Запуск ASP.NET Core приложений gRPC в рабочих средах
ms.date: 09/02/2019
ms.openlocfilehash: f30252b9937353b8670f509a245694f89512ba30
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967804"
---
# <a name="grpc-in-production"></a><span data-ttu-id="723d2-103">gRPC в рабочей среде</span><span class="sxs-lookup"><span data-stu-id="723d2-103">gRPC in production</span></span>

<span data-ttu-id="723d2-104">ASP.NET Core 3,0 приложений, включая службы gRPC Services, могут выполняться в Windows, Linux и в контейнерах с помощью современных платформ, таких как DOCKER и Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="723d2-104">ASP.NET Core 3.0 applications, including gRPC services, can be run on Windows, Linux, and in containers using modern platforms like Docker and Kubernetes.</span></span> <span data-ttu-id="723d2-105">В этой главе рассматриваются различные варианты запуска служб gRPC в рабочей среде и рассмотрены параметры мониторинга и ведения журнала, позволяющие обеспечить оптимальную работу систем.</span><span class="sxs-lookup"><span data-stu-id="723d2-105">This chapter will explore the various options for running your gRPC services in production, and look at monitoring and logging options to ensure the optimal operation of systems.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="723d2-106">[Назад](encryption.md)
>[Вперед](self-hosted.md)</span><span class="sxs-lookup"><span data-stu-id="723d2-106">[Previous](encryption.md)
[Next](self-hosted.md)</span></span>
