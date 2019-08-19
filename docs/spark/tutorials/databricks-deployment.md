---
title: Развертывание .NET для Apache Spark приложения в модулях
description: Узнайте, как развернуть .NET для приложения Apache Spark в модулях.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: ca9e93a413622c84325ca9fc8bac17268b990c5a
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2019
ms.locfileid: "69576971"
---
# <a name="deploy-a-net-for-apache-spark-application-to-databricks"></a>Развертывание .NET для Apache Spark приложения в модулях

В этом учебнике описывается развертывание приложения .NET для Apache Spark в модулях.

В этом руководстве вы узнаете, как:

> [!div class="checklist"]
> * Подготовка Microsoft. Spark. Worker
> * Публикация приложения Spark .NET
> * Развертывание приложения в модулях
> * Запуск приложения

## <a name="prerequisites"></a>Предварительные требования

Прежде чем начать, выполните следующие действия.

* Скачайте интерфейс [командной строки для модуля](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).
* Скачайте [Install-Worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) на локальный компьютер. Это вспомогательный скрипт, который используется позже для копирования .NET для Apache Spark зависимых файлов в рабочие узлы кластера Spark.

## <a name="prepare-worker-dependencies"></a>Подготовка зависимостей рабочей роли

**Microsoft. Spark. Worker** — это компонент серверной части, который находится на отдельных рабочих узлах кластера Spark. Если вы хотите выполнить определяемую C# пользователем функцию (UDF), Spark необходимо понять, как запустить среду CLR .NET для выполнения пользовательской функции. **Microsoft. Spark. Worker** предоставляет коллекцию классов для Spark, которые обеспечивают эту функциональность.

