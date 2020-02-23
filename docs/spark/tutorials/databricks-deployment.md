---
title: Развертывание приложения .NET для Apache Spark в Databricks
description: Узнайте, как развернуть приложение .NET для Apache Spark в Databricks.
ms.date: 01/23/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: c5308530831fa288bf637849c1342f51769c3ad4
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503960"
---
# <a name="tutorial-deploy-a-net-for-apache-spark-application-to-databricks"></a><span data-ttu-id="9f857-103">Учебник. Развертывание приложения .NET для Apache Spark в Databricks</span><span class="sxs-lookup"><span data-stu-id="9f857-103">Tutorial: Deploy a .NET for Apache Spark application to Databricks</span></span>

<span data-ttu-id="9f857-104">В этом учебнике описывается, как развернуть приложение в облаке с помощью Azure Databricks, платформу для аналитики на базе Apache Spark. Платформа настраивается одним щелчком, упрощает рабочие процессы и предоставляет интерактивную рабочую область для совместной работы.</span><span class="sxs-lookup"><span data-stu-id="9f857-104">This tutorial teaches you how to deploy your app to the cloud through Azure Databricks, an Apache Spark-based analytics platform with one-click setup, streamlined workflows, and interactive workspace that enables collaboration.</span></span>

<span data-ttu-id="9f857-105">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="9f857-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="9f857-106">создание рабочей области Azure Databricks;</span><span class="sxs-lookup"><span data-stu-id="9f857-106">Create an Azure Databricks workspace.</span></span>
> - <span data-ttu-id="9f857-107">Опубликовать приложение .NET для Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="9f857-107">Publish your .NET for Apache Spark app.</span></span>
> - <span data-ttu-id="9f857-108">Создать задание Spark и кластер Spark.</span><span class="sxs-lookup"><span data-stu-id="9f857-108">Create a Spark job and Spark cluster.</span></span>
> - <span data-ttu-id="9f857-109">Запустить приложение в кластере Spark.</span><span class="sxs-lookup"><span data-stu-id="9f857-109">Run your app on the Spark cluster.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9f857-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9f857-110">Prerequisites</span></span>

<span data-ttu-id="9f857-111">Прежде чем начать, сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="9f857-111">Before you start, do the following tasks:</span></span>

