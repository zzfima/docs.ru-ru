---
title: Начало работы с .NET для Apache Spark
description: Узнайте, как запустить приложение .NET для Apache Spark, используя .NET Core на Windows, macOS и Ubuntu.
ms.date: 01/31/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 018c21804bf942233e07039281d7ec22a6bef763
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092321"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a>Учебник. Начало работы с .NET для Apache Spark

В этом руководстве описывается, как запустить приложение .NET для Apache Spark, используя .NET Core на Windows, macOS и Ubuntu.

В этом руководстве вы узнаете, как:

> [!div class="checklist"]
>
> * подготовить среду под .NET для Apache Spark;
> * написать свое первое приложение .NET для Apache Spark;
> * скомпилировать и запустить простое приложение .NET для Apache Spark.

## <a name="prepare-your-environment"></a>Подготовка среды

Прежде чем приступить к написанию приложения, нужно настроить некоторые необходимые зависимости. Если вы можете выполнить `dotnet`, `java`, `mvn`, `spark-shell` из среды командной строки, то ваша среда уже подготовлена, и вы можете перейти к следующему разделу. Если эти команды или хотя бы одну из них выполнить не получается, сделайте следующее.

### <a name="1-install-net"></a>1. Установка .NET

Чтобы приступить к созданию приложений .NET, необходимо загрузить и установить пакет средств разработки программного обеспечения (SDK) для .NET.

