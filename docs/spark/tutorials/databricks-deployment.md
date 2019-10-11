---
title: Развертывание приложения .NET для Apache Spark в Databricks
description: Узнайте, как развернуть приложение .NET для Apache Spark в Databricks.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 035a3c36337413153ee0370aec154d48b84a4711
ms.sourcegitcommit: 7bfe1682d9368cf88d43e895d1e80ba2d88c3a99
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71957251"
---
# <a name="deploy-a-net-for-apache-spark-application-to-databricks"></a>Развертывание приложения .NET для Apache Spark в Databricks

В этом руководстве рассматривается развертывание приложения .NET для Apache Spark в Databricks.

В этом руководстве вы узнаете, как:

> [!div class="checklist"]
>
> - Подготовка Microsoft.Spark.Worker
> - Публикация приложения Spark .NET
> - Развертывание приложения в Databricks
> - Запуск приложения

## <a name="prerequisites"></a>Предварительные требования

Прежде чем начать, сделайте следующее:

- Скачайте [интерфейс командной строки Databricks](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).
- Скачайте файл [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) на локальный компьютер. Это вспомогательный скрипт, который будет использоваться позже для копирования зависимых файлов .NET для Apache Spark в рабочие узлы кластера Spark.

## <a name="prepare-worker-dependencies"></a>Подготовка зависимостей рабочей роли

**Microsoft.Spark.Worker** — это серверный компонент, который размещается в отдельных рабочих узлах кластера Spark. Если вам нужно выполнить определяемую пользователем функцию C#, Spark необходимо знать, как запустить среду CLR .NET для выполнения этой функции. **Microsoft.Spark.Worker** предоставляет Spark коллекцию классов, которые обеспечивают такую возможность.

1. Выберите выпуск netcoreapp компонента [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) для Linux, который будет развернут в кластере.

   Например, чтобы использовать `.NET for Apache Spark v0.1.0` с `netcoreapp2.1`, скачайте выпуск [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).

2. Передайте файлы `Microsoft.Spark.Worker.<release>.tar.gz` и [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) в распределенную файловую систему (например, DBFS), к которой есть доступ у кластера.

## <a name="prepare-your-net-for-apache-spark-app"></a>Подготовка приложения .NET для Apache Spark

1. Выполните сборку приложения согласно инструкциям из [руководства по началу работы](get-started.md).

