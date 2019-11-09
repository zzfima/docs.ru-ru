---
title: Обзор gRPC-gRPC для разработчиков WCF
description: Узнайте о наборе принципов, которые являются идентификаторами разработки gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 6980b473a6f9852a4e4f396355e98e2d3300cabe
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841591"
---
# <a name="grpc-overview"></a><span data-ttu-id="46132-103">Обзор gRPC</span><span class="sxs-lookup"><span data-stu-id="46132-103">gRPC overview</span></span>

<span data-ttu-id="46132-104">Изучив женесис и WCF, и gRPC в последней главе, в этой главе рассматриваются некоторые основные функции gRPC и их сравнение с WCF.</span><span class="sxs-lookup"><span data-stu-id="46132-104">After looking at the genesis of both WCF and gRPC in the last chapter, this chapter will consider some of the key features of gRPC and how they compare to WCF.</span></span>

<span data-ttu-id="46132-105">ASP.NET Core 3,0 — это первый выпуск ASP.NET, который изначально поддерживает gRPC в качестве участника первого класса, с Microsoft Teams, участвующим в официальной реализации .NET gRPC.</span><span class="sxs-lookup"><span data-stu-id="46132-105">ASP.NET Core 3.0 is the first release of ASP.NET that natively supports gRPC as a first-class citizen, with Microsoft teams contributing to the official .NET implementation of gRPC.</span></span> <span data-ttu-id="46132-106">Рекомендуется как лучший подход к созданию распределенных приложений с помощью .NET, которые могут взаимодействовать со всеми остальными основными языками программирования и платформами.</span><span class="sxs-lookup"><span data-stu-id="46132-106">It's recommended as the best approach for building distributed applications with .NET that can interoperate with all other major programming languages and frameworks.</span></span>

## <a name="key-principles"></a><span data-ttu-id="46132-107">Основные принципы</span><span class="sxs-lookup"><span data-stu-id="46132-107">Key principles</span></span>

<span data-ttu-id="46132-108">Как обсуждалось в главе 1, Google хотела использовать введение HTTP/2 для замены продолжим, его внутренней инфраструктуры RPC общего назначения.</span><span class="sxs-lookup"><span data-stu-id="46132-108">As discussed in chapter 1, Google wanted to use the introduction of HTTP/2 to replace Stubby, its internal, general purpose RPC infrastructure.</span></span> <span data-ttu-id="46132-109">gRPC на основе продолжим, теперь может воспользоваться преимуществами стандартизации и расширить ее применимость к мобильным вычислениям, облаку и "Интернет вещей".</span><span class="sxs-lookup"><span data-stu-id="46132-109">gRPC, based on Stubby, now could take advantage of standardization and would extend its applicability to mobile computing, the cloud, and the Internet of Things.</span></span>

<span data-ttu-id="46132-110">Для этого [облачный машинный фундамент (кнкф)](https://www.cncf.io/) установил набор принципов, управляющих gRPC.</span><span class="sxs-lookup"><span data-stu-id="46132-110">To achieve this, the [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) established a set of principles that would govern gRPC.</span></span> <span data-ttu-id="46132-111">В следующем списке перечислены наиболее важные из них, которые в основном связаны с максимальным уровнем доступности и удобства использования.</span><span class="sxs-lookup"><span data-stu-id="46132-111">The following list shows the most relevant ones, which are mainly concerned with maximizing accessibility and usability:</span></span>

- <span data-ttu-id="46132-112">**Free и Open** — все артефакты должны быть открытыми исходными данными с лицензией, которые не ограничивают разработчиков внедрением gRPC.</span><span class="sxs-lookup"><span data-stu-id="46132-112">**Free and open** – all artifacts should be open source with licensing that doesn't constrain developers from adopting gRPC.</span></span>
- <span data-ttu-id="46132-113">**Покрытие и простота** — gRPC должны быть доступны для каждой популярной платформы и достаточно проста для создания на любой платформе.</span><span class="sxs-lookup"><span data-stu-id="46132-113">**Coverage and simplicity** – gRPC should be available across every popular platform and simple enough to build on any platform.</span></span>
- <span data-ttu-id="46132-114">**Взаимодействие и доступ** . в любой сети можно использовать gRPC, независимо от пропускной способности или задержки, используя широко доступные сетевые стандарты.</span><span class="sxs-lookup"><span data-stu-id="46132-114">**Interoperability and reach** – it should be possible to use gRPC on any network, regardless of bandwidth or latency, using widely available network standards.</span></span>
- <span data-ttu-id="46132-115">**Общая цель и исполнитель** — платформа должна быть использована в качестве широкого спектра вариантов использования, если это возможно без ущерба для производительности.</span><span class="sxs-lookup"><span data-stu-id="46132-115">**General purpose and performant** – the framework should be usable by as broad a range of use-cases as possible without compromising performance.</span></span>
- <span data-ttu-id="46132-116">**Потоковая передача** — протокол должен обеспечивать семантику потоковой передачи для больших наборов данных или асинхронного обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="46132-116">**Streaming** – the protocol should provide streaming semantics for large data-sets or asynchronous messaging.</span></span>
- <span data-ttu-id="46132-117">**Обмен метаданными** . протокол позволяет обрабатывать небизнес-данные, например маркеры проверки подлинности, отдельно от реальных бизнес-данных.</span><span class="sxs-lookup"><span data-stu-id="46132-117">**Metadata exchange** – the protocol allow non-business data, such as authentication tokens, to be handled separately from actual business data.</span></span>
- <span data-ttu-id="46132-118">**Стандартизированные коды состояния** — вариативность кодов ошибок должна быть снижена, чтобы решения по обработке ошибок были более четкими и, где требуется дополнительная обработка ошибок, для управления этим в обмене метаданными необходимо предоставить механизм.</span><span class="sxs-lookup"><span data-stu-id="46132-118">**Standardized status codes** – the variability of error codes should be reduced to make error handling decisions clearer and, where additional richer error handling is required, a mechanism should be provided for managing this within the metadata exchange.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="46132-119">[Назад](introduction.md)
>[Вперед](approach.md)</span><span class="sxs-lookup"><span data-stu-id="46132-119">[Previous](introduction.md)
[Next](approach.md)</span></span>