Скачайте и установите [пакет SDK для .NET Core](https://dotnet.microsoft.com/download/dotnet-core/3.1). При установке пакета SDK в переменную PATH добавляется цепочка инструментов `dotnet`.

Установив пакет SDK для .NET Core, откройте новое окно командной строки или терминала и выполните команду `dotnet`.

Если команда выполняется и выводит сведения об использовании dotnet, можно перейти к следующему шагу. Если возникает ошибка `'dotnet' is not recognized as an internal or external command`, убедитесь, что команда выполняется в **новом** окне терминала или командной строки.

### <a name="2-install-java"></a>2. Установка Java

Установите [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) для Windows и macOS или [OpenJDK 8](https://openjdk.java.net/install/) для Ubuntu.

Выберите соответствующую версию для вашей операционной системы. Например, выберите **jdk-8u201-windows-x64.exe** для компьютера с 64-разрядной версией Windows (как показано ниже) или **jdk-8u231-macosx-x64.dmg** для macOS. Затем используйте команду `java`, чтобы проверить установку.

![Скачать Java](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-compression-software"></a>3. Установка ПО для сжатия

Apache Spark загружается как сжатый файл TGZ. Чтобы извлечь файл, используйте программу-архиватор, например [7-Zip](https://www.7-zip.org/) или [WinZip](https://www.winzip.com/).

### <a name="4-install-apache-spark"></a>4. Установка Apache Spark

[Скачайте и установите Apache Spark](https://spark.apache.org/downloads.html). Вам потребуется выбрать одну из следующих версий: 2.3.* либо 2.4.0, 2.4.1, 2.4.3 или 2.4.4 (.NET для Apache Spark несовместима с другими версиями Apache Spark).

Команды, используемые на следующих этапах, подразумевают, что [скачана и установлена версия Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz). Если вы хотите использовать другую версию, замените **2.4.1** на соответствующий номер версии. Затем извлеките файл **TAR** и файлы Apache Spark.

Чтобы извлечь вложенный файл **TAR**:

* Найдите скачанный файл **spark-2.4.1-bin-hadoop2.7.tgz**.
* Щелкните файл правой кнопкой мыши и выберите **7-Zip -> Извлечь сюда**.
* **spark-2.4.1-bin-hadoop2.7.tar** будет создан рядом со скачанным файлом **TGZ**.

Чтобы извлечь файлы Apache Spark:

* Щелкните правой кнопкой мыши **spark-2.4.1-bin-hadoop2.7.tar** и выберите **7-Zip-> Извлечь файлы…**
* Введите **C:\bin** в поле **Извлечь в**.
* Снимите флажок под полем **Извлечь в**.
* Нажмите кнопку **ОК**.
* Файлы Apache Spark будут извлечены в папку C:\bin\spark-2.4.1-bin-hadoop2.7\

![Установка Spark](https://dotnet.microsoft.com/static/images/spark-extract-with-7-zip.png?v=YvjUv54LIxI9FbALPC3h8zSQdyMtK2-NKbFOliG-f8M)

Выполните следующие команды, чтобы задать переменные сред, используемые для обнаружения Apache Spark на **Windows**:

```console
setx HADOOP_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx SPARK_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
```

Выполните следующие команды, чтобы задать переменные сред, используемые для обнаружения Apache Spark на **macOS** и **Ubuntu**:

```bash
export SPARK_HOME=~/bin/spark-2.4.1-bin-hadoop2.7/
export PATH="$SPARK_HOME/bin:$PATH"
source ~/.bashrc
```

Установив все необходимое и задав переменные сред, откройте **новое** окно командной строки или терминала и выполните следующую команду:

`%SPARK_HOME%\bin\spark-submit --version`

Если команда выполняется и выводит сведения о версии, можно перейти к следующему шагу.

При возникновении ошибки `'spark-submit' is not recognized as an internal or external command` убедитесь, что вы открыли **новую** командную строку.

### <a name="5-install-net-for-apache-spark"></a>5. Установка .NET для Apache Spark

Загрузите выпуск [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) со страницы выпусков .NET для Apache Spark в GitHub. Например, если вы планируете использовать .NET Core на компьютере под управлением Windows, [скачайте выпуск netcoreapp3.1 для Windows x64](https://github.com/dotnet/spark/releases/download/v0.8.0/Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip).

Для извлечения Microsoft.Spark.Worker:

* Найдите скачанный файл **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip**.
* Щелкните правой кнопкой мыши и выберите **7-Zip -> Извлечь файлы…** .
* Введите **C:\bin** в поле **Извлечь в**.
* Снимите флажок под полем **Извлечь в**.
* Нажмите кнопку **ОК**.

![Установка .NET Spark](https://dotnet.microsoft.com/static/images/dotnet-for-spark-extract-with-7-zip.png?v=jwCyum9mL0mGIi4V5zC7yuvLfcj1_nL-QFFD8TClhZk)

### <a name="6-install-winutils-windows-only"></a>6.  Установка WinUtils (только для Windows)

.NET для Apache Spark требует установки WinUtils вместе с Apache Spark. [Скачайте winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe). Затем скопируйте WinUtils в папку **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.

> [!NOTE]
> Если вы используете другую версию Hadoop, которая указывается в конце имени папки установки Spark, [выберите версию WinUtils](https://github.com/steveloughran/winutils), совместимую с вашей версией Hadoop.

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a>7. Установка DOTNET_WORKER_DIR и проверка зависимостей

Выполните одну из следующих команд, чтобы задать переменную среды `DOTNET_WORKER_DIR`, которая используется приложениями .NET для обнаружения .NET для Apache Spark.

В **Windows** создайте [переменную среды](https://www.java.com/en/download/help/path.xml) с именем `DOTNET_WORKER_DIR` и присвойте ей путь к каталогу, в который вы скачали и извлекли Microsoft.Spark.Worker (например, `C:\bin\Microsoft.Spark.Worker\`).

В **macOS** создайте переменную среды с помощью `export DOTNET_WORKER_DIR <your_path>` и присвойте ей путь к каталогу, в который вы скачали и извлекли Microsoft.Spark.Worker (например, *~/bin/Microsoft.Spark.Worker/* ). 

В **Ubuntu** создайте [переменную среды](https://help.ubuntu.com/community/EnvironmentVariables) с именем `DOTNET_WORKER_DIR` и присвойте ей путь к каталогу, в который вы скачали и извлекли Microsoft.Spark.Worker (например, *~/bin/Microsoft.Spark.Worker*).

Наконец, перед переходом к следующему разделу еще раз проверьте, можно ли выполнять команды `dotnet`, `java`, `mvn` и `spark-shell` из командной строки.

## <a name="write-a-net-for-apache-spark-app"></a>Написание приложения .NET для Apache Spark

### <a name="1-create-a-console-app"></a>1. Создание консольного приложения

В командной строке или терминале выполните следующие команды, чтобы создать новое консольное приложение:

```dotnetcli
dotnet new console -o mySparkApp
cd mySparkApp
```

Команда `dotnet` создаст для вас приложение `new` типа `console`. Параметр `-o` создаст каталог с именем *mySparkApp*, в котором хранится приложение и используемые им файлы. Команда `cd mySparkApp` изменит каталог на только что созданный каталог приложения.

### <a name="2-install-nuget-package"></a>2. Установка пакета NuGet

Чтобы использовать .NET для Apache Spark в приложении, установите пакет Microsoft.Spark. В командной строке или терминале выполните следующую команду:

`dotnet add package Microsoft.Spark --version 0.8.0`

### <a name="3-code-your-app"></a>3. Написание кода приложения

Откройте *Program.cs* в Visual Studio Code или любом текстовом редакторе и замените весь код следующим:

```csharp
using Microsoft.Spark.Sql;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a Spark session.
            SparkSession spark = SparkSession
                .Builder()
                .AppName("word_count_sample")
                .GetOrCreate();

            // Create initial DataFrame.
            DataFrame dataFrame = spark.Read().Text("input.txt");

            // Count words.
            DataFrame words = dataFrame
                .Select(Functions.Split(Functions.Col("value"), " ").Alias("words"))
                .Select(Functions.Explode(Functions.Col("words"))
                .Alias("word"))
                .GroupBy("word")
                .Count()
                .OrderBy(Functions.Col("count").Desc());

            // Show results.
            words.Show();

            // Stop Spark session.
            spark.Stop();
        }
    }
}
```

### <a name="4-create-and-add-a-data-file"></a>4. Создание и добавление файла данных

Откройте командную строку или терминал и перейдите в папку своего приложения.

```bash
cd <your-app-output-directory>
```

Ваше приложение обрабатывает файл, содержащий строки текста. Создайте файл *input.txt* в каталоге *mySparkApp*, содержащий следующий текст:

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

## <a name="run-your-net-for-apache-spark-app"></a>Запуск приложения .NET для Apache Spark

1. Запустите сборку приложения с помощью следующей команды:

   ```dotnetcli
   dotnet build
   ```

2. Отправьте приложение для запуска на Apache Spark с помощью следующей команды:

   ```console
   spark-submit \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --master local \
   microsoft-spark-2.4.x-<version>.jar \
   dotnet HelloSpark.dll
   ```

   > [!NOTE]
   > При выполнении этой команды предполагается, что вы скачали Apache Spark и добавили это решение в переменную среды PATH, чтобы использовать `spark-submit`. В противном случае потребуется использовать полный путь (например, *C:\bin\apache-spark\bin\spark-submit* или *~/spark/bin/spark-submit*).

3. При запуске приложения данные подсчета слов из файла *input.txt* записываются в консоль.

Поздравляем! Вы успешно создали и запустили приложение .NET для Apache Spark.

## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы узнали, как:
> [!div class="checklist"]
>
> * Подготовка среды Windows для .NET для Apache Spark
> * написать свое первое приложение .NET для Apache Spark;
> * скомпилировать и запустить простое приложение .NET для Apache Spark.

Видео, подробнее объясняющее приведенные выше шаги, можно найти в серии видео [.NET for Apache Spark 101](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App) (Введение в .NET для Apache Spark).

Дополнительные сведения см. на странице ресурсов.
> [!div class="nextstepaction"]
> [Ресурсы по .NET для Apache Spark](../resources/index.md)
