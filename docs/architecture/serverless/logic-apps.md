---
title: Azure Logic Apps — бессерверные приложения
description: С помощью службы Azure Logic Apps можно создавать автоматические масштабируемые рабочие процессы для интеграции приложений и данных в различные облачные службы и локальные системы.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7ece3d30209713d42ee44ef9c1be1cf0fe82464a
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2019
ms.locfileid: "69577457"
---
# <a name="azure-logic-apps"></a><span data-ttu-id="5b93a-103">Azure Logic Apps</span><span class="sxs-lookup"><span data-stu-id="5b93a-103">Azure Logic Apps</span></span>

<span data-ttu-id="5b93a-104">[Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps) предоставляет бессерверный модуль, позволяющий создавать автоматизированные рабочие процессы для интеграции приложений и данных в различные облачные службы и локальные системы.</span><span class="sxs-lookup"><span data-stu-id="5b93a-104">[Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps) provides a serverless engine to build automated workflows to integrate apps and data between cloud services and on-premises systems.</span></span> <span data-ttu-id="5b93a-105">Рабочие процессы можно создать с помощью визуального конструктора.</span><span class="sxs-lookup"><span data-stu-id="5b93a-105">You build workflows using a visual designer.</span></span> <span data-ttu-id="5b93a-106">Вы можете активировать рабочие процессы на основе событий или таймеров, а также использовать соединители для интеграции приложений и обеспечения связи "бизнес — бизнес" (B2B).</span><span class="sxs-lookup"><span data-stu-id="5b93a-106">You can trigger workflows based on events or timers and leverage connectors to integration applications and facilitate business-to-business (B2B) communication.</span></span> <span data-ttu-id="5b93a-107">Служба Logic Apps легко интегрируется с Функциями Azure.</span><span class="sxs-lookup"><span data-stu-id="5b93a-107">Logic Apps integrates seamlessly with Azure Functions.</span></span>

![Логотип Azure Logic Apps](./media/logic-apps-logo.png)

<span data-ttu-id="5b93a-109">Logic Apps может не только подключать облачные службы (например, функции) к облачным ресурсам (например, к очередям и базам данных).</span><span class="sxs-lookup"><span data-stu-id="5b93a-109">Logic Apps can do more than just connect your cloud services (like functions) with cloud resources (like queues and databases).</span></span> <span data-ttu-id="5b93a-110">Вы также можете управлять локальными рабочими процессами с помощью локального шлюза.</span><span class="sxs-lookup"><span data-stu-id="5b93a-110">You can also orchestrate on-premises workflows with the on-premises gateway.</span></span> <span data-ttu-id="5b93a-111">Например, Logic Apps можно использовать для активации локальной хранимой процедуры SQL в ответ на облачное событие или условную логику в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="5b93a-111">For example, you can use the Logic App to trigger an on-premises SQL stored procedure in response to a cloud-based event or conditional logic in your workflow.</span></span> <span data-ttu-id="5b93a-112">[Дополнительные сведения о подключении к локальным источникам данных с помощью локального шлюза данных](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway).</span><span class="sxs-lookup"><span data-stu-id="5b93a-112">Learn more about [Connecting to on-premises data sources with Azure On-premises Data Gateway](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway).</span></span>

![Архитектура Logic Apps](./media/logic-apps-architecture.png)

<span data-ttu-id="5b93a-114">Как и в случае с Функциями Azure, вы запускаете рабочие процессы Logic Apps с помощью триггера.</span><span class="sxs-lookup"><span data-stu-id="5b93a-114">Like Azure Functions, you kick off Logic App workflows with a trigger.</span></span> <span data-ttu-id="5b93a-115">Вы можете выбрать один из множества триггеров.</span><span class="sxs-lookup"><span data-stu-id="5b93a-115">There are many triggers for you to choose from.</span></span> <span data-ttu-id="5b93a-116">На приведенном ниже снимке экрана показаны лишь несколько популярных триггеров из сотен доступных.</span><span class="sxs-lookup"><span data-stu-id="5b93a-116">The following capture shows just a few of the more popular ones out of hundreds that are available.</span></span>

![Триггеры Logic Apps](./media/logic-app-triggers.png)

<span data-ttu-id="5b93a-118">После запуска приложения можно использовать визуальный конструктор для шагов, циклов, условий и действий.</span><span class="sxs-lookup"><span data-stu-id="5b93a-118">Once the app is triggered, you can use the visual designer to build out steps, loops, conditions, and actions.</span></span> <span data-ttu-id="5b93a-119">Все данные, полученные на предыдущем шаге, доступны для использования на последующих шагах.</span><span class="sxs-lookup"><span data-stu-id="5b93a-119">Any data ingested in a previous step is available for you to use in subsequent steps.</span></span> <span data-ttu-id="5b93a-120">Следующий рабочий процесс загружает URL-адреса из базы данных CosmosDB.</span><span class="sxs-lookup"><span data-stu-id="5b93a-120">The following workflow loads URLs from a CosmosDB database.</span></span> <span data-ttu-id="5b93a-121">Он находит URL-адреса с узлом `t.co`, а затем ищет их в Twitter.</span><span class="sxs-lookup"><span data-stu-id="5b93a-121">It finds the ones with a host of `t.co` then searches for them on Twitter.</span></span> <span data-ttu-id="5b93a-122">Если он находит соответствующие твиты, он обновляет документы, добавляя связанные твиты путем вызова функции.</span><span class="sxs-lookup"><span data-stu-id="5b93a-122">If it finds corresponding tweets, it updates the documents with the related tweets by calling a function.</span></span>

![Рабочий процесс Logic Apps](./media/logic-app-workflow.png)

<span data-ttu-id="5b93a-124">На панели мониторинга Logic Apps отображается журнал выполнения рабочих процессов и результатов их выполнения (успешное или нет).</span><span class="sxs-lookup"><span data-stu-id="5b93a-124">The Logic Apps dashboard shows the history of running your workflows and whether each run completed successfully or not.</span></span> <span data-ttu-id="5b93a-125">Можно перейти к любому заданному выполнению и проверить данные, используемые на каждом шаге, для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="5b93a-125">You can navigate into any given run and inspect the data used by each step for troubleshooting.</span></span> <span data-ttu-id="5b93a-126">Logic Apps также предоставляет существующие шаблоны, которые можно изменять и которые хорошо подходят для сложных рабочих процессов предприятия.</span><span class="sxs-lookup"><span data-stu-id="5b93a-126">Logic Apps also provides existing templates you can edit and are well suited for complex enterprise workflows.</span></span>

<span data-ttu-id="5b93a-127">Дополнительные сведения см. в разделе [Документация по Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps).</span><span class="sxs-lookup"><span data-stu-id="5b93a-127">To learn more, see [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5b93a-128">[Назад](application-insights.md)
>[Вперед](event-grid.md)</span><span class="sxs-lookup"><span data-stu-id="5b93a-128">[Previous](application-insights.md)
[Next](event-grid.md)</span></span>