* <span data-ttu-id="9f857-112">Если у вас нет учетной записи, вы можете создать [бесплатную учетную запись](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="9f857-112">If you don't have an Azure account, create a [free account](https://azure.microsoft.com/free/).</span></span>
* <span data-ttu-id="9f857-113">Войдите на [портале Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="9f857-113">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
* <span data-ttu-id="9f857-114">Пройдите учебник [.NET для Apache Spark — начало работы за 10 минут](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro).</span><span class="sxs-lookup"><span data-stu-id="9f857-114">Complete the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial.</span></span>

## <a name="create-an-azure-databricks-workspace"></a><span data-ttu-id="9f857-115">Создание рабочей области Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="9f857-115">Create an Azure Databricks workspace</span></span>

> [!Note]
> <span data-ttu-id="9f857-116">Инструкции из этого руководство нельзя выполнять с **бесплатной пробной версией подписки**.</span><span class="sxs-lookup"><span data-stu-id="9f857-116">This tutorial cannot be carried out using **Azure Free Trial Subscription**.</span></span>
> <span data-ttu-id="9f857-117">Если у вас есть бесплатная учетная запись, перейдите к профилю и измените подписку на подписку с **оплатой по мере использования**.</span><span class="sxs-lookup"><span data-stu-id="9f857-117">If you have a free account, go to your profile and change your subscription to **pay-as-you-go**.</span></span> <span data-ttu-id="9f857-118">Дополнительные сведения см. на странице [создания бесплатной учетной записи Azure](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="9f857-118">For more information, see [Azure free account](https://azure.microsoft.com/free/).</span></span> <span data-ttu-id="9f857-119">Затем [удалите предельную сумму расходов](https://docs.microsoft.com/azure/billing/billing-spending-limit#why-you-might-want-to-remove-the-spending-limit) и [запросите увеличение квоты](https://docs.microsoft.com/azure/azure-supportability/resource-manager-core-quotas-request) на ЦП в своем регионе.</span><span class="sxs-lookup"><span data-stu-id="9f857-119">Then, [remove the spending limit](https://docs.microsoft.com/azure/billing/billing-spending-limit#why-you-might-want-to-remove-the-spending-limit), and [request a quota increase](https://docs.microsoft.com/azure/azure-supportability/resource-manager-core-quotas-request) for vCPUs in your region.</span></span> <span data-ttu-id="9f857-120">При создании рабочей области Azure Databricks можно выбрать ценовую категорию **Пробная версия ("Премиум" — 14 дней бесплатно (DBU))** для предоставления рабочей области доступа к бесплатным DBU Azure Databricks уровня "Премиум" на 14 дней.</span><span class="sxs-lookup"><span data-stu-id="9f857-120">When you create your Azure Databricks workspace, you can select the **Trial (Premium - 14-Days Free DBUs)** pricing tier to give the workspace access to free Premium Azure Databricks DBUs for 14 days.</span></span>

<span data-ttu-id="9f857-121">В этом разделе вы создадите рабочую область Azure Databricks с помощью портала Azure.</span><span class="sxs-lookup"><span data-stu-id="9f857-121">In this section, you create an Azure Databricks workspace using the Azure portal.</span></span>

1. <span data-ttu-id="9f857-122">На портале Azure выберите **Создать ресурс** > **Analytics** > **Azure Databricks**.</span><span class="sxs-lookup"><span data-stu-id="9f857-122">In the Azure portal, select **Create a resource** > **Analytics** > **Azure Databricks**.</span></span>

   ![Создание ресурса Azure Databricks на портале Azure](./media/databricks-deployment/create-databricks-resource.png)

2. <span data-ttu-id="9f857-124">В разделе **службы Azure Databricks** укажите значения для создания рабочей области Databricks.</span><span class="sxs-lookup"><span data-stu-id="9f857-124">Under **Azure Databricks Service**, provide the values to create a Databricks workspace.</span></span>

    |<span data-ttu-id="9f857-125">Свойство.</span><span class="sxs-lookup"><span data-stu-id="9f857-125">Property</span></span>  |<span data-ttu-id="9f857-126">Описание</span><span class="sxs-lookup"><span data-stu-id="9f857-126">Description</span></span>  |
    |---------|---------|
    |<span data-ttu-id="9f857-127">**Имя рабочей области**</span><span class="sxs-lookup"><span data-stu-id="9f857-127">**Workspace name**</span></span>     | <span data-ttu-id="9f857-128">Укажите имя рабочей области Databricks.</span><span class="sxs-lookup"><span data-stu-id="9f857-128">Provide a name for your Databricks workspace.</span></span>        |
    |<span data-ttu-id="9f857-129">**Подписка**</span><span class="sxs-lookup"><span data-stu-id="9f857-129">**Subscription**</span></span>     | <span data-ttu-id="9f857-130">Выберите подписку Azure в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="9f857-130">From the drop-down, select your Azure subscription.</span></span>        |
    |<span data-ttu-id="9f857-131">**Группа ресурсов**</span><span class="sxs-lookup"><span data-stu-id="9f857-131">**Resource group**</span></span>     | <span data-ttu-id="9f857-132">Укажите, следует ли создать новую группу ресурсов или использовать имеющуюся.</span><span class="sxs-lookup"><span data-stu-id="9f857-132">Specify whether you want to create a new resource group or use an existing one.</span></span> <span data-ttu-id="9f857-133">Группа ресурсов — это контейнер, содержащий связанные ресурсы для решения Azure.</span><span class="sxs-lookup"><span data-stu-id="9f857-133">A resource group is a container that holds related resources for an Azure solution.</span></span> <span data-ttu-id="9f857-134">Дополнительные сведения см. в [обзоре группы ресурсов Azure](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview).</span><span class="sxs-lookup"><span data-stu-id="9f857-134">For more information, see [Azure Resource Group overview](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview).</span></span> |
    |<span data-ttu-id="9f857-135">**Расположение**</span><span class="sxs-lookup"><span data-stu-id="9f857-135">**Location**</span></span>     | <span data-ttu-id="9f857-136">Выберите предпочитаемый регион.</span><span class="sxs-lookup"><span data-stu-id="9f857-136">Select your preferred region.</span></span> <span data-ttu-id="9f857-137">Доступные регионы см. в статье о [доступности служб Azure по регионам](https://azure.microsoft.com/regions/services/).</span><span class="sxs-lookup"><span data-stu-id="9f857-137">For information about available regions, see [Azure services available by region](https://azure.microsoft.com/regions/services/).</span></span>        |
    |<span data-ttu-id="9f857-138">**Ценовая категория**</span><span class="sxs-lookup"><span data-stu-id="9f857-138">**Pricing Tier**</span></span>     |  <span data-ttu-id="9f857-139">Вы можете выбрать уровень **Стандартный** или **Премиум** или воспользоваться **бесплатной пробной версией**.</span><span class="sxs-lookup"><span data-stu-id="9f857-139">Choose between **Standard**, **Premium**, or **Trial**.</span></span> <span data-ttu-id="9f857-140">Дополнительные сведения об этих ценовых категориях см. на [странице цен на Databricks](https://azure.microsoft.com/pricing/details/databricks/).</span><span class="sxs-lookup"><span data-stu-id="9f857-140">For more information on these tiers, see [Databricks pricing page](https://azure.microsoft.com/pricing/details/databricks/).</span></span>       |
    |<span data-ttu-id="9f857-141">**Виртуальная сеть**</span><span class="sxs-lookup"><span data-stu-id="9f857-141">**Virtual Network**</span></span>     |   <span data-ttu-id="9f857-142">Нет</span><span class="sxs-lookup"><span data-stu-id="9f857-142">No</span></span>       |

3. <span data-ttu-id="9f857-143">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="9f857-143">Select **Create**.</span></span> <span data-ttu-id="9f857-144">Создание рабочей области займет несколько минут.</span><span class="sxs-lookup"><span data-stu-id="9f857-144">The workspace creation takes a few minutes.</span></span> <span data-ttu-id="9f857-145">Во время создания рабочей области состояние развертывания можно просмотреть в области **Уведомления**.</span><span class="sxs-lookup"><span data-stu-id="9f857-145">During workspace creation, you can view the deployment status in **Notifications**.</span></span>

## <a name="install-azure-databricks-tools"></a><span data-ttu-id="9f857-146">Установка средств Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="9f857-146">Install Azure Databricks tools</span></span>

<span data-ttu-id="9f857-147">Для подключения к кластерам Azure Databricks и передачи файлов с локального компьютера можно использовать **интерфейс командной строки Databricks**.</span><span class="sxs-lookup"><span data-stu-id="9f857-147">You can use the **Databricks CLI** to connect to Azure Databricks clusters and upload files to them from your local machine.</span></span> <span data-ttu-id="9f857-148">В кластерах Databricks доступ к файлам осуществляется через DBFS (файловая система Databricks).</span><span class="sxs-lookup"><span data-stu-id="9f857-148">Databricks clusters access files through DBFS (Databricks File System).</span></span>

1. <span data-ttu-id="9f857-149">Для работы интерфейса командной строки Databricks требуется Python 3.6 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="9f857-149">The Databricks CLI requires Python 3.6 or above.</span></span> <span data-ttu-id="9f857-150">Если у вас уже установлен Python, можно перейти к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="9f857-150">If you already have Python installed, you can skip this step.</span></span>

   <span data-ttu-id="9f857-151">**Для Windows:**</span><span class="sxs-lookup"><span data-stu-id="9f857-151">**For Windows:**</span></span>

   [<span data-ttu-id="9f857-152">Загрузка Python для Windows</span><span class="sxs-lookup"><span data-stu-id="9f857-152">Download Python for Windows</span></span>](https://www.python.org/ftp/python/3.7.4/python-3.7.4.exe)

   <span data-ttu-id="9f857-153">**Для Linux:** Python предустановлен в большинстве дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="9f857-153">**For Linux:** Python comes preinstalled on most Linux distributions.</span></span> <span data-ttu-id="9f857-154">Выполните следующую команду, чтобы узнать, какая версия установлена:</span><span class="sxs-lookup"><span data-stu-id="9f857-154">Run the following command to see which version you have installed:</span></span>

   ```bash
   python3 --version
   ```

2. <span data-ttu-id="9f857-155">Установите интерфейс командной строки Databricks с помощью pip.</span><span class="sxs-lookup"><span data-stu-id="9f857-155">Use pip to install the Databricks CLI.</span></span> <span data-ttu-id="9f857-156">В Python 3.4 и более поздних версий pip включен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9f857-156">Python 3.4 and later include pip by default.</span></span> <span data-ttu-id="9f857-157">Используйте pip3 для Python 3.</span><span class="sxs-lookup"><span data-stu-id="9f857-157">Use pip3 for Python 3.</span></span> <span data-ttu-id="9f857-158">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9f857-158">Run the following command:</span></span>

   ```bash
   pip3 install databricks-cli
   ```

3. <span data-ttu-id="9f857-159">После установки интерфейса командной строки Databricks откройте новую командную строку и выполните команду `databricks`.</span><span class="sxs-lookup"><span data-stu-id="9f857-159">Once you've installed the Databricks CLI, open a new command prompt and run the command `databricks`.</span></span> <span data-ttu-id="9f857-160">Если вы получаете **внутреннюю или внешнюю ошибку команды о том, что Databricks не распознан**, убедитесь, что открыли новую командную строку.</span><span class="sxs-lookup"><span data-stu-id="9f857-160">If you receive a **'databricks' is not recognized as an internal or external command error**, make sure you opened a new command prompt.</span></span>

## <a name="set-up-azure-databricks"></a><span data-ttu-id="9f857-161">Настройка Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="9f857-161">Set up Azure Databricks</span></span>

<span data-ttu-id="9f857-162">Теперь, когда интерфейс командной строки Databricks установлен, необходимо настроить сведения о проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="9f857-162">Now that you have the Databricks CLI installed, you need to set up authentication details.</span></span>

1. <span data-ttu-id="9f857-163">В интерфейсе командной строки Databricks выполните команду `databricks configure --token`.</span><span class="sxs-lookup"><span data-stu-id="9f857-163">Run the Databricks CLI command `databricks configure --token`.</span></span>

2. <span data-ttu-id="9f857-164">После выполнения команды конфигурации будет предложено ввести узел.</span><span class="sxs-lookup"><span data-stu-id="9f857-164">After running the configure command, you are prompted to enter a host.</span></span> <span data-ttu-id="9f857-165">URL-адрес узла использует формат: **https://<\Location>.azuredatabricks.net**.</span><span class="sxs-lookup"><span data-stu-id="9f857-165">Your host URL uses the format: **https://<\Location>.azuredatabricks.net**.</span></span> <span data-ttu-id="9f857-166">Например, если вы выбрали **eastus2** при создании службы Azure Databricks, узел будет **https://eastus2.azuredatabricks.net** .</span><span class="sxs-lookup"><span data-stu-id="9f857-166">For instance, if you selected **eastus2** during Azure Databricks Service creation, the host would be **https://eastus2.azuredatabricks.net**.</span></span>

3. <span data-ttu-id="9f857-167">После ввода узла вам будет предложено ввести маркер.</span><span class="sxs-lookup"><span data-stu-id="9f857-167">After entering your host, you are prompted to enter a token.</span></span> <span data-ttu-id="9f857-168">На портале Azure выберите **Запустить рабочую область**, чтобы запустить рабочую область Azure Databricks.</span><span class="sxs-lookup"><span data-stu-id="9f857-168">In the Azure portal, select **Launch Workspace** to launch your Azure Databricks workspace.</span></span>

   ![Запуск рабочей области Azure Databricks](./media/databricks-deployment/launch-databricks-workspace.png)

4. <span data-ttu-id="9f857-170">На домашней странице рабочей области выберите **Параметры пользователя**.</span><span class="sxs-lookup"><span data-stu-id="9f857-170">On the home page of your workspace, select **User Settings**.</span></span>

   ![Параметры пользователя рабочей области Azure Databricks](./media/databricks-deployment/databricks-user-settings.png)

5. <span data-ttu-id="9f857-172">На странице "Параметры пользователя" можно создать новый маркер.</span><span class="sxs-lookup"><span data-stu-id="9f857-172">On the User Settings page, you can generate a new token.</span></span> <span data-ttu-id="9f857-173">Скопируйте созданный маркер и вставьте его обратно в командную строку.</span><span class="sxs-lookup"><span data-stu-id="9f857-173">Copy the generated token and paste it back into your command prompt.</span></span>

   ![Создание нового маркера доступа в рабочей области Azure Databricks](./media/databricks-deployment/generate-token.png)

<span data-ttu-id="9f857-175">Теперь вы можете получить доступ ко всем кластерам Azure Databricks, которые вы создаете, и отправить файлы в DBFS.</span><span class="sxs-lookup"><span data-stu-id="9f857-175">You should now be able to access any Azure Databricks clusters you create and upload files to the DBFS.</span></span>

## <a name="download-worker-dependencies"></a><span data-ttu-id="9f857-176">Загрузка зависимостей рабочей роли</span><span class="sxs-lookup"><span data-stu-id="9f857-176">Download worker dependencies</span></span>

1. <span data-ttu-id="9f857-177">Microsoft.Spark.Worker помогает Apache Spark запускать ваше приложение, например пользовательские функции (UDF), которые вы написали.</span><span class="sxs-lookup"><span data-stu-id="9f857-177">Microsoft.Spark.Worker helps Apache Spark execute your app, such as any user-defined functions (UDFs) you may have written.</span></span> <span data-ttu-id="9f857-178">Загрузите [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="9f857-178">Download [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz).</span></span>

2. <span data-ttu-id="9f857-179">*install-worker.sh* — это скрипт, который позволяет копировать зависимые файлы .NET для Apache Spark в узлы кластера.</span><span class="sxs-lookup"><span data-stu-id="9f857-179">The *install-worker.sh* is a script that lets you copy .NET for Apache Spark dependent files into the nodes of your cluster.</span></span>

   <span data-ttu-id="9f857-180">Создайте новый файл с именем **install-worker.sh** на локальном компьютере и вставьте [содержимое файла install-worker.sh](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh), расположенного на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="9f857-180">Create a new file named **install-worker.sh** on your local computer, and paste the [install-worker.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) located on GitHub.</span></span>

3. <span data-ttu-id="9f857-181">*db-init.sh* — это скрипт, который устанавливает зависимости на кластер Databricks Spark.</span><span class="sxs-lookup"><span data-stu-id="9f857-181">The *db-init.sh* is a script that installs dependencies onto your Databricks Spark cluster.</span></span>

   <span data-ttu-id="9f857-182">Создайте новый файл с именем **db-init.sh** на локальном компьютере и вставьте [содержимое файла db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh), расположенного на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="9f857-182">Create a new file named **db-init.sh** on your local computer, and paste the [db-init.sh contents](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) located on GitHub.</span></span>

   <span data-ttu-id="9f857-183">В только что созданном файле задайте для переменной `DOTNET_SPARK_RELEASE` значение `https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz`.</span><span class="sxs-lookup"><span data-stu-id="9f857-183">In the file you just created, set the `DOTNET_SPARK_RELEASE` variable to `https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz`.</span></span> <span data-ttu-id="9f857-184">Оставьте остальную часть файла *db-init.sh* без изменений.</span><span class="sxs-lookup"><span data-stu-id="9f857-184">Leave the rest of the *db-init.sh* file as-is.</span></span>

> [!Note]
> <span data-ttu-id="9f857-185">Если вы используете Windows, убедитесь, что для окончаний строк в скриптах *install-worker.sh* и *db-init.sh* используется стиль Unix (LF).</span><span class="sxs-lookup"><span data-stu-id="9f857-185">If you are using Windows, verify that the line-endings in your *install-worker.sh* and *db-init.sh* scripts are Unix-style (LF).</span></span> <span data-ttu-id="9f857-186">Можно изменять окончания строк в текстовых редакторах, таких как Notepad++ и Atom.</span><span class="sxs-lookup"><span data-stu-id="9f857-186">You can change line endings through text editors like Notepad++ and Atom.</span></span>

## <a name="publish-your-app"></a><span data-ttu-id="9f857-187">Публикация приложения</span><span class="sxs-lookup"><span data-stu-id="9f857-187">Publish your app</span></span>

<span data-ttu-id="9f857-188">Затем вы публикуете приложение *mySparkApp*, созданное в учебнике [.NET для Apache Spark — начало работы за 10 минут](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro), чтобы кластер Spark имел доступ ко всем файлам, которые необходимы для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="9f857-188">Next, you publish the *mySparkApp* created in the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial to ensure your Spark cluster has access to all the files it needs to run your app.</span></span>

1. <span data-ttu-id="9f857-189">Для публикации *mySparkApp* выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="9f857-189">Run the following commands to publish the *mySparkApp*:</span></span>

   ```dotnetcli
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

2. <span data-ttu-id="9f857-190">Выполните следующие задачи и заархивируйте опубликованные файлы приложения, чтобы их можно было легко передать в кластер Databricks Spark.</span><span class="sxs-lookup"><span data-stu-id="9f857-190">Do the following tasks to zip your published app files so that you can easily upload them to your Databricks Spark cluster.</span></span>

   <span data-ttu-id="9f857-191">**В Windows:**</span><span class="sxs-lookup"><span data-stu-id="9f857-191">**On Windows:**</span></span>

   <span data-ttu-id="9f857-192">Перейдите в каталог mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64.</span><span class="sxs-lookup"><span data-stu-id="9f857-192">Navigate to mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64.</span></span> <span data-ttu-id="9f857-193">Затем щелкните правой кнопкой мыши папку **Publish** и выберите **Отправить > Сжатая ZIP-папка**.</span><span class="sxs-lookup"><span data-stu-id="9f857-193">Then, right-click on **Publish** folder and select **Send to > Compressed (zipped) folder**.</span></span> <span data-ttu-id="9f857-194">Назовите папку **publish.zip**.</span><span class="sxs-lookup"><span data-stu-id="9f857-194">Name the new folder **publish.zip**.</span></span>

   <span data-ttu-id="9f857-195">**В Linux выполните следующую команду:**</span><span class="sxs-lookup"><span data-stu-id="9f857-195">**On Linux, run the following command:**</span></span>

   ```bash
   zip -r publish.zip .
   ```

## <a name="upload-files"></a><span data-ttu-id="9f857-196">Отправка файлов</span><span class="sxs-lookup"><span data-stu-id="9f857-196">Upload files</span></span>

<span data-ttu-id="9f857-197">В этом разделе вы отправите в DBFS несколько файлов, чтобы в кластере было все необходимое для запуска приложения в облаке.</span><span class="sxs-lookup"><span data-stu-id="9f857-197">In this section, you upload several files to DBFS so that your cluster has everything it needs to run your app in the cloud.</span></span> <span data-ttu-id="9f857-198">Каждый раз при отправке файла в DBFS убеждайтесь, что вы находитесь в каталоге, где расположен этот файл на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9f857-198">Each time you upload a file to the DBFS, make sure you are in the directory where that file is located on your computer.</span></span>

1. <span data-ttu-id="9f857-199">Выполните следующие команды, чтобы отправить *db-init.sh*, *install-worker.sh* и *Microsoft.Spark.Worker* в DBFS:</span><span class="sxs-lookup"><span data-stu-id="9f857-199">Run the following commands to upload the *db-init.sh*, *install-worker.sh*, and *Microsoft.Spark.Worker* to DBFS:</span></span>

   ```console
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   databricks fs cp Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz dbfs:/spark-dotnet/   Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz
   ```

2. <span data-ttu-id="9f857-200">Выполните следующие команды, чтобы отправить оставшиеся файлы, необходимые кластеру для запуска приложения: ZIP-папку публикации, *input.txt* и *microsoft-spark-2.4.x-0.3.0.jar*.</span><span class="sxs-lookup"><span data-stu-id="9f857-200">Run the following commands to upload the remaining files your cluster will need to run your app: the zipped publish folder, *input.txt*, and *microsoft-spark-2.4.x-0.3.0.jar*.</span></span>

   ```console
   cd mySparkApp
   databricks fs cp input.txt dbfs:/input.txt

   cd mySparkApp\bin\Release\netcoreapp3.0\ubuntu.16.04-x64 directory
   databricks fs cp mySparkApp.zip dbfs:/spark-dotnet/publish.zip
   databricks fs cp microsoft-spark-2.4.x-0.6.0.jar dbfs:/spark-dotnet/microsoft-spark-2.4.x-0.6.0.jar
   ```

## <a name="create-a-job"></a><span data-ttu-id="9f857-201">Создание задания</span><span class="sxs-lookup"><span data-stu-id="9f857-201">Create a job</span></span>

<span data-ttu-id="9f857-202">Приложение выполняется на Azure Databricks с помощью задания, которое выполняет **spark-submit**. Это команда, используемая для запуска заданий .NET для Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="9f857-202">Your app runs on Azure Databricks through a job that runs **spark-submit**, which is the command you use to run .NET for Apache Spark jobs.</span></span>

1. <span data-ttu-id="9f857-203">В рабочей области Azure Databricks нажмите на значок **Задания**, а затем **+ Создать задание**.</span><span class="sxs-lookup"><span data-stu-id="9f857-203">In your Azure Databricks Workspace, select the **Jobs** icon and then **+ Create Job**.</span></span>

   ![Создание задания Azure Databricks](./media/databricks-deployment/create-job.png)

2. <span data-ttu-id="9f857-205">Выберите название задания, а затем нажмите **Настройка spark-submit**.</span><span class="sxs-lookup"><span data-stu-id="9f857-205">Choose a title for your job, and then select **Configure spark-submit**.</span></span>

   ![Настройка spark-submit для задания Databricks](./media/databricks-deployment/configure-spark-submit.png)

3. <span data-ttu-id="9f857-207">Вставьте следующие параметры в конфигурацию задания.</span><span class="sxs-lookup"><span data-stu-id="9f857-207">Paste the following parameters in the job configuration.</span></span> <span data-ttu-id="9f857-208">Затем выберите **Подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="9f857-208">Then, select **Confirm**.</span></span>

   ```
   ["--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/spark-dotnet/microsoft-spark-2.4.x-0.6.0.jar","/dbfs/spark-dotnet/publish.zip","mySparkApp"]
   ```

## <a name="create-a-cluster"></a><span data-ttu-id="9f857-209">Создание кластера</span><span class="sxs-lookup"><span data-stu-id="9f857-209">Create a cluster</span></span>

1. <span data-ttu-id="9f857-210">Перейдите к своему заданию и выберите **Изменить**, чтобы настроить кластер задания.</span><span class="sxs-lookup"><span data-stu-id="9f857-210">Navigate to your job and select **Edit** to configure your job's cluster.</span></span>

2. <span data-ttu-id="9f857-211">Выберите для кластера **Spark 2.4.1**.</span><span class="sxs-lookup"><span data-stu-id="9f857-211">Set your cluster to **Spark 2.4.1**.</span></span> <span data-ttu-id="9f857-212">Затем выберите **Дополнительные параметры** > **Скрипты инициализации**.</span><span class="sxs-lookup"><span data-stu-id="9f857-212">Then, select **Advanced Options** > **Init Scripts**.</span></span> <span data-ttu-id="9f857-213">Введите следующий путь к скрипту инициализации: `dbfs:/spark-dotnet/db-init.sh`.</span><span class="sxs-lookup"><span data-stu-id="9f857-213">Set Init Script Path as `dbfs:/spark-dotnet/db-init.sh`.</span></span>

   ![Настройка кластера Spark в Azure Databricks](./media/databricks-deployment/cluster-config.png)

3. <span data-ttu-id="9f857-215">Выберите **Подтвердить**, чтобы подтвердить параметры кластера.</span><span class="sxs-lookup"><span data-stu-id="9f857-215">Select **Confirm** to confirm your cluster settings.</span></span>

## <a name="run-your-app"></a><span data-ttu-id="9f857-216">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="9f857-216">Run your app</span></span>

1. <span data-ttu-id="9f857-217">Перейдите к своему заданию и выберите **Запустить сейчас**, чтобы запустить задание в только что настроенном кластере Spark.</span><span class="sxs-lookup"><span data-stu-id="9f857-217">Navigate to your job and select **Run Now** to run your job on your newly configured Spark cluster.</span></span>

2. <span data-ttu-id="9f857-218">Создание кластера задания может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="9f857-218">It takes a few minutes for the job's cluster to create.</span></span> <span data-ttu-id="9f857-219">После создания задание будет отправлено, и вы сможете просмотреть выходные данные.</span><span class="sxs-lookup"><span data-stu-id="9f857-219">Once it is created, your job will be submitted, and you can view the output.</span></span>

3. <span data-ttu-id="9f857-220">Выберите **Кластеры** в меню слева, а затем имя и выполнение задания.</span><span class="sxs-lookup"><span data-stu-id="9f857-220">Select **Clusters** from the left menu, and then the name and run of your job.</span></span>

4. <span data-ttu-id="9f857-221">Выберите **Журналы драйверов**, чтобы просмотреть выходные данные задания.</span><span class="sxs-lookup"><span data-stu-id="9f857-221">Select **Driver Logs** to view the output of your job.</span></span> <span data-ttu-id="9f857-222">После выполнения приложения отображается та же таблица подсчета слов из локального запуска начального приложения, записанная на консоль стандартного потока вывода.</span><span class="sxs-lookup"><span data-stu-id="9f857-222">When your app finishes executing, you see the same word count table from the getting started local run written to the standard output console.</span></span>

   ![Таблица выходных данных задания Azure Databricks](./media/databricks-deployment/table-output.png)

   <span data-ttu-id="9f857-224">Поздравляем, вы запустили свое первое приложение .NET для Apache Spark в облаке!</span><span class="sxs-lookup"><span data-stu-id="9f857-224">Congratulations, you've run your first .NET for Apache Spark application in the cloud!</span></span>

## <a name="clean-up-resources"></a><span data-ttu-id="9f857-225">Очистка ресурсов</span><span class="sxs-lookup"><span data-stu-id="9f857-225">Clean up resources</span></span>

<span data-ttu-id="9f857-226">Если рабочая область Databricks больше не нужна, можно удалить ресурс Azure Databricks на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="9f857-226">If you no longer need the Databricks workspace, you can delete your Azure Databricks resource in the Azure portal.</span></span> <span data-ttu-id="9f857-227">Кроме того, можно выбрать имя группы ресурсов, чтобы открыть страницу группы ресурсов, а затем щелкнуть **Удалить группу ресурсов**.</span><span class="sxs-lookup"><span data-stu-id="9f857-227">You can also select the resource group name to open the resource group page, and then select **Delete resource group**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9f857-228">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="9f857-228">Next steps</span></span>

<span data-ttu-id="9f857-229">В этом руководстве вы развернули приложение .NET для Apache Spark в Databricks.</span><span class="sxs-lookup"><span data-stu-id="9f857-229">In this tutorial, you deployed your .NET for Apache Spark application to Databricks.</span></span> <span data-ttu-id="9f857-230">Дополнительные сведения о Databricks см. в документации по Azure Databricks.</span><span class="sxs-lookup"><span data-stu-id="9f857-230">To learn more about Databricks, continue to the Azure Databricks Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9f857-231">Документация по Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="9f857-231">Azure Databricks Documentation</span></span>](https://docs.microsoft.com/azure/azure-databricks/)
