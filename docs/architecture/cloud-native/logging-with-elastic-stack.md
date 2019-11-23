---
title: Ведение журналов с использованием эластичного стека
description: Ведение журналов с помощью эластичного стека, Logstash и Kibana
ms.date: 09/23/2019
ms.openlocfilehash: 989834925bc08541bf484e1a4567a56ac324872f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841741"
---
# <a name="logging-with-elastic-stack"></a><span data-ttu-id="e5383-103">Ведение журналов с использованием эластичного стека</span><span class="sxs-lookup"><span data-stu-id="e5383-103">Logging with Elastic Stack</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="e5383-104">Существует множество хороших средств централизованного ведения журналов, которые изменяются по затратам от бесплатных средств с открытым исходным кодом до более дорогостоящих вариантов.</span><span class="sxs-lookup"><span data-stu-id="e5383-104">There are many good centralized logging tools and they vary in cost from being free, open-source tools, to more expensive options.</span></span> <span data-ttu-id="e5383-105">Во многих случаях бесплатные инструменты должны быть как или более надежными, чем оплаченные предложения.</span><span class="sxs-lookup"><span data-stu-id="e5383-105">In many cases, the free tools are as good as or better than the paid offerings.</span></span> <span data-ttu-id="e5383-106">Одним из таких инструментов является сочетание трех компонентов с открытым исходным кодом: Эластичный Поиск, Logstash и Kibana.</span><span class="sxs-lookup"><span data-stu-id="e5383-106">One such tool is a combination of three open-source components: Elastic search, Logstash, and Kibana.</span></span>
<span data-ttu-id="e5383-107">Вместе эти средства называются стеком эластичных баз данных или ELK.</span><span class="sxs-lookup"><span data-stu-id="e5383-107">Collectively these tools are known as the Elastic Stack or ELK stack.</span></span>

## <a name="what-are-the-advantages-of-elastic-stack"></a><span data-ttu-id="e5383-108">Каковы преимущества эластичного стека?</span><span class="sxs-lookup"><span data-stu-id="e5383-108">What are the advantages of Elastic Stack?</span></span>

<span data-ttu-id="e5383-109">Эластичный стек обеспечивает централизованное ведение журналов с экономичным, масштабируемым и облачным способом.</span><span class="sxs-lookup"><span data-stu-id="e5383-109">Elastic Stack provides centralized logging in a low-cost, scalable, cloud-friendly manner.</span></span> <span data-ttu-id="e5383-110">Его пользовательский интерфейс упрощает анализ данных, позволяя тратить время на получение ценных сведений из данных вместо борьбы с интерфейсом неуклюжим.</span><span class="sxs-lookup"><span data-stu-id="e5383-110">Its user interface streamlines data analysis so you can spend your time gleaning insights from your data instead of fighting with a clunky interface.</span></span> <span data-ttu-id="e5383-111">Он поддерживает широкий спектр входных данных, так как распределенное приложение охватывает больше и разных типов служб, поэтому вы можете продолжать работать с данными журналов и метрик в системе.</span><span class="sxs-lookup"><span data-stu-id="e5383-111">It supports a wide variety of inputs so as your distributed application spans more and different kinds of services, you can expect to continue to be able to feed log and metric data into the system.</span></span> <span data-ttu-id="e5383-112">Эластичный стек также поддерживает быстрый поиск даже в больших наборах данных, что делает возможным даже для больших приложений запись подробных данных в журнал и по-прежнему иметь возможность видеть их в удобном для себя виде.</span><span class="sxs-lookup"><span data-stu-id="e5383-112">The Elastic Stack also supports fast searches even across large data sets, making it possible even for large applications to log detailed data and still be able to have visibility into it in a performant fashion.</span></span>

## <a name="logstash"></a><span data-ttu-id="e5383-113">Logstash</span><span class="sxs-lookup"><span data-stu-id="e5383-113">Logstash</span></span>

