---
title: Что такое Apache Spark?
description: Сведения об Apache Spark и сценариях обработки больших данных.
ms.date: 10/15/2019
ms.topic: conceptual
ms.custom: mvc
ms.openlocfilehash: 653f355d09a045feabb3dee0f5737cb691cf2dc4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458175"
---
# <a name="what-is-apache-spark"></a><span data-ttu-id="eee36-103">Что такое Apache Spark?</span><span class="sxs-lookup"><span data-stu-id="eee36-103">What is Apache Spark?</span></span>

<span data-ttu-id="eee36-104">[Apache Spark](https://spark.apache.org/) — это платформа параллельной обработки с открытым кодом, которая поддерживает обработку в памяти, чтобы повысить производительность приложений, анализирующих большие данные.</span><span class="sxs-lookup"><span data-stu-id="eee36-104">[Apache Spark](https://spark.apache.org/) is an open-source parallel processing framework that supports in-memory processing to boost the performance of applications that analyze big data.</span></span> <span data-ttu-id="eee36-105">Решения для работы с большими данными предназначены для обработки данных со слишком большим объемом или сложностью для традиционных баз данных.</span><span class="sxs-lookup"><span data-stu-id="eee36-105">Big data solutions are designed to handle data that is too large or complex for traditional databases.</span></span> <span data-ttu-id="eee36-106">Spark обрабатывает большие объемы данных в памяти, что намного быстрее, чем альтернативная обработка с использованием диска.</span><span class="sxs-lookup"><span data-stu-id="eee36-106">Spark processes large amounts of data in memory, which is much faster than disk-based alternatives.</span></span>

## <a name="common-big-data-scenarios"></a><span data-ttu-id="eee36-107">Типичные сценарии обработки больших данных</span><span class="sxs-lookup"><span data-stu-id="eee36-107">Common big data scenarios</span></span>

<span data-ttu-id="eee36-108">Архитектура для работы с большими данными полезна, если вам нужно хранить и обрабатывать большие объемы данных, преобразовывать неструктурированные данные или обрабатывать потоковые данные.</span><span class="sxs-lookup"><span data-stu-id="eee36-108">You might consider a big data architecture if you need to store and process large volumes of data, transform unstructured data, or processes streaming data.</span></span> <span data-ttu-id="eee36-109">Spark предоставляет механизм распределенной обработки широкого назначения, который позволяет реализовать несколько сценариев работы с большими данными.</span><span class="sxs-lookup"><span data-stu-id="eee36-109">Spark is a general-purpose distributed processing engine that can be used for several big data scenarios.</span></span>

### <a name="extract-transform-and-load-etl"></a><span data-ttu-id="eee36-110">Извлечение, преобразование и загрузка (ETL)</span><span class="sxs-lookup"><span data-stu-id="eee36-110">Extract, transform, and load (ETL)</span></span>

<span data-ttu-id="eee36-111">Процесс [извлечения, преобразования и загрузки (ETL)](/azure/architecture/data-guide/relational-data/etl) включает сбор данных из одного или нескольких источников, изменение этих данных и их перемещение в новое хранилище.</span><span class="sxs-lookup"><span data-stu-id="eee36-111">[Extract, transform, and load (ETL)](/azure/architecture/data-guide/relational-data/etl) is the process of collecting data from one or multiple sources, modifying the data, and moving the data to a new data store.</span></span> <span data-ttu-id="eee36-112">Есть несколько способов преобразовать данные, например:</span><span class="sxs-lookup"><span data-stu-id="eee36-112">There are several ways to transform data, including:</span></span>

* <span data-ttu-id="eee36-113">Фильтрация</span><span class="sxs-lookup"><span data-stu-id="eee36-113">Filtering</span></span>
* <span data-ttu-id="eee36-114">Сортировка</span><span class="sxs-lookup"><span data-stu-id="eee36-114">Sorting</span></span>
* <span data-ttu-id="eee36-115">статистическая обработка;</span><span class="sxs-lookup"><span data-stu-id="eee36-115">Aggregating</span></span>
* <span data-ttu-id="eee36-116">Соединение</span><span class="sxs-lookup"><span data-stu-id="eee36-116">Joining</span></span>
* <span data-ttu-id="eee36-117">очистка;</span><span class="sxs-lookup"><span data-stu-id="eee36-117">Cleaning</span></span>
* <span data-ttu-id="eee36-118">дедупликация;</span><span class="sxs-lookup"><span data-stu-id="eee36-118">Deduplicating</span></span>
* <span data-ttu-id="eee36-119">Validating</span><span class="sxs-lookup"><span data-stu-id="eee36-119">Validating</span></span>

### <a name="real-time-data-stream-processing"></a><span data-ttu-id="eee36-120">Обработка потоков данных в реальном времени</span><span class="sxs-lookup"><span data-stu-id="eee36-120">Real-time data stream processing</span></span>

<span data-ttu-id="eee36-121">Данными потоковой передачи (реального времени) называют данные, которые находятся в движении.</span><span class="sxs-lookup"><span data-stu-id="eee36-121">Streaming, or real-time, data is data in motion.</span></span> <span data-ttu-id="eee36-122">К ним относятся, например, данные телеметрии от устройств Интернета вещей, веб-журналы и сведения о посещении ресурсов.</span><span class="sxs-lookup"><span data-stu-id="eee36-122">Telemetry from IoT devices, weblogs, and clickstreams are all examples of streaming data.</span></span> <span data-ttu-id="eee36-123">Обработка данных реального времени позволяет получить полезные сведения (например, с помощью геопространственного анализа, удаленного мониторинга и обнаружения аномалий).</span><span class="sxs-lookup"><span data-stu-id="eee36-123">Real-time data can be processed to provide useful information, such as geospatial analysis, remote monitoring, and anomaly detection.</span></span> <span data-ttu-id="eee36-124">Как и в случае с реляционными данными, перед перемещением потоковых данных в приемник вы можете их фильтровать, объединять и подготавливать.</span><span class="sxs-lookup"><span data-stu-id="eee36-124">Just like relational data, you can filter, aggregate, and prepare streaming data before moving the data to an output sink.</span></span> <span data-ttu-id="eee36-125">Apache Spark поддерживает [обработку потока данных реального времени](/azure/architecture/data-guide/big-data/real-time-processing) с помощью [потоковой передачи Spark](https://spark.apache.org/streaming/).</span><span class="sxs-lookup"><span data-stu-id="eee36-125">Apache Spark supports [real-time data stream processing](/azure/architecture/data-guide/big-data/real-time-processing) through [Spark Streaming](https://spark.apache.org/streaming/).</span></span>

### <a name="batch-processing"></a><span data-ttu-id="eee36-126">Пакетная обработка</span><span class="sxs-lookup"><span data-stu-id="eee36-126">Batch processing</span></span>

<span data-ttu-id="eee36-127">[Пакетная обработка](/azure/architecture/data-guide/big-data/batch-processing) — это обработка неактивных больших данных.</span><span class="sxs-lookup"><span data-stu-id="eee36-127">[Batch processing](/azure/architecture/data-guide/big-data/batch-processing) is the processing of big data at rest.</span></span> <span data-ttu-id="eee36-128">Вы можете фильтровать, объединять и подготавливать очень большие наборы данных с помощью длительно выполняющихся параллельных заданий.</span><span class="sxs-lookup"><span data-stu-id="eee36-128">You can filter, aggregate, and prepare very large datasets using long-running jobs in parallel.</span></span>

### <a name="machine-learning-through-mllib"></a><span data-ttu-id="eee36-129">Машинное обучение с использованием MLlib</span><span class="sxs-lookup"><span data-stu-id="eee36-129">Machine learning through MLlib</span></span>

<span data-ttu-id="eee36-130">Машинное обучение позволяет выполнять расширенные аналитические задачи.</span><span class="sxs-lookup"><span data-stu-id="eee36-130">Machine learning is used for advanced analytical problems.</span></span> <span data-ttu-id="eee36-131">Ваш компьютер может использовать существующие данные для прогнозирования реакции, результатов и тенденций.</span><span class="sxs-lookup"><span data-stu-id="eee36-131">Your computer can use existing data to forecast or predict future behaviors, outcomes, and trends.</span></span> <span data-ttu-id="eee36-132">Библиотека машинного обучения [MLlib](https://spark.apache.org/mllib/) из Apache Spark содержит несколько алгоритмов машинного обучения и служебных программ.</span><span class="sxs-lookup"><span data-stu-id="eee36-132">Apache Spark's machine learning library, [MLlib](https://spark.apache.org/mllib/), contains several machine learning algorithms and utilities.</span></span>

### <a name="graph-processing-through-graphx"></a><span data-ttu-id="eee36-133">Обработка графов с помощью GraphX</span><span class="sxs-lookup"><span data-stu-id="eee36-133">Graph processing through GraphX</span></span>

<span data-ttu-id="eee36-134">Граф — это коллекция узлов, которые соединяются ребрами.</span><span class="sxs-lookup"><span data-stu-id="eee36-134">A graph is a collection of nodes connected by edges.</span></span> <span data-ttu-id="eee36-135">Вы можете использовать базу данных графов для иерархических или взаимосвязанных данных.</span><span class="sxs-lookup"><span data-stu-id="eee36-135">You might use a graph database if you have hierarchial data or data with interconnected relationships.</span></span> <span data-ttu-id="eee36-136">Такие данные можно обрабатывать с помощью API [GraphX](https://spark.apache.org/graphx/) в Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="eee36-136">You can process this data using Apache Spark's [GraphX](https://spark.apache.org/graphx/) API.</span></span>

### <a name="sql-and-structured-data-processing-with-spark-sql"></a><span data-ttu-id="eee36-137">Обработка SQL и структурированных данных с помощью Spark SQL</span><span class="sxs-lookup"><span data-stu-id="eee36-137">SQL and structured data processing with Spark SQL</span></span>

<span data-ttu-id="eee36-138">Для работы со структурированными (форматированными) данными в приложении Spark можно использовать SQL-запросы с помощью [Spark SQL](https://spark.apache.org/sql/).</span><span class="sxs-lookup"><span data-stu-id="eee36-138">If you're working with structured (formatted) data, you can use SQL queries in your Spark application using [Spark SQL](https://spark.apache.org/sql/).</span></span>

## <a name="apache-spark-architecture"></a><span data-ttu-id="eee36-139">Архитектура Apache Spark</span><span class="sxs-lookup"><span data-stu-id="eee36-139">Apache Spark architecture</span></span>

<span data-ttu-id="eee36-140">Для Apache Spark при использовании архитектуры "основной-рабочий", предусмотрено три основных компонента: драйвер, исполнители и диспетчер кластера.</span><span class="sxs-lookup"><span data-stu-id="eee36-140">Apache Spark, which uses the master/worker architecture, has three main components: the driver, executors, and cluster manager.</span></span>

![Архитектура Apache Spark](media/spark-architecture.png)

### <a name="driver"></a><span data-ttu-id="eee36-142">Драйвер</span><span class="sxs-lookup"><span data-stu-id="eee36-142">Driver</span></span>

<span data-ttu-id="eee36-143">Драйвер состоит из пользовательской программы, например консольного приложения C#, и сеанса Spark.</span><span class="sxs-lookup"><span data-stu-id="eee36-143">The driver consists of your program, like a C# console app, and a Spark session.</span></span> <span data-ttu-id="eee36-144">Сеанс Spark принимает программу и делит ее на небольшие задачи, которые обрабатываются исполнителями.</span><span class="sxs-lookup"><span data-stu-id="eee36-144">The Spark session takes your program and divides it into smaller tasks that are handled by the executors.</span></span>

### <a name="executors"></a><span data-ttu-id="eee36-145">Исполнители</span><span class="sxs-lookup"><span data-stu-id="eee36-145">Executors</span></span>

<span data-ttu-id="eee36-146">Каждый исполнитель (рабочий узел) получает от драйвера задачу и выполняет ее.</span><span class="sxs-lookup"><span data-stu-id="eee36-146">Each executor, or worker node, receives a task from the driver and executes that task.</span></span> <span data-ttu-id="eee36-147">Исполнители находятся в сущности, которая называется кластером.</span><span class="sxs-lookup"><span data-stu-id="eee36-147">The executors reside on an entity known as a cluster.</span></span>

### <a name="cluster-manager"></a><span data-ttu-id="eee36-148">Диспетчер кластера</span><span class="sxs-lookup"><span data-stu-id="eee36-148">Cluster manager</span></span>

<span data-ttu-id="eee36-149">Диспетчер кластера взаимодействует с драйвером и исполнителями, выполняя следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="eee36-149">The cluster manager communicates with both the driver and the executors to:</span></span>

* <span data-ttu-id="eee36-150">управление выделением ресурсов;</span><span class="sxs-lookup"><span data-stu-id="eee36-150">Manage resource allocation</span></span>
* <span data-ttu-id="eee36-151">управление разделением программы;</span><span class="sxs-lookup"><span data-stu-id="eee36-151">Manage program division</span></span>
* <span data-ttu-id="eee36-152">управление выполнением программы.</span><span class="sxs-lookup"><span data-stu-id="eee36-152">Manage program execution</span></span>

## <a name="language-support"></a><span data-ttu-id="eee36-153">Языковая поддержка</span><span class="sxs-lookup"><span data-stu-id="eee36-153">Language support</span></span>

<span data-ttu-id="eee36-154">Apache Spark поддерживает следующие языки программирования:</span><span class="sxs-lookup"><span data-stu-id="eee36-154">Apache Spark supports the following programming languages:</span></span>

* <span data-ttu-id="eee36-155">Scala</span><span class="sxs-lookup"><span data-stu-id="eee36-155">Scala</span></span>
* <span data-ttu-id="eee36-156">Python</span><span class="sxs-lookup"><span data-stu-id="eee36-156">Python</span></span>
* <span data-ttu-id="eee36-157">Java</span><span class="sxs-lookup"><span data-stu-id="eee36-157">Java</span></span>
* <span data-ttu-id="eee36-158">SQL-код</span><span class="sxs-lookup"><span data-stu-id="eee36-158">SQL</span></span>
* <span data-ttu-id="eee36-159">R</span><span class="sxs-lookup"><span data-stu-id="eee36-159">R</span></span>
* <span data-ttu-id="eee36-160">.NET</span><span class="sxs-lookup"><span data-stu-id="eee36-160">.NET</span></span>

## <a name="spark-apis"></a><span data-ttu-id="eee36-161">API-интерфейсы Spark</span><span class="sxs-lookup"><span data-stu-id="eee36-161">Spark APIs</span></span>

<span data-ttu-id="eee36-162">Apache Spark поддерживает следующие API:</span><span class="sxs-lookup"><span data-stu-id="eee36-162">Apache Spark supports the following APIs:</span></span>

* <span data-ttu-id="eee36-163">[API Scala для Spark](https://spark.apache.org/docs/2.2.0/api/scala/index.html);</span><span class="sxs-lookup"><span data-stu-id="eee36-163">[Spark Scala API](https://spark.apache.org/docs/2.2.0/api/scala/index.html)</span></span>
* <span data-ttu-id="eee36-164">[API Java для Spark](https://spark.apache.org/docs/2.2.0/api/java/index.html);</span><span class="sxs-lookup"><span data-stu-id="eee36-164">[Spark Java API](https://spark.apache.org/docs/2.2.0/api/java/index.html)</span></span>
* <span data-ttu-id="eee36-165">[API Python для Spark](https://spark.apache.org/docs/2.2.0/api/python/index.html);</span><span class="sxs-lookup"><span data-stu-id="eee36-165">[Spark Python API](https://spark.apache.org/docs/2.2.0/api/python/index.html)</span></span>
* <span data-ttu-id="eee36-166">[API R для Spark](https://spark.apache.org/docs/2.2.0/api/R/index.html);</span><span class="sxs-lookup"><span data-stu-id="eee36-166">[Spark R API](https://spark.apache.org/docs/2.2.0/api/R/index.html)</span></span>
* <span data-ttu-id="eee36-167">[Spark SQL](https://spark.apache.org/docs/latest/api/sql/index.html), встроенные функции.</span><span class="sxs-lookup"><span data-stu-id="eee36-167">[Spark SQL](https://spark.apache.org/docs/latest/api/sql/index.html), built-in functions</span></span>

## <a name="next-steps"></a><span data-ttu-id="eee36-168">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="eee36-168">Next steps</span></span>

<span data-ttu-id="eee36-169">Сведения об использовании Apache Spark в приложениях .NET.</span><span class="sxs-lookup"><span data-stu-id="eee36-169">Learn how you can use Apache Spark in your .NET application.</span></span> <span data-ttu-id="eee36-170">.NET для Apache Spark позволяет разработчикам, имеющим опыт работы с .NET, создавать запросы для обработки больших данных на C# или F#.</span><span class="sxs-lookup"><span data-stu-id="eee36-170">With .NET for Apache Spark, developers with .NET experience and business logic can write big data queries in C# and F#.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="eee36-171">Что такое .NET для Apache Spark?</span><span class="sxs-lookup"><span data-stu-id="eee36-171">What is .NET for Apache Spark</span></span>](what-is-apache-spark-dotnet.md)