1. Выберите выпуск [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp, который будет развернут в кластере.

   Например, если вы хотите `.NET for Apache Spark v0.1.0` использовать `netcoreapp2.1`, скачайте [Microsoft. Spark. Worker. netcoreapp 2.1. Linux-x64-0.1.0. tar. gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).

2. Отправляйте `Microsoft.Spark.Worker.<release>.tar.gz` и [Install-Worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) в распределенную файловую систему (например, DBFS), к которой имеет доступ кластер.

## <a name="prepare-your-net-for-apache-spark-app"></a>Подготовка .NET для приложения Apache Spark

1. Выполните инструкции из руководства по [началу работы](get-started.md) , чтобы создать приложение.

2. Опубликуйте свое приложение Spark .NET как автономное.

   В Linux можно выполнить следующую команду.

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. Создание `<your app>.zip` для опубликованных файлов.

   Вы можете выполнить следующую команду в Linux с помощью `zip`команды.

   ```bash
   zip -r <your app>.zip .
   ```

4. Отправьте следующее в распределенную файловую систему (например, DBFS), к которой имеет доступ кластер:

   * `microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Этот JAR-файл входит в состав пакета NuGet [Microsoft. Spark](https://www.nuget.org/packages/Microsoft.Spark/) и размещается в выходном каталоге сборки приложения.
   * `<your app>.zip`
   * Файлы (например, файлы зависимостей или общие данные, доступные каждому рабочему процессу) или сборки (например, библиотеки DLL, содержащие определяемые пользователем функции или библиотеки, от которых зависит ваше приложение) должны размещаться в рабочем каталоге каждого исполнителя.

## <a name="deploy-to-databricks"></a>Развертывание в Databricks

[Модуль](https://databricks.com) обработки данных — это платформа, которая предоставляет облачные данные, основанные на больших объемах, с помощью Apache Spark.

> [!Note] 
> Модуль данных [Azure Databricks](https://azure.microsoft.com/services/databricks/) и [AWS](https://databricks.com/aws) основаны на Linux. Поэтому, если вы заинтересованы в развертывании приложения в модулях, убедитесь, что приложение совместимо .NET Standard и вы используете [компилятор .NET Core](https://dotnet.microsoft.com/download) для компиляции приложения.

Кирпичы позволяют отправлять .NET для Apache Spark приложений в существующий активный кластер или создавать новый кластер при каждом запуске задания. Для этого требуется установить **Microsoft. Spark. Worker** перед отправкой приложения .net для Apache Spark.

### <a name="deploy-microsoftsparkworker"></a>Развертывание Microsoft. Spark. Worker

Этот шаг требуется только один раз для кластера.

1. Скачайте [DB-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) и [Install-Worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh
) на локальный компьютер.

2. Измените **DB-init.sh** , чтобы он указывал на выпуск **Microsoft. Spark. Worker** , который вы хотите скачать и установить в кластере.

3. Установите интерфейс [командной строки для модуля](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html)установки.

4. [Настройте](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html#set-up-authentication) сведения о проверке подлинности для интерфейса командной строки для модуля данных.

5. Отправьте файлы в кластер "кирпичы" с помощью следующей команды:

   ```bash
   cd <path-to-db-init-and-install-worker>
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   ```

6. Перейдите в рабочую область "кирпичы". Выберите **кластеры** в меню слева, а затем выберите **создать кластер**.

7. После надлежащего конфигурирования кластера задайте **Скрипт init** и создайте кластер.

   ![Изображение действия сценария](./media/databricks-deployment/deployment-databricks-init-script.png)

## <a name="run-your-app"></a>Запуск приложения 

Вы можете использовать `set JAR` или `spark-submit` для отправки задания в кирпичы.

### <a name="use-set-jar"></a>Использование Set JAR

[Set JAR](https://docs.databricks.com/user-guide/jobs.html#create-a-job) позволяет отправить задание в существующий активный кластер.

#### <a name="one-time-setup"></a>Однократная настройка

1. Перейдите к кластеру кирпичов и выберите **задания** в меню слева. Затем выберите **задать JAR**.

2. Отправьте соответствующий `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` файл.

3. Задайте соответствующие параметры.

   ```
   Main Class: org.apache.spark.deploy.DotnetRunner
   Arguments /dbfs/apps/<your-app-name>.zip <your-app-main-class>
   ```
 
4. Настройте **кластер** так, чтобы он указывал на существующий кластер, для которого был создан **Скрипт init** , в предыдущем разделе.

#### <a name="publish-and-run-your-app"></a>Публикация и запуск приложения

1. Используйте интерфейс [командной строки](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html) для передачи приложения в кластер кирпичей.

      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
      ```

2. Этот шаг необходим только в том случае, если сборки приложения (например, библиотеки DLL, содержащие определяемые пользователем функции вместе с их зависимостями) должны быть помещены в рабочий каталог каждого **Microsoft. Spark. Worker**.

   - Передача сборок приложения в кластер кирпичов
      
      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <assembly>.dll dbfs:/apps/dependencies
      ```

   - Раскомментируйте и измените раздел зависимостей приложений в [DB-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) , чтобы указать путь зависимостей приложения и передать его в кластер кирпичей.
   
      ```bash
      cd <path-to-db-init-and-install-worker>
      databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
      ```
   
   - Перезапустите кластер.

3. Перейдите к кластеру "кирпичы" в рабочей области "кирпичы". В разделе **задания**выберите задание, а затем щелкните **Запустить сейчас** , чтобы выполнить задание.

### <a name="use-spark-submit"></a>Использование Spark-Submit

Команда [Spark-Submit](https://spark.apache.org/docs/latest/submitting-applications.html) позволяет отправить задание в новый кластер.

1. [Создайте задание](https://docs.databricks.com/user-guide/jobs.html) и выберите **Настройка Spark-Submit**.

2. Настройте `spark-submit` со следующими параметрами:

      ```bash
      ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
      ```

3. Перейдите к кластеру "кирпичы" в рабочей области "кирпичы". В разделе **задания**выберите задание, а затем щелкните **Запустить сейчас** , чтобы выполнить задание.

## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы развернули .NET для Apache Spark приложения в модулях. Чтобы узнать больше о модулях, перейдите к документации по Azure Databricks.

> [!div class="nextstepaction"]
> [Документация по Azure Databricks](https://docs.microsoft.com/azure/azure-databricks/)
