---
title: Начало работы с .NET для Apache Spark
description: Узнайте, как запустить приложение .NET для Apache Spark с помощью .NET Core в Windows.
ms.date: 06/27/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 19efc8412d834d73069c61e1cc1ccd9e5eb8593b
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774376"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a>Учебник. Начало работы с .NET для Apache Spark

В этом руководстве описывается, как запустить приложение .NET для Apache Spark с помощью .NET Core в Windows.

В этом руководстве вы узнаете, как:

> [!div class="checklist"]
>
> * Подготовка среды Windows для .NET для Apache Spark
> * Скачивание **Microsoft.Spark.Worker**
> * Сборка и запуск простого приложения .NET для Apache Spark

## <a name="prepare-your-environment"></a>Подготовка среды

Перед началом работы убедитесь в том, что вы можете выполнять команды `dotnet`, `java`, `mvn` и `spark-shell` из командной строки. Если среда уже подготовлена, можно перейти к следующему разделу. Если какие-либо из этих команд или все они не выполняются, выполните указанные ниже действия.

1. Скачайте и установите [пакет SDK для .NET Core 2.1x](https://dotnet.microsoft.com/download/dotnet-core/2.1). При установке пакета SDK в переменную PATH добавляется цепочка инструментов `dotnet`. Выполните команду PowerShell `dotnet --version`, чтобы проверить установку.

2. Установите [Visual Studio 2017](https://www.visualstudio.com/downloads/) или [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) с последними обновлениями. Можно использовать выпуск Community, Professional или Enterprise. Версия Community бесплатна.

   Во время установки выберите следующие рабочие нагрузки:
      * Разработка классических приложений .NET
          * Все необходимые компоненты
          * Средства разработки для .NET Framework 4.6.1
      * Кроссплатформенная разработка .NET Core
          * Все необходимые компоненты

3. Установите [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).

    * Выберите соответствующую версию для вашей операционной системы. Например, для компьютера с 64-разрядной версией Windows выберите **jdk-8u201-windows-x64.exe**.
    * Выполните команду PowerShell `java -version`, чтобы проверить установку.

4. Установите [Apache Maven 3.6.0 или более поздней версии](https://maven.apache.org/download.cgi).
    * Загрузите [Apache Maven 3.6.2](http://mirror.metrocast.net/apache/maven/maven-3/3.6.2/binaries/apache-maven-3.6.2-bin.zip).
    * Извлеките содержимое в локальный каталог. Например, `c:\bin\apache-maven-3.6.2\`.
    * Добавьте Apache Maven в [переменную среды PATH](https://www.java.com/en/download/help/path.xml). Если содержимое было извлечено в `c:\bin\apache-maven-3.6.2\`, в переменную PATH следует добавить `c:\bin\apache-maven-3.6.2\bin`.
    * Выполните команду PowerShell `mvn -version`, чтобы проверить установку.

5. Установите [Apache Spark 2.3 или более поздней версии](https://spark.apache.org/downloads.html). Apache Spark 2.4 и более поздние версии не поддерживаются.
    * Скачайте [Apache Spark 2.3 или более поздней версии](https://spark.apache.org/downloads.html) и извлеките содержимое в локальную папку с помощью такого средства, как [7-zip](https://www.7-zip.org/) или [WinZip](https://www.winzip.com/). Например, можно извлечь его в папку `c:\bin\spark-2.3.2-bin-hadoop2.7\`.
    * Добавьте Apache Spark в [переменную среды PATH](https://www.java.com/en/download/help/path.xml). Если содержимое было извлечено в `c:\bin\spark-2.3.2-bin-hadoop2.7\`, в переменную PATH следует добавить `c:\bin\spark-2.3.2-bin-hadoop2.7\bin`.
    * Добавьте [новую переменную среды](https://www.java.com/en/download/help/path.xml) с именем `SPARK_HOME`. Если содержимое было извлечено в `C:\bin\spark-2.3.2-bin-hadoop2.7\`, используйте `C:\bin\spark-2.3.2-bin-hadoop2.7\` в качестве **значения переменной**.
    * Убедитесь в том, что вы можете выполнить команду `spark-shell` в командной строке.

6. Настройте [WinUtils](https://github.com/steveloughran/winutils).
    * Скачайте двоичный файл **winutils.exe** из [репозитория WinUtils](https://github.com/steveloughran/winutils). Выберите версию Hadoop, с использованием которой был скомпилирован дистрибутив Spark. Например, для **Spark 2.3.2** используйте **hadoop-2.7.1**. Версия Hadoop указывается в конце имени папки установки Spark.
    * Сохраните двоичный файл **winutils.exe** в любом каталоге на ваш выбор. Например, `c:\hadoop\bin`.
    * Присвойте переменной `HADOOP_HOME` путь к каталогу с файлом **winutils.exe** без `bin`. Например, `c:\hadoop`.
    * Включите в переменную среды PATH значение `%HADOOP_HOME%\bin`.

Перед переходом к следующему разделу еще раз проверьте, можно ли выполнять команды `dotnet`, `java`, `mvn` и `spark-shell` из командной строки.

## <a name="download-the-microsoftsparkworker-release"></a>Скачивание выпуска Microsoft.Spark.Worker

1. Скачайте выпуск [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) на локальный компьютер со страницы выпусков .NET для Apache Spark в GitHub. Например, его можно скачать по пути `c:\bin\Microsoft.Spark.Worker\`.

2. Создайте [переменную среды](https://www.java.com/en/download/help/path.xml) с именем `DOTNET_WORKER_DIR` и присвойте ей путь к каталогу, в который вы скачали и извлекли выпуск **Microsoft.Spark.Worker**. Например, `c:\bin\Microsoft.Spark.Worker`.

## <a name="clone-the-net-for-apache-spark-github-repo"></a>Клонирование репозитория .NET для Apache Spark в GitHub

Используйте приведенную ниже команду [GitBash](https://gitforwindows.org/), чтобы клонировать репозиторий .NET для Apache Spark на компьютер.

```bash
git clone https://github.com/dotnet/spark.git c:\github\dotnet-spark
```

## <a name="write-a-net-for-apache-spark-app"></a>Написание приложения .NET для Apache Spark

1. Откройте **Visual Studio** и последовательно выберите **Файл > Создать новый проект > Консольное приложение (.NET Core)** . Назовите приложение **HelloSpark**.

2. Установите [пакет NuGet Microsoft.Spark](https://www.nuget.org/profiles/spark). Дополнительные сведения об установке пакетов NuGet см. в статье [Способы установки пакетов NuGet](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).

3. В **обозревателе решений** откройте файл **Program.cs** и добавьте следующий код C#:

   ```csharp
     var spark = SparkSession.Builder().GetOrCreate();
     var df = spark.Read().Json("people.json");
     df.Show();
   ```

4. Постройте решение.

## <a name="run-your-net-for-apache-spark-app"></a>Запуск приложения .NET для Apache Spark

1. Откройте **PowerShell** и перейдите в папку, в которой хранится приложение.

   ```powershell
   cd <your-app-output-directory>
   ```

2. Создайте файл **people.json** со следующим содержимым:

   ```json
   {"name":"Michael"}
   {"name":"Andy", "age":30}
   {"name":"Justin", "age":19}
   ```

3. Запустите приложение с помощью следующей команды PowerShell:

   ```powershell
    spark-submit `
    --class org.apache.spark.deploy.dotnet.DotnetRunner `
    --master local `
    microsoft-spark-2.4.x-<version>.jar `
    dotnet HelloSpark.dll
    ```

Поздравляем! Вы успешно создали и запустили приложение .NET для Apache Spark.

## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы узнали, как:
> [!div class="checklist"]
>
> * Подготовка среды Windows для .NET для Apache Spark
> * Скачивание **Microsoft.Spark.Worker**
> * Сборка и запуск простого приложения .NET для Apache Spark

Дополнительные сведения см. на странице ресурсов.
> [!div class="nextstepaction"]
> [Ресурсы по .NET для Apache Spark](../resources/index.md)
