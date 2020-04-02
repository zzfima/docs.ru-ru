---
title: Установка .NET для Apache Spark в записных книжках Jupyter в кластерах Spark Azure HDInsight
description: Узнайте, как установить .NET для Apache Spark в записных книжках Jupyter Notebook Azure HDInsight.
ms.date: 03/13/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 32047efcde093a3752bdd59baa88896d1547b93e
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546754"
---
# <a name="install-net-for-apache-spark-on-jupyter-notebooks-on-azure-hdinsight-spark-clusters"></a><span data-ttu-id="123ca-103">Установка .NET для Apache Spark в записных книжках Jupyter в кластерах Spark Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="123ca-103">Install .NET for Apache Spark on Jupyter notebooks on Azure HDInsight Spark clusters</span></span>

<span data-ttu-id="123ca-104">В этой статье описывается, как установить .NET для Apache Spark в записных книжках Jupyter в кластерах Spark Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="123ca-104">This article teaches you how to install .NET for Apache Spark on Jupyter notebooks on Azure HDInsight Spark clusters.</span></span> <span data-ttu-id="123ca-105">Вы можете развернуть .NET для Apache Spark в кластерах Azure HDInsight с помощью командной строки и портала Azure (дополнительные сведения см. в статье [Учебник. Развертывание приложения .NET для Apache Spark в Azure HDInsight](../tutorials/hdinsight-deployment.md)). Обратите внимание, что записные книжки предоставляют более интерактивный и итеративный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="123ca-105">You can deploy .NET for Apache Spark on Azure HDInsight clusters through a combination of the command line and the Azure portal (for more information, see [how to deploy a .NET for Apache Spark application to Azure HDInsight](../tutorials/hdinsight-deployment.md)), but notebooks provide a more interactive and iterative experience.</span></span>

<span data-ttu-id="123ca-106">Кластеры Azure HDInsight поставляются с записными книжками Jupyter, поэтому вам нужно лишь настроить их для запуска .NET для Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="123ca-106">Azure HDInsight clusters already come with Jupyter notebooks, so all you have to do is configure the Jupyter notebooks to run .NET for Apache Spark.</span></span> <span data-ttu-id="123ca-107">Чтобы использовать .NET для Apache Spark в записных книжках Jupyter, необходимо иметь C# REPL, чтобы построчно выполнить код C# и при необходимости сохранить состояние выполнения.</span><span class="sxs-lookup"><span data-stu-id="123ca-107">To use .NET for Apache Spark in your Jupyter notebooks, a C# REPL is needed to execute your C# code line-by-line and to preserve execution state when necessary.</span></span> <span data-ttu-id="123ca-108">Средство [Try .NET](https://github.com/dotnet/try) интегрировано в качестве официальной версии .NET REPL.</span><span class="sxs-lookup"><span data-stu-id="123ca-108">[Try .NET](https://github.com/dotnet/try) has been integrated as the official .NET REPL.</span></span>

<span data-ttu-id="123ca-109">Чтобы включить .NET для Apache Spark через интерфейс записных книжек Jupyter Notebook, необходимо выполнить несколько действий вручную с помощью [Ambari](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-manage-ambari) и отправить [действия скрипта](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux) в кластере HDInsight Spark.</span><span class="sxs-lookup"><span data-stu-id="123ca-109">To enable .NET for Apache Spark through the Jupyter Notebooks experience, you need to follow a few manual steps through [Ambari](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-manage-ambari) and submit [script actions](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux) on the HDInsight Spark cluster.</span></span>

> [!NOTE]
> <span data-ttu-id="123ca-110">Эта *экспериментальная* функция, и она не поддерживается командой HDInsight Spark.</span><span class="sxs-lookup"><span data-stu-id="123ca-110">This feature is *experimental* and is not supported by the HDInsight Spark team.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="123ca-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="123ca-111">Prerequisites</span></span>