<span data-ttu-id="e5383-114">Первый компонент — [Logstash](https://www.elastic.co/products/logstash).</span><span class="sxs-lookup"><span data-stu-id="e5383-114">The first component is [Logstash](https://www.elastic.co/products/logstash).</span></span> <span data-ttu-id="e5383-115">Это средство используется для сбора данных журнала из большого спектра различных источников.</span><span class="sxs-lookup"><span data-stu-id="e5383-115">This tool is used to gather log information from a large variety of different sources.</span></span> <span data-ttu-id="e5383-116">Например, Logstash может считывать журналы с диска, а также отправлять сообщения из библиотек ведения журналов, например [Serilog](https://serilog.net/).</span><span class="sxs-lookup"><span data-stu-id="e5383-116">For instance, Logstash can read logs from disk and also receive messages from logging libraries like [Serilog](https://serilog.net/).</span></span> <span data-ttu-id="e5383-117">Logstash может выполнять некоторую базовую фильтрацию и расширение журналов по мере их поступления.</span><span class="sxs-lookup"><span data-stu-id="e5383-117">Logstash can do some basic filtering and expansion on the logs as they arrive.</span></span> <span data-ttu-id="e5383-118">Например, если журналы содержат IP-адреса, Logstash можно настроить для выполнения географического поиска и получения страны или даже города происхождения сообщения.</span><span class="sxs-lookup"><span data-stu-id="e5383-118">For instance, if your logs contain IP addresses then Logstash may be configured to do a geographical lookup and obtain a country or even city of origin for that message.</span></span>

<span data-ttu-id="e5383-119">Serilog — это библиотека ведения журналов для языков .NET, позволяющая выполнять параметризованное ведение журнала.</span><span class="sxs-lookup"><span data-stu-id="e5383-119">Serilog is a logging library for .NET languages, which allows for parameterized logging.</span></span> <span data-ttu-id="e5383-120">Вместо создания текстового сообщения журнала, включающего поля, параметры хранятся отдельно.</span><span class="sxs-lookup"><span data-stu-id="e5383-120">Instead of generating a textual log message that embeds fields, parameters are kept separate.</span></span> <span data-ttu-id="e5383-121">Это обеспечивает более интеллектуальную фильтрацию и поиск.</span><span class="sxs-lookup"><span data-stu-id="e5383-121">This allows for more intelligent filtering and searching.</span></span> <span data-ttu-id="e5383-122">Пример конфигурации Serilog для записи в Logstash показан на рис. 7-2.</span><span class="sxs-lookup"><span data-stu-id="e5383-122">A sample Serilog configuration for writing to Logstash appears in Figure 7-2.</span></span>

```csharp
var log = new LoggerConfiguration()
         .WriteTo.Http("http://localhost:8080")
         .CreateLogger();
```

<span data-ttu-id="e5383-123">**Рис. 7-2** Serilog config для записи сведений журнала непосредственно в logstash по протоколу HTTP</span><span class="sxs-lookup"><span data-stu-id="e5383-123">**Figure 7-2** Serilog config for writing log information directly to logstash over HTTP</span></span>

<span data-ttu-id="e5383-124">Logstash будет использовать конфигурацию, подобную показанной на рис. 7-3.</span><span class="sxs-lookup"><span data-stu-id="e5383-124">Logstash would use a configuration like the one shown in Figure 7-3.</span></span>

```
input {
    http {
        #default host 0.0.0.0:8080
        codec => json
    }
}

output {
    elasticsearch {
        hosts => "elasticsearch:9200"
        index=>"sales-%{+xxxx.ww}"
    }
}
```

<span data-ttu-id="e5383-125">**Рис. 7-3** . Конфигурация Logstash для использования журналов из Serilog</span><span class="sxs-lookup"><span data-stu-id="e5383-125">**Figure 7-3** - A Logstash configuration for consuming logs from Serilog</span></span>

<span data-ttu-id="e5383-126">Для сценариев, в которых не требуется много операций с журналами, существует альтернатива [Logstash, известного как](https://www.elastic.co/products/beats)незначительное.</span><span class="sxs-lookup"><span data-stu-id="e5383-126">For scenarios where extensive log manipulation isn't needed there's an alternative to Logstash known as [Beats](https://www.elastic.co/products/beats).</span></span> <span data-ttu-id="e5383-127">Ритм — это семейство средств, которое может собирать разнообразные данные из журналов в данные сети и сведения о времени работы.</span><span class="sxs-lookup"><span data-stu-id="e5383-127">Beats is a family of tools that can gather a wide variety of data from logs to network data and uptime information.</span></span> <span data-ttu-id="e5383-128">Многие приложения будут использовать как Logstash, так и ритмы.</span><span class="sxs-lookup"><span data-stu-id="e5383-128">Many applications will use both Logstash and Beats.</span></span>

<span data-ttu-id="e5383-129">После того, как журналы собраны с помощью Logstash, им нужно поместить их в любое место.</span><span class="sxs-lookup"><span data-stu-id="e5383-129">Once the logs have been gathered by Logstash, it needs somewhere to put them.</span></span> <span data-ttu-id="e5383-130">Хотя Logstash поддерживает множество различных выходов, одна из самых интересных — эластичный Поиск.</span><span class="sxs-lookup"><span data-stu-id="e5383-130">While Logstash supports many different outputs, one of the more exciting ones is Elastic search.</span></span>

## <a name="elastic-search"></a><span data-ttu-id="e5383-131">Эластичный Поиск</span><span class="sxs-lookup"><span data-stu-id="e5383-131">Elastic search</span></span>

<span data-ttu-id="e5383-132">Эластичный Поиск — это мощная поисковая система, которая может индексировать журналы по мере их поступления.</span><span class="sxs-lookup"><span data-stu-id="e5383-132">Elastic search is a powerful search engine that can index logs as they arrive.</span></span> <span data-ttu-id="e5383-133">Он позволяет быстро выполнять запросы к журналам.</span><span class="sxs-lookup"><span data-stu-id="e5383-133">It makes running queries against the logs quick.</span></span> <span data-ttu-id="e5383-134">Эластичный Поиск может обрабатывать огромные объемы журналов, и в крайних случаях их можно масштабировать на нескольких узлах.</span><span class="sxs-lookup"><span data-stu-id="e5383-134">Elastic search can handle huge quantities of logs and, in extreme cases, can be scaled out across many nodes.</span></span>

<span data-ttu-id="e5383-135">Сообщения журнала, которые были созданы для хранения параметров или которых были разделены с помощью обработки Logstash, можно запрашивать напрямую, так как Elasticsearch сохраняет эти сведения.</span><span class="sxs-lookup"><span data-stu-id="e5383-135">Log messages that have been crafted to contain parameters or that have had parameters split from them through Logstash processing, can be queried directly as Elasticsearch preserves this information.</span></span>

<span data-ttu-id="e5383-136">Запрос, выполняющий поиск 10 первых страниц, посещенных `jill@example.com`, отображается на рис. 7-4.</span><span class="sxs-lookup"><span data-stu-id="e5383-136">A query that searches for the top 10 pages visited by `jill@example.com`, appears in Figure 7-4.</span></span>

```
"query": {
    "match": {
      "user": "jill@example.com"
    }
  },
  "aggregations": {
    "top_10_pages": {
      "terms": {
        "field": "page",
        "size": 10
      }
    }
  }
```

<span data-ttu-id="e5383-137">**Рис. 7-4** . запрос Elasticsearch для поиска 10 ведущих страниц, посещенных пользователем</span><span class="sxs-lookup"><span data-stu-id="e5383-137">**Figure 7-4** - An Elasticsearch query for finding top 10 pages visited by a user</span></span>

## <a name="visualizing-information-with-kibana-web-dashboards"></a><span data-ttu-id="e5383-138">Визуализация информации с помощью веб-панелей мониторинга Kibana</span><span class="sxs-lookup"><span data-stu-id="e5383-138">Visualizing information with Kibana web dashboards</span></span>

<span data-ttu-id="e5383-139">Последним компонентом стека является Kibana.</span><span class="sxs-lookup"><span data-stu-id="e5383-139">The final component of the stack is Kibana.</span></span> <span data-ttu-id="e5383-140">Это средство используется для предоставления интерактивных визуализаций на веб-панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="e5383-140">This tool is used to provide interactive visualizations in a web dashboard.</span></span> <span data-ttu-id="e5383-141">Панели мониторинга могут создаваться даже пользователями, которые не являются техническими.</span><span class="sxs-lookup"><span data-stu-id="e5383-141">Dashboards may be crafted even by users who are non-technical.</span></span> <span data-ttu-id="e5383-142">Большинство данных, находящихся в Elasticsearch индексе, могут быть добавлены на панели мониторинга Kibana.</span><span class="sxs-lookup"><span data-stu-id="e5383-142">Most data that is resident in the Elasticsearch index, can be included in the Kibana dashboards.</span></span> <span data-ttu-id="e5383-143">Отдельные пользователи могут иметь разную панель мониторинга, и Kibana обеспечивает эту настройку, позволяя пользователям просматривать панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="e5383-143">Individual users may have different dashboard desires and Kibana enables this customization through allowing user-specific dashboards.</span></span>

## <a name="installing-elastic-stack-on-azure"></a><span data-ttu-id="e5383-144">Установка эластичного стека в Azure</span><span class="sxs-lookup"><span data-stu-id="e5383-144">Installing Elastic Stack on Azure</span></span>

<span data-ttu-id="e5383-145">Эластичный стек можно установить в Azure несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="e5383-145">The Elastic stack can be installed on Azure in a number of ways.</span></span> <span data-ttu-id="e5383-146">Как всегда, можно [подготавливать виртуальные машины и устанавливать эластичный стек на них напрямую](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch).</span><span class="sxs-lookup"><span data-stu-id="e5383-146">As always, it's possible to [provision virtual machines and install Elastic Stack on them directly](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch).</span></span> <span data-ttu-id="e5383-147">Этот вариант является предпочтительным для некоторых опытных пользователей, так как он обеспечивает наивысшую степень настройки.</span><span class="sxs-lookup"><span data-stu-id="e5383-147">This option is preferred by some experienced users as it offers the highest degree of customizability.</span></span> <span data-ttu-id="e5383-148">При развертывании на основе инфраструктуры в качестве службы вы узнаете о значительных затратах на управление, которые применяют этот путь, чтобы стать владельцем всех задач, связанных с инфраструктурой, таких как обеспечение безопасности компьютеров и обновление исправлений.</span><span class="sxs-lookup"><span data-stu-id="e5383-148">Deploying on infrastructure as a service introduces significant management overhead forcing those who take that path to take ownership of all the tasks associated with infrastructure as a service such as securing the machines and keeping up-to-date with patches.</span></span>

<span data-ttu-id="e5383-149">Параметр с меньшими издержками заключается в использовании одного из многих контейнеров DOCKER, для которых уже настроен эластичный стек.</span><span class="sxs-lookup"><span data-stu-id="e5383-149">An option with less overhead is to make use of one of the many Docker containers on which the Elastic Stack has already been configured.</span></span> <span data-ttu-id="e5383-150">Эти контейнеры можно удалить в существующий кластер Kubernetes и запустить вместе с кодом приложения.</span><span class="sxs-lookup"><span data-stu-id="e5383-150">These containers can be dropped into an existing Kubernetes cluster and run alongside application code.</span></span> <span data-ttu-id="e5383-151">Контейнер [себп/Elk](https://elk-docker.readthedocs.io/) — это хорошо документированный и протестированный контейнер эластичного стека.</span><span class="sxs-lookup"><span data-stu-id="e5383-151">The [sebp/elk](https://elk-docker.readthedocs.io/) container is a well-documented and tested Elastic Stack container.</span></span>

<span data-ttu-id="e5383-152">Другой вариант — [недавно объявленное предложение Elk как услуга](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/).</span><span class="sxs-lookup"><span data-stu-id="e5383-152">Another option is a [recently announced ELK-as-a-service offering](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/).</span></span>

## <a name="references"></a><span data-ttu-id="e5383-153">Ссылки</span><span class="sxs-lookup"><span data-stu-id="e5383-153">References</span></span>

- [<span data-ttu-id="e5383-154">Установка эластичного стека в Azure</span><span class="sxs-lookup"><span data-stu-id="e5383-154">Install Elastic Stack on Azure</span></span>](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch)

>[!div class="step-by-step"]
><span data-ttu-id="e5383-155">[Назад](observability-patterns.md)
>[Вперед](monitoring-azure-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="e5383-155">[Previous](observability-patterns.md)
[Next](monitoring-azure-kubernetes.md)</span></span>