2. Опубликуйте приложение .NET для Spark как автономное.

   В Linux можно выполнить приведенную ниже команду.

   ```dotnetcli
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. Создайте `<your app>.zip` для опубликованных файлов.

   В Linux можно выполнить приведенную ниже команду с помощью `zip`.

   ```bash
   zip -r <your app>.zip .
   ```

4. Передайте в распределенную файловую систему (например, DBFS), к которой есть доступ у кластера, следующие файлы:

   - `microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`. Этот JAR-файл входит в состав пакета NuGet [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) и размещается в выходном каталоге сборки приложения.
   - `<your app>.zip`
   - Файлы (например, файлы зависимостей или общие данные, доступные каждой рабочей роли) или сборки (например, библиотеки DLL, содержащие определяемые пользователем функции, или библиотеки, от которых зависит приложение), которые необходимо поместить в рабочий каталог каждого исполнителя.

## <a name="deploy-to-databricks"></a>Развертывание в Databricks

[Databricks](https://databricks.com) — это платформа, которая обеспечивает обработку больших данных в облаке с помощью Apache Spark.

> [!Note] 
> [Azure Databricks](https://azure.microsoft.com/services/databricks/) и [AWS Databricks](https://databricks.com/aws) работают под управлением Linux. Поэтому если вы хотите развернуть приложение в Databricks, оно должно быть совместимо с .NET Standard, а для его компиляции необходимо использовать [компилятор .NET Core](https://dotnet.microsoft.com/download).

Databricks позволяет отправлять приложения .NET для Apache Spark в существующий активный кластер или создавать новый кластер при каждом запуске задания. Перед отправкой приложения .NET для Apache Spark требуется установить **Microsoft.Spark.Worker**.

### <a name="deploy-microsoftsparkworker"></a>Развертывание Microsoft.Spark.Worker

Этот шаг необходимо выполнить для кластера только один раз.

1. Скачайте файлы [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) и [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh
) на локальный компьютер.

2. Измените файл **db-init.sh** так, чтобы он указывал на выпуск **Microsoft.Spark.Worker**, который вы хотите скачать и установить в кластере.

3. Установите [интерфейс командной строки Databricks](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).

4. [Настройте сведения о проверке подлинности](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html#set-up-authentication) для интерфейса командной строки Databricks.

5. Отправьте файлы в кластер Databricks с помощью следующей команды:

   ```bash
   cd <path-to-db-init-and-install-worker>
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   ```

6. Перейдите к рабочей области Databricks. В меню слева выберите **Кластеры**, а затем выберите **Создать кластер**.

7. Настроив кластер нужным образом, укажите **скрипт инициализации** и создайте кластер.

   ![Изображение действия скрипта](./media/databricks-deployment/deployment-databricks-init-script.png)

## <a name="run-your-app"></a>Запуск приложения 

Для отправки задания в Databricks можно использовать `set JAR` или `spark-submit`.

### <a name="use-set-jar"></a>Использование действия "Указание файла JAR"

Действие [Указание файла JAR](https://docs.databricks.com/user-guide/jobs.html#create-a-job) позволяет отправить задание в существующий активный кластер.

#### <a name="one-time-setup"></a>Однократная настройка

1. Перейдите в кластер Databricks и в меню слева выберите **Задания**. Затем выберите действие **Указание файла JAR**.

2. Отправьте соответствующий файл `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar`.

3. Задайте необходимые параметры.

   | Параметр   | Значение                                                |
   |-------------|------------------------------------------------------|
   | Основной класс  | org.apache.spark.deploy.dotnet.DotnetRunner          |
   | Аргументы   | /dbfs/apps/<your-app-name>.zip <your-app-main-class> |

4. Настройте параметр **Кластер** так, чтобы он указывал на существующий кластер, для которого в предыдущем разделе был создан **скрипт инициализации**.

#### <a name="publish-and-run-your-app"></a>Публикация и запуск приложения

1. Чтобы передать приложение в кластер Databricks, используйте [интерфейс командной строки Databricks](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).

      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
      ```

2. Этот шаг требуется, только если сборки приложения (например, библиотеки DLL, содержащие определяемые пользователем функции, и их зависимости) необходимо поместить в рабочий каталог каждой роли **Microsoft.Spark.Worker**.

   - Передача сборок приложения в кластер Databricks
      
      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <assembly>.dll dbfs:/apps/dependencies
      ```

   - Раскомментируйте и измените раздел зависимостей приложения в файле [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh), указав путь к зависимостям приложения, а затем передайте этот файл в кластер Databricks.
   
      ```bash
      cd <path-to-db-init-and-install-worker>
      databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
      ```
   
   - Перезапустите кластер.

3. Перейдите в кластер Databricks в рабочей области Databricks. В разделе **Задания** выберите задание, а затем щелкните **Запустить сейчас**, чтобы выполнить его.

### <a name="use-spark-submit"></a>Использование команды spark-submit

Команда [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) позволяет отправить задание в новый кластер.

1. [Создайте задание](https://docs.databricks.com/user-guide/jobs.html) и выберите **Настройка spark-submit**.

2. Настройте команду `spark-submit` со следующими параметрами:

      ```bash
      ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
      ```

3. Перейдите в кластер Databricks в рабочей области Databricks. В разделе **Задания** выберите задание, а затем щелкните **Запустить сейчас**, чтобы выполнить его.

## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы развернули приложение .NET для Apache Spark в Databricks. Дополнительные сведения о Databricks см. в документации по Azure Databricks.

> [!div class="nextstepaction"]
> [Документация по Azure Databricks](https://docs.microsoft.com/azure/azure-databricks/)