<span data-ttu-id="123ca-112">Создайте кластер [Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-jupyter-spark-sql-use-portal#create-an-hdinsight-spark-cluster), если его у вас еще нет.</span><span class="sxs-lookup"><span data-stu-id="123ca-112">If you don't already have one, create an [Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-jupyter-spark-sql-use-portal#create-an-hdinsight-spark-cluster) cluster.</span></span>

1. <span data-ttu-id="123ca-113">Перейдите на [портал Azure](https://portal.azure.com) и выберите **Создать ресурс**.</span><span class="sxs-lookup"><span data-stu-id="123ca-113">Visit the [Azure portal](https://portal.azure.com) and select **+ Create a Resource**.</span></span>

1. <span data-ttu-id="123ca-114">Создайте ресурс кластера Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="123ca-114">Create a new Azure HDInsight cluster resource.</span></span> <span data-ttu-id="123ca-115">Во время создания кластера выберите **Spark 2.4** и **HDI 4.0**.</span><span class="sxs-lookup"><span data-stu-id="123ca-115">Select **Spark 2.4** and **HDI 4.0** during cluster creation.</span></span>

## <a name="install-net-for-apache-spark"></a><span data-ttu-id="123ca-116">Установка .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="123ca-116">Install .NET for Apache Spark</span></span>

<span data-ttu-id="123ca-117">На портале Azure выберите **кластер HDInsight Spark**, созданный на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="123ca-117">In the Azure portal, select the **HDInsight Spark cluster** you created in the previous step.</span></span>

### <a name="stop-the-livy-server"></a><span data-ttu-id="123ca-118">Остановка работы сервера Livy</span><span class="sxs-lookup"><span data-stu-id="123ca-118">Stop the Livy server</span></span>

1. <span data-ttu-id="123ca-119">На портале щелкните **Обзор**, а затем выберите **Домашняя страница Ambari**.</span><span class="sxs-lookup"><span data-stu-id="123ca-119">From the portal, select **Overview**, and then select **Ambari home**.</span></span> <span data-ttu-id="123ca-120">При появлении запроса введите учетные данные для входа в кластер.</span><span class="sxs-lookup"><span data-stu-id="123ca-120">If prompted, enter the login credentials for the cluster.</span></span>

   ![Остановка работы сервера Livy](./media/hdinsight-notebook-installation/select-ambari.png)

2. <span data-ttu-id="123ca-122">Выберите **Spark2** в меню навигации слева, а затем — **LIVY FOR SPARK2 SERVER** (LIVY для сервера SPARK2).</span><span class="sxs-lookup"><span data-stu-id="123ca-122">Select **Spark2** from the left navigation menu, and select **LIVY FOR SPARK2 SERVER**.</span></span>

   ![Остановка работы сервера Livy](./media/hdinsight-notebook-installation/select-livyserver.png)

3. <span data-ttu-id="123ca-124">Выберите узел **hn0…**</span><span class="sxs-lookup"><span data-stu-id="123ca-124">Select **hn0... host**.</span></span>

   ![Остановка работы сервера Livy](./media/hdinsight-notebook-installation/select-host.png)

4. <span data-ttu-id="123ca-126">Щелкните многоточие рядом с **Livy for Spark2 Server** (Сервер Livy для Spark2), а затем выберите **Остановить**.</span><span class="sxs-lookup"><span data-stu-id="123ca-126">Select the ellipsis next to **Livy for Spark2 Server** and select **Stop**.</span></span> <span data-ttu-id="123ca-127">При появлении запроса щелкните **ОК**, чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="123ca-127">When prompted, select **OK** to proceed.</span></span>

   <span data-ttu-id="123ca-128">Остановка работы сервера Livy для Spark2.</span><span class="sxs-lookup"><span data-stu-id="123ca-128">Stop Livy for Spark2 Server.</span></span>
   <span data-ttu-id="123ca-129">![Остановка работы сервера Livy](./media/hdinsight-notebook-installation/stop-server.png)</span><span class="sxs-lookup"><span data-stu-id="123ca-129">![Stop Livy Server](./media/hdinsight-notebook-installation/stop-server.png)</span></span>

5. <span data-ttu-id="123ca-130">Повторите предыдущие шаги для узла **hn1…**</span><span class="sxs-lookup"><span data-stu-id="123ca-130">Repeat the previous steps for **hn1... host**.</span></span>

### <a name="submit-an-hdinsight-script-action"></a><span data-ttu-id="123ca-131">Отправка действия скрипта HDInsight</span><span class="sxs-lookup"><span data-stu-id="123ca-131">Submit an HDInsight script action</span></span>

1. <span data-ttu-id="123ca-132">`install-interactive-notebook.sh` — это скрипт, который устанавливает .NET для Apache Spark и вносит изменения в Apache Livy и Sparkmagic.</span><span class="sxs-lookup"><span data-stu-id="123ca-132">The `install-interactive-notebook.sh` is a script that installs .NET for Apache Spark and makes changes to Apache Livy and sparkmagic.</span></span> <span data-ttu-id="123ca-133">Прежде чем отправить действия скрипта в HDInsight, необходимо создать и отправить `install-interactive-notebook.sh`.</span><span class="sxs-lookup"><span data-stu-id="123ca-133">Before you submit a script action to HDInsight, you need to create and upload `install-interactive-notebook.sh`.</span></span>

   <span data-ttu-id="123ca-134">Создайте файл **install-interactive-notebook.sh** на локальном компьютере и вставьте содержимое [nstall-interactive-notebook.sh contentss](https://raw.githubusercontent.com/dotnet/spark/master/deployment/HDI-Spark/Notebooks/install-interactive-notebook.sh).</span><span class="sxs-lookup"><span data-stu-id="123ca-134">Create a new file named **install-interactive-notebook.sh** in your local computer and paste the contents of [install-interactive-notebook.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/HDI-Spark/Notebooks/install-interactive-notebook.sh).</span></span>

   <span data-ttu-id="123ca-135">Отправьте скрипт в [универсальный код ресурса (URI)](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux#understand-script-actions), который доступен из кластера HDInsight.</span><span class="sxs-lookup"><span data-stu-id="123ca-135">Upload the script to a [URI](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux#understand-script-actions) that's accessible from the HDInsight cluster.</span></span> <span data-ttu-id="123ca-136">Например, `https://<my storage account>.blob.core.windows.net/<my container>/<some dir>/install-interactive-notebook.sh`.</span><span class="sxs-lookup"><span data-stu-id="123ca-136">For example, `https://<my storage account>.blob.core.windows.net/<my container>/<some dir>/install-interactive-notebook.sh`.</span></span>

2. <span data-ttu-id="123ca-137">Выполните скрипт `install-interactive-notebook.sh` в кластере с помощью [действий скриптов HDInsight](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).</span><span class="sxs-lookup"><span data-stu-id="123ca-137">Run `install-interactive-notebook.sh` on the cluster using [HDInsight Script Actions](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).</span></span>

   <span data-ttu-id="123ca-138">Вернитесь к кластеру HDI на портале Azure и выберите **Действия скрипта** из параметров слева.</span><span class="sxs-lookup"><span data-stu-id="123ca-138">Return to your HDI cluster in the Azure portal, and select **Script actions** from the options on the left.</span></span> <span data-ttu-id="123ca-139">Вы отправляете одно действие скрипта, чтобы развернуть .NET для Apache Spark REPL в кластере HDInsight Spark.</span><span class="sxs-lookup"><span data-stu-id="123ca-139">You submit one script action to deploy the .NET for Apache Spark REPL on your HDInsight Spark cluster.</span></span> <span data-ttu-id="123ca-140">Используйте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="123ca-140">Use the following settings:</span></span>

   |<span data-ttu-id="123ca-141">Свойство.</span><span class="sxs-lookup"><span data-stu-id="123ca-141">Property</span></span>  |<span data-ttu-id="123ca-142">Описание</span><span class="sxs-lookup"><span data-stu-id="123ca-142">Description</span></span>  |
   |---------|---------|
   | <span data-ttu-id="123ca-143">Тип скрипта</span><span class="sxs-lookup"><span data-stu-id="123ca-143">Script type</span></span> | <span data-ttu-id="123ca-144">Другой</span><span class="sxs-lookup"><span data-stu-id="123ca-144">Custom</span></span> |
   | <span data-ttu-id="123ca-145">name</span><span class="sxs-lookup"><span data-stu-id="123ca-145">Name</span></span> | <span data-ttu-id="123ca-146">*Установка .NET для Apache Spark в интерфейс интерактивной Notebook*.</span><span class="sxs-lookup"><span data-stu-id="123ca-146">*Install .NET for Apache Spark Interactive Notebook Experience*</span></span> |
   | <span data-ttu-id="123ca-147">URI bash-скрипта</span><span class="sxs-lookup"><span data-stu-id="123ca-147">Bash script URI</span></span> | <span data-ttu-id="123ca-148">Универсальный код ресурса (URI), по которому был отправлен файл `install-interactive-notebook.sh`.</span><span class="sxs-lookup"><span data-stu-id="123ca-148">The URI to which you uploaded `install-interactive-notebook.sh`.</span></span> |
   | <span data-ttu-id="123ca-149">Типы узлов</span><span class="sxs-lookup"><span data-stu-id="123ca-149">Node type(s)</span></span>| <span data-ttu-id="123ca-150">Головной и рабочий.</span><span class="sxs-lookup"><span data-stu-id="123ca-150">Head and Worker</span></span> |
   | <span data-ttu-id="123ca-151">Параметры</span><span class="sxs-lookup"><span data-stu-id="123ca-151">Parameters</span></span> | <span data-ttu-id="123ca-152">Версия .NET для Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="123ca-152">.NET for Apache Spark version.</span></span> <span data-ttu-id="123ca-153">Вы можете ознакомиться с [выпусками .NET для Apache Spark](https://github.com/dotnet/spark/releases).</span><span class="sxs-lookup"><span data-stu-id="123ca-153">You can check [.NET for Apache Spark releases](https://github.com/dotnet/spark/releases).</span></span> <span data-ttu-id="123ca-154">Например, если вы хотите установить Sparkdotnet версии 0.6.0, параметры будут следующими: `0.6.0`.</span><span class="sxs-lookup"><span data-stu-id="123ca-154">For example, if you want to install Sparkdotnet version 0.6.0 then it would be `0.6.0`.</span></span>

   <span data-ttu-id="123ca-155">Перейдите к следующему шагу, когда рядом с состоянием действия скрипта отображаются зеленые отметки.</span><span class="sxs-lookup"><span data-stu-id="123ca-155">Move to the next step when green checkmarks appear next to the status of the script action.</span></span>

### <a name="start-the-livy-server"></a><span data-ttu-id="123ca-156">Запуск сервера Livy</span><span class="sxs-lookup"><span data-stu-id="123ca-156">Start the Livy server</span></span>

<span data-ttu-id="123ca-157">Выполните инструкции, приведенные в разделе [Остановка работы сервера Livy](#stop-the-livy-server), чтобы **запустить** (а не **остановить**) сервер Livy для Spark2 узлов **hn0** и **hn1**.</span><span class="sxs-lookup"><span data-stu-id="123ca-157">Follow the instructions in the [Stop Livy server](#stop-the-livy-server) section to **Start** (rather than **Stop**) the Livy for Spark2 Server for hosts **hn0** and **hn1**.</span></span>

### <a name="set-up-spark-default-configurations"></a><span data-ttu-id="123ca-158">Настройка конфигураций по умолчанию Spark</span><span class="sxs-lookup"><span data-stu-id="123ca-158">Set up Spark default configurations</span></span>

1. <span data-ttu-id="123ca-159">На портале щелкните **Обзор**, а затем выберите **Домашняя страница Ambari**.</span><span class="sxs-lookup"><span data-stu-id="123ca-159">From the portal, select **Overview**, and then select **Ambari home**.</span></span> <span data-ttu-id="123ca-160">При появлении запроса введите учетные данные для входа в кластер.</span><span class="sxs-lookup"><span data-stu-id="123ca-160">If prompted, enter the cluster login credentials for the cluster.</span></span>

2. <span data-ttu-id="123ca-161">Выберите **Spark2** и **CONFIGS** (Конфигурации).</span><span class="sxs-lookup"><span data-stu-id="123ca-161">Select **Spark2** and **CONFIGS**.</span></span> <span data-ttu-id="123ca-162">Затем выберите группу **Custom spark2-defaults**.</span><span class="sxs-lookup"><span data-stu-id="123ca-162">Then, select **Custom spark2-defaults**.</span></span>

   ![Настройка конфигураций](./media/hdinsight-notebook-installation/spark-configs.png)

3. <span data-ttu-id="123ca-164">Выберите **Добавить свойство…** , чтобы добавить параметры Spark по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="123ca-164">Select **Add Property...** to add Spark default settings.</span></span>

   ![Добавление свойства](./media/hdinsight-notebook-installation/add-property.png)

   <span data-ttu-id="123ca-166">Существует три отдельных свойства.</span><span class="sxs-lookup"><span data-stu-id="123ca-166">There are three individual properties.</span></span> <span data-ttu-id="123ca-167">Добавьте их поочередно, используя тип свойства **Текст** в режиме добавления одного свойства.</span><span class="sxs-lookup"><span data-stu-id="123ca-167">Add them one at a time using the **TEXT** property type in Single property add mode.</span></span> <span data-ttu-id="123ca-168">Убедитесь, что до или после ключей и значений нет дополнительных пробелов.</span><span class="sxs-lookup"><span data-stu-id="123ca-168">Check that you don't have any extra spaces before or after any of the keys/values.</span></span>

   * <span data-ttu-id="123ca-169">**Свойство 1**.</span><span class="sxs-lookup"><span data-stu-id="123ca-169">**Property 1**</span></span>
       * <span data-ttu-id="123ca-170">Ключ:&ensp;&ensp;`spark.dotnet.shell.command`.</span><span class="sxs-lookup"><span data-stu-id="123ca-170">Key:&ensp;&ensp;`spark.dotnet.shell.command`</span></span>
       * <span data-ttu-id="123ca-171">Значение: `/usr/share/dotnet-tools/dotnet-try,kernel-server,--default-kernel,csharp`</span><span class="sxs-lookup"><span data-stu-id="123ca-171">Value: `/usr/share/dotnet-tools/dotnet-try,kernel-server,--default-kernel,csharp`</span></span>

   * <span data-ttu-id="123ca-172">**Свойство 2**. Используйте версию .NET для Apache Spark, которая была включена в предыдущее действие скрипта.</span><span class="sxs-lookup"><span data-stu-id="123ca-172">**Property 2** Use the version of .NET for Apache Spark which you had included in the previous script action.</span></span>
       * <span data-ttu-id="123ca-173">Ключ:&ensp;&ensp;`spark.dotnet.packages`.</span><span class="sxs-lookup"><span data-stu-id="123ca-173">Key:&ensp;&ensp;`spark.dotnet.packages`</span></span>
       * <span data-ttu-id="123ca-174">Значение: `["nuget: Microsoft.Spark, 0.6.0", "nuget: Microsoft.Spark.Extensions.Delta, 0.6.0"]`</span><span class="sxs-lookup"><span data-stu-id="123ca-174">Value: `["nuget: Microsoft.Spark, 0.6.0", "nuget: Microsoft.Spark.Extensions.Delta, 0.6.0"]`</span></span>

   * <span data-ttu-id="123ca-175">**Свойство 3**.</span><span class="sxs-lookup"><span data-stu-id="123ca-175">**Property 3**</span></span>
       * <span data-ttu-id="123ca-176">Ключ:&ensp;&ensp;`spark.dotnet.interpreter`.</span><span class="sxs-lookup"><span data-stu-id="123ca-176">Key:&ensp;&ensp;`spark.dotnet.interpreter`</span></span>
       * <span data-ttu-id="123ca-177">Значение: `try`</span><span class="sxs-lookup"><span data-stu-id="123ca-177">Value: `try`</span></span>

   <span data-ttu-id="123ca-178">Например, на следующем рисунке показан параметр для добавления свойства 1:</span><span class="sxs-lookup"><span data-stu-id="123ca-178">For example, the following image captures the setting for adding property 1:</span></span>

   ![Настройка конфигураций](./media/hdinsight-notebook-installation/add-sparkconfig.png)

   <span data-ttu-id="123ca-180">После добавления трех свойств выберите **SAVE** (Сохранить).</span><span class="sxs-lookup"><span data-stu-id="123ca-180">After adding the three properties, select **SAVE**.</span></span> <span data-ttu-id="123ca-181">Если появится экран предупреждения с рекомендациями конфигурации, выберите **PROCEED ANYWAY** (Продолжить).</span><span class="sxs-lookup"><span data-stu-id="123ca-181">If you see a warning screen of config recommendations, select **PROCEED ANYWAY**.</span></span>

4. <span data-ttu-id="123ca-182">Перезапустите затронутые компоненты.</span><span class="sxs-lookup"><span data-stu-id="123ca-182">Restart affected components.</span></span>

   <span data-ttu-id="123ca-183">После добавления новых свойств необходимо перезапустить компоненты, которые были затронуты изменениями.</span><span class="sxs-lookup"><span data-stu-id="123ca-183">After adding the new properties, you need to restart components that were affected by the changes.</span></span> <span data-ttu-id="123ca-184">В верхней части выберите **RESTART** (Перезапустить), а затем — **Restart All Affected** (Перезапустить все затронутые) из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="123ca-184">At the top, select **RESTART**, and then **Restart All Affected** from the drop-down.</span></span>

   ![Настройка конфигураций](./media/hdinsight-notebook-installation/restart-affected.png)

   <span data-ttu-id="123ca-186">При появлении запроса выберите **CONFIRM RESTART ALL** (Подтвердить перезапуск всех), чтобы продолжить, а затем нажмите кнопку **ОК** для завершения работы.</span><span class="sxs-lookup"><span data-stu-id="123ca-186">When prompted, select **CONFIRM RESTART ALL** to continue, then click **OK** to finish.</span></span>

## <a name="submit-jobs-through-a-jupyter-notebook"></a><span data-ttu-id="123ca-187">Отправка заданий с помощью записной книжки Jupyter</span><span class="sxs-lookup"><span data-stu-id="123ca-187">Submit jobs through a Jupyter notebook</span></span>

<span data-ttu-id="123ca-188">После завершения предыдущих шагов можно отправить задания .NET для Apache Spark с помощью записных книжек Jupyter.</span><span class="sxs-lookup"><span data-stu-id="123ca-188">After finishing the previous steps, you can now submit your .NET for Apache Spark jobs through Jupyter notebooks.</span></span>

1. <span data-ttu-id="123ca-189">Создайте записную книжку .NET для Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="123ca-189">Create a new .NET for Apache Spark notebook.</span></span> <span data-ttu-id="123ca-190">Запустите записную книжку Jupyter из кластера HDI на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="123ca-190">Launch a Jupyter notebook from your HDI cluster in the Azure portal.</span></span>

   ![Запуск Jupyter Notebook](./media/hdinsight-notebook-installation/launch-notebook.png)

   <span data-ttu-id="123ca-192">Затем выберите **New** (Создать)  >  **.NET Spark (C#)** , чтобы создать записную книжку.</span><span class="sxs-lookup"><span data-stu-id="123ca-192">Then, select **New** > **.NET Spark (C#)** to create a notebook.</span></span>

   ![Портативный компьютер Jupyter](./media/hdinsight-notebook-installation/create-sparkdotnet-notebook.png)

2. <span data-ttu-id="123ca-194">Отправьте задания с помощью .NET для Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="123ca-194">Submit jobs using .NET for Apache Spark.</span></span>

   <span data-ttu-id="123ca-195">Чтобы создать кадр данных, используйте следующий фрагмент кода:</span><span class="sxs-lookup"><span data-stu-id="123ca-195">Use the following code snippet to create a DataFrame:</span></span>

   ```csharp
   var df = spark.Range(0,5);
   df.Show();
   ```

   ![Отправка задания Spark](./media/hdinsight-notebook-installation/create-df.png)

   <span data-ttu-id="123ca-197">Используйте следующий фрагмент кода, чтобы зарегистрировать определяемую пользователем функцию (UDF) и использовать ее с кадрами данных:</span><span class="sxs-lookup"><span data-stu-id="123ca-197">Use the following code snippet to register a user-defined function (UDF) and use the UDF with DataFrames:</span></span>

   ```csharp
   var myawesomeudf = Udf<int, string>((id) => $"hello {id}");
   df.Select(myawesomeudf(df["id"])).Show();
   ```

   ![Отправка задания Spark](./media/hdinsight-notebook-installation/run-udf.png)

## <a name="next-steps"></a><span data-ttu-id="123ca-199">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="123ca-199">Next steps</span></span>

* [<span data-ttu-id="123ca-200">Развертывание приложения .NET для Apache Spark в Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="123ca-200">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="123ca-201">Документация по HDInsight</span><span class="sxs-lookup"><span data-stu-id="123ca-201">HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)
