---
title: Развертывание приложения .NET для Apache Spark в Azure HDInsight
description: Узнайте, как развернуть приложение .NET для Apache Spark в HDInsight.
ms.date: 01/23/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 77b57463375c36444532bdd383ec4b3bfe3ab056
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "77504163"
---
# <a name="tutorial-deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a><span data-ttu-id="7499c-103">Учебник. Развертывание приложения .NET для Apache Spark в Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="7499c-103">Tutorial: Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>

<span data-ttu-id="7499c-104">В этом учебнике описывается развертывание приложения .NET для Apache Spark в облаке с помощью кластера Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="7499c-104">This tutorial teaches you how to deploy your .NET for Apache Spark app to the cloud through an Azure HDInsight cluster.</span></span> <span data-ttu-id="7499c-105">HDInsight упрощает создание и настройку кластера Spark в Azure, так как кластеры Spark в HDInsight совместимы со службой хранилища Azure и Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="7499c-105">HDInsight makes it easier to create and configure a Spark cluster in Azure since Spark clusters in HDInsight are compatible with Azure Storage and Azure Data Lake Storage.</span></span>

<span data-ttu-id="7499c-106">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="7499c-106">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="7499c-107">Получить доступ к учетным записям хранения с помощью Обозревателя службы хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="7499c-107">Access your storage accounts using Azure Storage Explorer.</span></span>
> * <span data-ttu-id="7499c-108">Создать кластер Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="7499c-108">Create an Azure HDInsight cluster.</span></span>
> * <span data-ttu-id="7499c-109">Опубликовать приложение .NET для Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="7499c-109">Publish your .NET for Apache Spark app.</span></span>
> * <span data-ttu-id="7499c-110">Создать и запустить действие скрипта HDInsight.</span><span class="sxs-lookup"><span data-stu-id="7499c-110">Create and run an HDInsight script action.</span></span>
> * <span data-ttu-id="7499c-111">Запустить приложение .NET для Apache Spark в кластере HDInsight.</span><span class="sxs-lookup"><span data-stu-id="7499c-111">Run a .NET for Apache Spark app on an HDInsight cluster.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7499c-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="7499c-112">Prerequisites</span></span>

<span data-ttu-id="7499c-113">Прежде чем начать, сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="7499c-113">Before you start, do the following tasks:</span></span>

