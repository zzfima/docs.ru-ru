---
title: Обзор gRPC-gRPC для разработчиков WCF
description: Узнайте о наборе принципов, которые являются идентификаторами разработки gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: a0811adadc617097d86edc5f845c42a7e90f560f
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542927"
---
# <a name="grpc-overview"></a><span data-ttu-id="6115b-103">Обзор gRPC</span><span class="sxs-lookup"><span data-stu-id="6115b-103">gRPC overview</span></span>

<span data-ttu-id="6115b-104">После рассмотрения женесис обеих Windows Communication Foundation (WCF) и gRPC в последней главе эта глава рассматривает некоторые ключевые функции gRPC и их сравнение с WCF.</span><span class="sxs-lookup"><span data-stu-id="6115b-104">After looking at the genesis of both Windows Communication Foundation (WCF) and gRPC in the last chapter, this chapter considers some of the key features of gRPC and how they compare to WCF.</span></span>

<span data-ttu-id="6115b-105">ASP.NET Core 3,0 — это первый выпуск ASP.NET, который изначально поддерживает gRPC в качестве участника первого класса, с Microsoft Teams, участвующим в официальной реализации .NET gRPC.</span><span class="sxs-lookup"><span data-stu-id="6115b-105">ASP.NET Core 3.0 is the first release of ASP.NET that natively supports gRPC as a first-class citizen, with Microsoft teams contributing to the official .NET implementation of gRPC.</span></span> <span data-ttu-id="6115b-106">Рекомендуется создавать распределенные приложения с помощью .NET, которые могут взаимодействовать со всеми остальными основными языками программирования и платформами.</span><span class="sxs-lookup"><span data-stu-id="6115b-106">It's recommended for building distributed applications with .NET that can interoperate with all other major programming languages and frameworks.</span></span>

## <a name="key-principles"></a><span data-ttu-id="6115b-107">Ключевые принципы</span><span class="sxs-lookup"><span data-stu-id="6115b-107">Key principles</span></span>

<span data-ttu-id="6115b-108">Как обсуждалось в главе 1, Google хотела использовать введение HTTP/2 для замены продолжим, его внутренней инфраструктуры RPC общего назначения.</span><span class="sxs-lookup"><span data-stu-id="6115b-108">As discussed in chapter 1, Google wanted to use the introduction of HTTP/2 to replace Stubby, its internal, general purpose RPC infrastructure.</span></span> <span data-ttu-id="6115b-109">gRPC на основе продолжим, теперь может воспользоваться преимуществами стандартизации и расширить ее применимость к мобильным вычислениям, облаку и "Интернет вещей".</span><span class="sxs-lookup"><span data-stu-id="6115b-109">gRPC, based on Stubby, now can take advantage of standardization and would extend its applicability to mobile computing, the cloud, and the Internet of Things.</span></span>

<span data-ttu-id="6115b-110">Для этого [облачный машинный фундамент (кнкф)](https://www.cncf.io/) установил набор принципов, управляющих gRPC.</span><span class="sxs-lookup"><span data-stu-id="6115b-110">To achieve this, the [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) established a set of principles that would govern gRPC.</span></span> <span data-ttu-id="6115b-111">В следующем списке перечислены наиболее важные из них, которые в основном связаны с максимальным уровнем доступности и удобства использования.</span><span class="sxs-lookup"><span data-stu-id="6115b-111">The following list shows the most relevant ones, which are mainly concerned with maximizing accessibility and usability:</span></span>

- <span data-ttu-id="6115b-112">**Free и Open** — все артефакты должны быть открытыми исходными данными с лицензией, которая не ограничивает разработчиков внедрением gRPC.</span><span class="sxs-lookup"><span data-stu-id="6115b-112">**Free and open** – All artifacts should be open source, with licensing that doesn't constrain developers from adopting gRPC.</span></span>
- <span data-ttu-id="6115b-113">**Покрытие и простота** — gRPC должны быть доступны для каждой популярной платформы и достаточно просто для создания на любой платформе.</span><span class="sxs-lookup"><span data-stu-id="6115b-113">**Coverage and simplicity** – gRPC should be available across every popular platform, and simple enough to build on any platform.</span></span>
- <span data-ttu-id="6115b-114">**Взаимодействие и доступ** . gRPC можно использовать в любой сети, независимо от пропускной способности или задержки, используя широко доступные сетевые стандарты.</span><span class="sxs-lookup"><span data-stu-id="6115b-114">**Interoperability and reach** – It should be possible to use gRPC on any network, regardless of bandwidth or latency, by using widely available network standards.</span></span>
- <span data-ttu-id="6115b-115">**Общая цель и исполнитель** — платформа должна использоваться в качестве широкого спектра вариантов использования, если это возможно, без ущерба для производительности.</span><span class="sxs-lookup"><span data-stu-id="6115b-115">**General purpose and performant** – The framework should be usable by as broad a range of use-cases as possible, without compromising performance.</span></span>
- <span data-ttu-id="6115b-116">**Потоковая передача** — протокол должен обеспечивать семантику потоковой передачи для больших наборов данных или асинхронного обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="6115b-116">**Streaming** – The protocol should provide streaming semantics for large datasets or asynchronous messaging.</span></span>
- <span data-ttu-id="6115b-117">**Обмен метаданными** — протокол позволяет обрабатывать небизнес-данные, такие как маркеры проверки подлинности, отдельно от реальных бизнес-данных.</span><span class="sxs-lookup"><span data-stu-id="6115b-117">**Metadata exchange** – The protocol allows non-business data, such as authentication tokens, to be handled separately from actual business data.</span></span>
- <span data-ttu-id="6115b-118">**Стандартизированные коды состояния** — вариативность кодов ошибок должна быть сокращена, чтобы решения по обработке ошибок были ясными.</span><span class="sxs-lookup"><span data-stu-id="6115b-118">**Standardized status codes** – The variability of error codes should be reduced to make error handling decisions clearer.</span></span> <span data-ttu-id="6115b-119">Если требуется дополнительная обработка ошибок, необходимо предоставить механизм для управления этим в обмене метаданными.</span><span class="sxs-lookup"><span data-stu-id="6115b-119">Where additional, richer error handling is required, a mechanism should be provided for managing this within the metadata exchange.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6115b-120">[Назад](introduction.md)
>[Вперед](approach.md)</span><span class="sxs-lookup"><span data-stu-id="6115b-120">[Previous](introduction.md)
[Next](approach.md)</span></span>