* <span data-ttu-id="7499c-114">Если у вас еще нет подписки Azure, создайте [бесплатную учетную запись Azure](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="7499c-114">If you don't have an Azure subscription, create a [free account](https://azure.microsoft.com/free/).</span></span>
* <span data-ttu-id="7499c-115">Войдите на [портале Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="7499c-115">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
* <span data-ttu-id="7499c-116">Установите Обозреватель службы хранилища Azure на [Windows](https://go.microsoft.com/fwlink/?LinkId=708343&clcid=0x409), [Linux](https://go.microsoft.com/fwlink/?LinkId=722418&clcid=0x409) или [компьютере MacOS](https://go.microsoft.com/fwlink/?LinkId=708342&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="7499c-116">Install Azure Storage Explorer on your [Windows](https://go.microsoft.com/fwlink/?LinkId=708343&clcid=0x409), [Linux](https://go.microsoft.com/fwlink/?LinkId=722418&clcid=0x409), or [MacOS](https://go.microsoft.com/fwlink/?LinkId=708342&clcid=0x409) computer.</span></span>
* <span data-ttu-id="7499c-117">Пройдите учебник [.NET для Apache Spark — начало работы за 10 минут](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro).</span><span class="sxs-lookup"><span data-stu-id="7499c-117">Complete the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial.</span></span>

## <a name="access-your-storage-accounts"></a><span data-ttu-id="7499c-118">Доступ к учетным записям хранения</span><span class="sxs-lookup"><span data-stu-id="7499c-118">Access your storage accounts</span></span>

1. <span data-ttu-id="7499c-119">Откройте обозреватель службы хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="7499c-119">Open Azure Storage Explorer.</span></span>

2. <span data-ttu-id="7499c-120">Выберите **Добавить учетную запись** в меню слева и войдите в учетную запись Azure.</span><span class="sxs-lookup"><span data-stu-id="7499c-120">Select **Add Account** on the left menu, and sign in to your Azure account.</span></span>

    ![Вход в учетную запись Azure из Обозревателя службы хранилища](./media/hdinsight-deployment/signin-azure-storage-explorer.png)

   <span data-ttu-id="7499c-122">После входа в систему должны отобразиться все учетные записи хранения, а также все ресурсы, отправленные в учетные записи хранения.</span><span class="sxs-lookup"><span data-stu-id="7499c-122">After you sign in, you should see all storage accounts you have and any resources you have uploaded to your storage accounts.</span></span>

## <a name="create-an-hdinsight-cluster"></a><span data-ttu-id="7499c-123">Создание кластера HDInsight</span><span class="sxs-lookup"><span data-stu-id="7499c-123">Create an HDInsight cluster</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7499c-124">Счета за кластеры HDInsight выставляются пропорционально за минуту, даже если вы их не используете.</span><span class="sxs-lookup"><span data-stu-id="7499c-124">Billing for HDInsight clusters is prorated per minute, even if you're not using them.</span></span> <span data-ttu-id="7499c-125">Обязательно удалите кластер, когда завершите его использование.</span><span class="sxs-lookup"><span data-stu-id="7499c-125">Be sure to delete your cluster after you have finished using it.</span></span> <span data-ttu-id="7499c-126">Дополнительные сведения см. в разделе [Очистка ресурсов](#clean-up-resources) этого учебника.</span><span class="sxs-lookup"><span data-stu-id="7499c-126">For more information, see the [Clean up resources](#clean-up-resources) section of this tutorial.</span></span>

1. <span data-ttu-id="7499c-127">Войдите на [портал Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="7499c-127">Visit the [Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="7499c-128">Выберите действие **Создать ресурс**.</span><span class="sxs-lookup"><span data-stu-id="7499c-128">Select **+ Create a resource**.</span></span> <span data-ttu-id="7499c-129">Затем выберите **HDInsight** в категории **Аналитика**.</span><span class="sxs-lookup"><span data-stu-id="7499c-129">Then, select **HDInsight** from the **Analytics** category.</span></span>

    ![Создание ресурса HDInsight на портале Azure](./media/hdinsight-deployment/create-hdinsight-resource.png)

3. <span data-ttu-id="7499c-131">В разделе **Основные сведения** укажите следующие значения.</span><span class="sxs-lookup"><span data-stu-id="7499c-131">Under **Basics**, provide the following values:</span></span>

    |<span data-ttu-id="7499c-132">Свойство.</span><span class="sxs-lookup"><span data-stu-id="7499c-132">Property</span></span>  |<span data-ttu-id="7499c-133">Описание</span><span class="sxs-lookup"><span data-stu-id="7499c-133">Description</span></span>  |
    |---------|---------|
    |<span data-ttu-id="7499c-134">Подписка</span><span class="sxs-lookup"><span data-stu-id="7499c-134">Subscription</span></span>  | <span data-ttu-id="7499c-135">В раскрывающемся списке выберите одну из активных подписок Azure.</span><span class="sxs-lookup"><span data-stu-id="7499c-135">From the drop-down, choose one of your active Azure subscriptions.</span></span> |
    |<span data-ttu-id="7499c-136">Группа ресурсов</span><span class="sxs-lookup"><span data-stu-id="7499c-136">Resource group</span></span> | <span data-ttu-id="7499c-137">Укажите, следует ли создать новую группу ресурсов или использовать имеющуюся.</span><span class="sxs-lookup"><span data-stu-id="7499c-137">Specify whether you want to create a new resource group or use an existing one.</span></span> <span data-ttu-id="7499c-138">Группа ресурсов — это контейнер, содержащий связанные ресурсы для решения Azure.</span><span class="sxs-lookup"><span data-stu-id="7499c-138">A resource group is a container that holds related resources for an Azure solution.</span></span> |
    |<span data-ttu-id="7499c-139">Имя кластера</span><span class="sxs-lookup"><span data-stu-id="7499c-139">Cluster name</span></span> | <span data-ttu-id="7499c-140">Введите имя кластера Spark в HDInsight.</span><span class="sxs-lookup"><span data-stu-id="7499c-140">Give a name to your HDInsight Spark cluster.</span></span>|
    |<span data-ttu-id="7499c-141">Местоположение</span><span class="sxs-lookup"><span data-stu-id="7499c-141">Location</span></span>   | <span data-ttu-id="7499c-142">Выберите расположение группы ресурсов.</span><span class="sxs-lookup"><span data-stu-id="7499c-142">Select a location for the resource group.</span></span> <span data-ttu-id="7499c-143">В шаблоне используется это расположение для создания кластера и его хранения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7499c-143">The template uses this location for creating the cluster as well as for the default cluster storage.</span></span> |
    |<span data-ttu-id="7499c-144">Тип кластера</span><span class="sxs-lookup"><span data-stu-id="7499c-144">Cluster type</span></span>| <span data-ttu-id="7499c-145">Выберите **spark** в качестве типа кластера.</span><span class="sxs-lookup"><span data-stu-id="7499c-145">Select **Spark** as the cluster type.</span></span>|
    |<span data-ttu-id="7499c-146">Cluster version</span><span class="sxs-lookup"><span data-stu-id="7499c-146">Cluster version</span></span>|<span data-ttu-id="7499c-147">Это поле будет автоматически заполнено версией по умолчанию после выбора типа кластера.</span><span class="sxs-lookup"><span data-stu-id="7499c-147">This field will autopopulate with the default version once the cluster type has been selected.</span></span> <span data-ttu-id="7499c-148">Выберите версию Spark 2.3 или 2.4.</span><span class="sxs-lookup"><span data-stu-id="7499c-148">Select a 2.3 or 2.4 version of Spark.</span></span>|
    |<span data-ttu-id="7499c-149">Имя пользователя для входа в кластер</span><span class="sxs-lookup"><span data-stu-id="7499c-149">Cluster login username</span></span>| <span data-ttu-id="7499c-150">Введите имя пользователя для входа в кластер.</span><span class="sxs-lookup"><span data-stu-id="7499c-150">Enter the cluster login username.</span></span>  <span data-ttu-id="7499c-151">Имя по умолчанию — *admin*.</span><span class="sxs-lookup"><span data-stu-id="7499c-151">The default name is *admin*.</span></span> |
    |<span data-ttu-id="7499c-152">Пароль для входа в кластер</span><span class="sxs-lookup"><span data-stu-id="7499c-152">Cluster login password</span></span>| <span data-ttu-id="7499c-153">Введите пароль для входа.</span><span class="sxs-lookup"><span data-stu-id="7499c-153">Enter any login password.</span></span> |
    |<span data-ttu-id="7499c-154">Имя пользователя для Secure Shell (SSH)</span><span class="sxs-lookup"><span data-stu-id="7499c-154">Secure Shell (SSH) username</span></span>| <span data-ttu-id="7499c-155">Введите имя пользователя SSH.</span><span class="sxs-lookup"><span data-stu-id="7499c-155">Enter the SSH username.</span></span> <span data-ttu-id="7499c-156">По умолчанию эта учетная запись использует тот же пароль, что и учетная запись *для входа в кластер*.</span><span class="sxs-lookup"><span data-stu-id="7499c-156">By default, this account shares the same password as the *Cluster Login username* account.</span></span> |

4. <span data-ttu-id="7499c-157">По завершении выберите **Next: Storage >>** (Далее: хранилище), чтобы перейти на страницу **Хранилище**.</span><span class="sxs-lookup"><span data-stu-id="7499c-157">Select **Next: Storage >>** to continue to the **Storage** page.</span></span> <span data-ttu-id="7499c-158">На странице **Хранилище** укажите следующие значения.</span><span class="sxs-lookup"><span data-stu-id="7499c-158">Under **Storage**, provide the following values:</span></span>

    |<span data-ttu-id="7499c-159">Свойство.</span><span class="sxs-lookup"><span data-stu-id="7499c-159">Property</span></span>  |<span data-ttu-id="7499c-160">Описание</span><span class="sxs-lookup"><span data-stu-id="7499c-160">Description</span></span>  |
    |---------|---------|
    |<span data-ttu-id="7499c-161">Тип первичного хранилища</span><span class="sxs-lookup"><span data-stu-id="7499c-161">Primary storage type</span></span>|<span data-ttu-id="7499c-162">Используйте значение **службы хранилища Azure** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7499c-162">Use the default value **Azure Storage**.</span></span>|
    |<span data-ttu-id="7499c-163">Метод выбора</span><span class="sxs-lookup"><span data-stu-id="7499c-163">Selection method</span></span>|<span data-ttu-id="7499c-164">Используйте значение **Выбрать в списке** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7499c-164">Use the default value **Select from list**.</span></span>|
    |<span data-ttu-id="7499c-165">Основную учетную запись хранения</span><span class="sxs-lookup"><span data-stu-id="7499c-165">Primary storage account</span></span>|<span data-ttu-id="7499c-166">Выберите подписку и одну из активных учетных записей хранения в этой подписке.</span><span class="sxs-lookup"><span data-stu-id="7499c-166">Choose your subscription and one of your active storage accounts within that subscription.</span></span>|
    |<span data-ttu-id="7499c-167">Контейнер</span><span class="sxs-lookup"><span data-stu-id="7499c-167">Container</span></span>|<span data-ttu-id="7499c-168">Этот контейнер является конкретным контейнером больших двоичных объектов в вашей учетной записи хранения, где кластер ищет файлы для запуска приложения в облаке.</span><span class="sxs-lookup"><span data-stu-id="7499c-168">This container is the specific blob container in your storage account where your cluster looks for files to run your app in the cloud.</span></span> <span data-ttu-id="7499c-169">Можно присвоить ему любое доступное имя.</span><span class="sxs-lookup"><span data-stu-id="7499c-169">You can give it any available name.</span></span>|

5. <span data-ttu-id="7499c-170">В разделе **Просмотр и создание** выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7499c-170">Under **Review + create**, select **Create**.</span></span> <span data-ttu-id="7499c-171">Процесс создания кластеров занимает около 20 минут.</span><span class="sxs-lookup"><span data-stu-id="7499c-171">It takes about 20 minutes to create the cluster.</span></span> <span data-ttu-id="7499c-172">Прежде чем перейти к следующему шагу, вы должны создать кластер.</span><span class="sxs-lookup"><span data-stu-id="7499c-172">The cluster must be created before you can continue to the next step.</span></span>

## <a name="publish-your-app"></a><span data-ttu-id="7499c-173">Публикация приложения</span><span class="sxs-lookup"><span data-stu-id="7499c-173">Publish your app</span></span>

<span data-ttu-id="7499c-174">Затем вы публикуете приложение *mySparkApp*, созданное в учебнике [.NET для Apache Spark — начало работы за 10 минут](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro), чтобы кластер Spark получил доступ ко всем файлам, которые необходимы для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="7499c-174">Next, you publish the *mySparkApp* created in the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial, which gives your Spark cluster access to all the files it needs to run your app.</span></span>

1. <span data-ttu-id="7499c-175">Для публикации *mySparkApp* выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="7499c-175">Run the following commands to publish the *mySparkApp*:</span></span>

   <span data-ttu-id="7499c-176">**В Windows:**</span><span class="sxs-lookup"><span data-stu-id="7499c-176">**On Windows:**</span></span>

   ```dotnetcli
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

   <span data-ttu-id="7499c-177">**В Linux:**</span><span class="sxs-lookup"><span data-stu-id="7499c-177">**On Linux:**</span></span>

   ```bash
   cd mySparkApp
   foo@bar:~/path/to/app$ dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

2. <span data-ttu-id="7499c-178">Выполните следующие задачи и заархивируйте опубликованные файлы приложения, чтобы их можно было легко передать в кластер HDInsight.</span><span class="sxs-lookup"><span data-stu-id="7499c-178">Do the following tasks to zip your published app files so that you can easily upload them to your HDInsight cluster.</span></span>

   <span data-ttu-id="7499c-179">**В Windows:**</span><span class="sxs-lookup"><span data-stu-id="7499c-179">**On Windows:**</span></span>

   <span data-ttu-id="7499c-180">Перейдите в каталог *mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64*.</span><span class="sxs-lookup"><span data-stu-id="7499c-180">Navigate to *mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64*.</span></span> <span data-ttu-id="7499c-181">Затем щелкните правой кнопкой мыши папку **Publish** и выберите **Отправить > Сжатая ZIP-папка**.</span><span class="sxs-lookup"><span data-stu-id="7499c-181">Then, right-click on **Publish** folder and select **Send to > Compressed (zipped) folder**.</span></span> <span data-ttu-id="7499c-182">Назовите папку **publish.zip**.</span><span class="sxs-lookup"><span data-stu-id="7499c-182">Name the new folder **publish.zip**.</span></span>

   <span data-ttu-id="7499c-183">**В Linux выполните следующую команду:**</span><span class="sxs-lookup"><span data-stu-id="7499c-183">**On Linux, run the following command:**</span></span>

   ```bash
   zip -r publish.zip
   ```

## <a name="upload-files-to-azure"></a><span data-ttu-id="7499c-184">Отправка файлов в Azure</span><span class="sxs-lookup"><span data-stu-id="7499c-184">Upload files to Azure</span></span>

<span data-ttu-id="7499c-185">Затем используйте Обозреватель службы хранилища Azure, чтобы передать следующие пять файлов в контейнер больших двоичных объектов, выбранный для системы хранения данных кластера:</span><span class="sxs-lookup"><span data-stu-id="7499c-185">Next, you use the Azure Storage Explorer to upload the following five files to the blob container you chose for your cluster's storage:</span></span>

* <span data-ttu-id="7499c-186">Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="7499c-186">Microsoft.Spark.Worker</span></span>
* <span data-ttu-id="7499c-187">install-worker.sh</span><span class="sxs-lookup"><span data-stu-id="7499c-187">install-worker.sh</span></span>
* <span data-ttu-id="7499c-188">publish.zip</span><span class="sxs-lookup"><span data-stu-id="7499c-188">publish.zip</span></span>
* <span data-ttu-id="7499c-189">microsoft-spark-2.3.x-0.3.0.jar</span><span class="sxs-lookup"><span data-stu-id="7499c-189">microsoft-spark-2.3.x-0.3.0.jar</span></span>
* <span data-ttu-id="7499c-190">input.txt.</span><span class="sxs-lookup"><span data-stu-id="7499c-190">input.txt.</span></span>

1. <span data-ttu-id="7499c-191">Откройте Обозреватель службы хранилища Azure и перейдите к своей учетной записи хранения в меню слева.</span><span class="sxs-lookup"><span data-stu-id="7499c-191">Open Azure Storage Explorer and navigate to your storage account from the left menu.</span></span> <span data-ttu-id="7499c-192">Выполните детализацию до контейнера больших двоичных объектов для кластера в разделе **Контейнеры больших двоичных объектов** в вашей учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="7499c-192">Drill down to the blob container for your cluster under **Blob Containers** in your storage account.</span></span>

2. <span data-ttu-id="7499c-193">*Microsoft.Spark.Worker* помогает Apache Spark запускать ваше приложение, например пользовательские функции (UDF), которые вы написали.</span><span class="sxs-lookup"><span data-stu-id="7499c-193">*Microsoft.Spark.Worker* helps Apache Spark execute your app, such as any user-defined functions (UDFs) you may have written.</span></span> <span data-ttu-id="7499c-194">Загрузите [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v0.3.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.3.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="7499c-194">Download [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v0.3.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.3.0.tar.gz).</span></span> <span data-ttu-id="7499c-195">Затем выберите **Отправить** в Обозревателе службы хранилища Azure, чтобы отправить рабочую роль.</span><span class="sxs-lookup"><span data-stu-id="7499c-195">Then, select **Upload** in Azure Storage Explorer to upload the worker.</span></span>

   ![Отправка файлов в Обозреватель службы хранилища Azure](./media/hdinsight-deployment/upload-files-to-storage.png)

3. <span data-ttu-id="7499c-197">*install-worker.sh* — это скрипт, который позволяет копировать зависимые файлы .NET для Apache Spark в узлы кластера.</span><span class="sxs-lookup"><span data-stu-id="7499c-197">The *install-worker.sh* is a script that lets you copy .NET for Apache Spark dependent files into the nodes of your cluster.</span></span>

   <span data-ttu-id="7499c-198">Создайте новый файл с именем **install-worker.sh** на локальном компьютере и вставьте [содержимое файла install-worker.sh](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh), расположенного на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="7499c-198">Create a new file named **install-worker.sh** your local computer, and paste the [install-worker.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) located on GitHub.</span></span> <span data-ttu-id="7499c-199">Затем отправьте *install-worker.sh* в контейнер больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="7499c-199">Then, upload *install-worker.sh* to your blob container.</span></span>

4. <span data-ttu-id="7499c-200">Кластеру требуется файл publish.zip, содержащий опубликованные файлы приложения.</span><span class="sxs-lookup"><span data-stu-id="7499c-200">Your cluster needs the publish.zip file that contains your app's published files.</span></span> <span data-ttu-id="7499c-201">Перейдите к опубликованной папке **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64** и найдите **publish.zip**.</span><span class="sxs-lookup"><span data-stu-id="7499c-201">Navigate to your published folder, **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64**, and locate **publish.zip**.</span></span> <span data-ttu-id="7499c-202">Затем отправьте файл *publish.zip* в контейнер больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="7499c-202">Then upload *publish.zip* to your blob container.</span></span>

5. <span data-ttu-id="7499c-203">Кластеру требуется код приложения, упакованный в JAR-файл.</span><span class="sxs-lookup"><span data-stu-id="7499c-203">Your cluster needs the application code that was packaged into a jar file.</span></span> <span data-ttu-id="7499c-204">Перейдите к опубликованной папке **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64** и найдите **microsoft-spark-2.3.x-0.3.0.jar**.</span><span class="sxs-lookup"><span data-stu-id="7499c-204">Navigate to your published folder, **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64**, and locate **microsoft-spark-2.3.x-0.3.0.jar**.</span></span> <span data-ttu-id="7499c-205">Затем отправьте JAR-файл в контейнер больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="7499c-205">Then, upload the jar file to your blob container.</span></span>

   <span data-ttu-id="7499c-206">Там может быть несколько JAR-файлов (для версий Spark 2.3.x и 2.4.x).</span><span class="sxs-lookup"><span data-stu-id="7499c-206">There may be multiple .jar files (for versions 2.3.x and 2.4.x of Spark).</span></span> <span data-ttu-id="7499c-207">Необходимо выбрать JAR-файл, соответствующий версии Spark, выбранной при создании кластера.</span><span class="sxs-lookup"><span data-stu-id="7499c-207">You need to choose the .jar file that matches the version of Spark you chose during cluster creation.</span></span> <span data-ttu-id="7499c-208">Например, выберите *microsoft-spark-2.3.x-0.3.0.jar*, если вы выбрали Spark 2.3.2 во время создания кластера.</span><span class="sxs-lookup"><span data-stu-id="7499c-208">For example, choose *microsoft-spark-2.3.x-0.3.0.jar* if you chose Spark 2.3.2 during cluster creation.</span></span>

6. <span data-ttu-id="7499c-209">Кластеру требуются входные данные для приложения.</span><span class="sxs-lookup"><span data-stu-id="7499c-209">Your cluster needs the input to your app.</span></span> <span data-ttu-id="7499c-210">Перейдите в каталог **mySparkApp** и найдите файл **input.txt**.</span><span class="sxs-lookup"><span data-stu-id="7499c-210">Navigate to your **mySparkApp** directory and locate **input.txt**.</span></span> <span data-ttu-id="7499c-211">Отправьте входной файл в каталог **user/sshuser** в контейнере больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="7499c-211">Upload your input file to the **user/sshuser** directory in your blob container.</span></span> <span data-ttu-id="7499c-212">Вы будете подключаться к кластеру по протоколу SSH, и в этой папке кластер будет искать входные данные.</span><span class="sxs-lookup"><span data-stu-id="7499c-212">You will be connecting to your cluster through ssh, and this folder is where your cluster looks for its input.</span></span> <span data-ttu-id="7499c-213">Файл *input.txt* — это единственный файл, отправленный в конкретный каталог.</span><span class="sxs-lookup"><span data-stu-id="7499c-213">The *input.txt* file is the only file uploaded to a specific directory.</span></span>

## <a name="run-the-hdinsight-script-action"></a><span data-ttu-id="7499c-214">Выполнения действия скрипта HDInsight</span><span class="sxs-lookup"><span data-stu-id="7499c-214">Run the HDInsight script action</span></span>

<span data-ttu-id="7499c-215">После запуска кластера и отправки файлов в Azure вы запускаете скрипт **install-worker.sh** в кластере.</span><span class="sxs-lookup"><span data-stu-id="7499c-215">Once your cluster is running and you've uploaded your files to Azure, you run the **install-worker.sh** script on the cluster.</span></span>

1. <span data-ttu-id="7499c-216">Перейдите к кластеру HDInsight Spark на портале Azure и выберите **Действия скрипта**.</span><span class="sxs-lookup"><span data-stu-id="7499c-216">Navigate to your HDInsight Spark cluster in Azure portal, and then select **Script actions**.</span></span>

2. <span data-ttu-id="7499c-217">Выберите **+ Отправить новый** и укажите следующие значения.</span><span class="sxs-lookup"><span data-stu-id="7499c-217">Select **+ Submit new** and provide the following values:</span></span>

   |<span data-ttu-id="7499c-218">Свойство.</span><span class="sxs-lookup"><span data-stu-id="7499c-218">Property</span></span>  |<span data-ttu-id="7499c-219">Описание</span><span class="sxs-lookup"><span data-stu-id="7499c-219">Description</span></span>  |
   |---------|---------|
   | <span data-ttu-id="7499c-220">Тип скрипта</span><span class="sxs-lookup"><span data-stu-id="7499c-220">Script type</span></span> |<span data-ttu-id="7499c-221">Другой</span><span class="sxs-lookup"><span data-stu-id="7499c-221">Custom</span></span>|
   | <span data-ttu-id="7499c-222">name</span><span class="sxs-lookup"><span data-stu-id="7499c-222">Name</span></span> | <span data-ttu-id="7499c-223">Установка рабочей роли</span><span class="sxs-lookup"><span data-stu-id="7499c-223">Install Worker</span></span>|
   | <span data-ttu-id="7499c-224">URI bash-скрипта</span><span class="sxs-lookup"><span data-stu-id="7499c-224">Bash script URI</span></span> |https://mystorageaccount.blob.core.windows.net/mycontainer/install-worker.sh </br> <span data-ttu-id="7499c-225">Чтобы подтвердить этот URI, щелкните правой кнопкой мыши install-worker.sh в Обозреватель службы хранилища Azure и выберите пункт "Свойства".</span><span class="sxs-lookup"><span data-stu-id="7499c-225">To confirm this URI, right-click on install-worker.sh in Azure Storage Explorer and select Properties.</span></span> |
   | <span data-ttu-id="7499c-226">Типы узлов</span><span class="sxs-lookup"><span data-stu-id="7499c-226">Node type(s)</span></span>| <span data-ttu-id="7499c-227">Рабочий узел</span><span class="sxs-lookup"><span data-stu-id="7499c-227">Worker</span></span>|
   | <span data-ttu-id="7499c-228">Параметры</span><span class="sxs-lookup"><span data-stu-id="7499c-228">Parameters</span></span> | <span data-ttu-id="7499c-229">azure</span><span class="sxs-lookup"><span data-stu-id="7499c-229">azure</span></span> </br> wasbs://mycontainer@myStorageAccount.blob.core.windows.net/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz </br> <span data-ttu-id="7499c-230">/usr/local/bin</span><span class="sxs-lookup"><span data-stu-id="7499c-230">/usr/local/bin</span></span>

3. <span data-ttu-id="7499c-231">Выберите **Создать**, чтобы отправить скрипт.</span><span class="sxs-lookup"><span data-stu-id="7499c-231">Select **Create** to submit your script.</span></span>

## <a name="run-your-app"></a><span data-ttu-id="7499c-232">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="7499c-232">Run your app</span></span>

1. <span data-ttu-id="7499c-233">Перейдите к кластеру HDInsight Spark на портале Azure и выберите **SSH и вход в кластер**.</span><span class="sxs-lookup"><span data-stu-id="7499c-233">Navigate to your HDInsight Spark cluster in Azure portal, and then select **SSH + Cluster login**.</span></span>

2. <span data-ttu-id="7499c-234">Скопируйте данные для входа по протоколу SSH и вставьте имя для входа в терминал.</span><span class="sxs-lookup"><span data-stu-id="7499c-234">Copy the ssh login information and paste the login into a terminal.</span></span> <span data-ttu-id="7499c-235">Войдите в кластер, используя пароль, заданный во время создания кластера.</span><span class="sxs-lookup"><span data-stu-id="7499c-235">Sign in to your cluster using the password you set during cluster creation.</span></span> <span data-ttu-id="7499c-236">Вы должны увидеть сообщение с приветствием в Ubuntu и Spark.</span><span class="sxs-lookup"><span data-stu-id="7499c-236">You should see messages welcoming you to Ubuntu and Spark.</span></span>

3. <span data-ttu-id="7499c-237">Используйте команду **spark-submit**, чтобы запустить приложение в кластере HDInsight.</span><span class="sxs-lookup"><span data-stu-id="7499c-237">Use the **spark-submit** command to run your app on your HDInsight cluster.</span></span> <span data-ttu-id="7499c-238">Не забудьте заменить **mycontainer** и **mystorageaccount** в примере скрипта, указав фактические имена контейнера больших двоичных объектов и учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="7499c-238">Remember to replace **mycontainer** and **mystorageaccount** in the example script with the actual names of your blob container and storage account.</span></span>

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-2.3.x-0.6.0.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

   <span data-ttu-id="7499c-239">При запуске приложения отображается та же таблица подсчета слов из локального запуска начального приложения, записанная на консоль.</span><span class="sxs-lookup"><span data-stu-id="7499c-239">When your app runs, you see the same word count table from the getting started local run written to the console.</span></span> <span data-ttu-id="7499c-240">Поздравляем, вы запустили свое первое приложение .NET для Apache Spark в облаке!</span><span class="sxs-lookup"><span data-stu-id="7499c-240">Congratulations, you've run your first .NET for Apache Spark application in the cloud!</span></span>

## <a name="clean-up-resources"></a><span data-ttu-id="7499c-241">Очистка ресурсов</span><span class="sxs-lookup"><span data-stu-id="7499c-241">Clean up resources</span></span>

<span data-ttu-id="7499c-242">HDInsight сохраняет ваши данные в службе хранилища Azure, что позволяет безопасно удалить неиспользуемый кластер.</span><span class="sxs-lookup"><span data-stu-id="7499c-242">HDInsight saves your data in Azure Storage, so you can safely delete a cluster when it is not in use.</span></span> <span data-ttu-id="7499c-243">Плата за кластеры HDInsight взимается, даже когда они не используются.</span><span class="sxs-lookup"><span data-stu-id="7499c-243">You are also charged for an HDInsight cluster, even when it is not in use.</span></span> <span data-ttu-id="7499c-244">Поскольку стоимость кластера во много раз превышает стоимость хранилища, экономически целесообразно удалять неиспользуемые кластеры.</span><span class="sxs-lookup"><span data-stu-id="7499c-244">Since the charges for the cluster are many times more than the charges for storage, it makes economic sense to delete clusters when they are not in use.</span></span>

<span data-ttu-id="7499c-245">Кроме того, можно выбрать имя группы ресурсов, чтобы открыть страницу группы ресурсов, а затем щелкнуть **Удалить группу ресурсов**.</span><span class="sxs-lookup"><span data-stu-id="7499c-245">You can also select the resource group name to open the resource group page, and then select **Delete resource group**.</span></span> <span data-ttu-id="7499c-246">Вместе с группой ресурсов вы также удалите кластер Spark в HDInsight и учетную запись хранения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7499c-246">By deleting the resource group, you delete both the HDInsight Spark cluster, and the default storage account.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7499c-247">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="7499c-247">Next steps</span></span>

<span data-ttu-id="7499c-248">В этом руководстве вы развернули приложение .NET для Apache Spark в Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="7499c-248">In this tutorial, you deployed your .NET for Apache Spark application to Azure HDInsight.</span></span> <span data-ttu-id="7499c-249">Дополнительные сведения об HDInsight см. в документации по Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="7499c-249">To learn more about HDInsight, continue to the Azure HDInsight Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7499c-250">Документация по Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="7499c-250">Azure HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)
