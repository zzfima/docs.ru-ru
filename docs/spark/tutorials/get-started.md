---
title: Начало работы с .NET для Apache Spark
description: Узнайте, как запустить приложение .NET для Apache Spark с помощью .NET Core в Windows.
ms.date: 11/04/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 934b91a258937a976804109c71df232b8ce6d6d7
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337592"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a>Учебник. Начало работы с .NET для Apache Spark

В этом руководстве описывается, как запустить приложение .NET для Apache Spark с помощью .NET Core в Windows.

В этом руководстве вы узнаете, как:

> [!div class="checklist"]
>
> * Подготовка среды Windows для .NET для Apache Spark
> * написать свое первое приложение .NET для Apache Spark;
> * скомпилировать и запустить простое приложение .NET для Apache Spark.

## <a name="prepare-your-environment"></a>Подготовка среды

Прежде чем приступить к написанию приложения, нужно настроить некоторые необходимые зависимости. Если вы можете выполнить `dotnet`, `java`, `mvn`, `spark-shell` из среды командной строки, то ваша среда уже подготовлена, и вы можете перейти к следующему разделу. Если эти команды или хотя бы одну из них выполнить не получается, сделайте следующее.

### <a name="1-install-net"></a>1. Установка .NET

Чтобы приступить к созданию приложений .NET, необходимо загрузить и установить пакет средств разработки программного обеспечения (SDK) для .NET.

Скачайте и установите [пакет SDK для .NET Core](https://dotnet.microsoft.com/download/dotnet-core/3.0). При установке пакета SDK в переменную PATH добавляется цепочка инструментов `dotnet`.

После установки пакета SDK для .NET Core, откройте новую командную строку и выполните команду `dotnet`.

Если команда выполняется и выводит сведения об использовании dotnet, можно перейти к следующему шагу. При возникновении ошибки `'dotnet' is not recognized as an internal or external command` убедитесь, что вы открыли **новую** командную строку перед выполнением команды.

### <a name="2-install-java"></a>2. Установка Java

Установите [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).

Выберите соответствующую версию для вашей операционной системы. Например, для компьютера с 64-разрядной версией Windows выберите **jdk-8u201-windows-x64.exe**. Затем используйте команду `java`, чтобы проверить установку.

![Скачать Java](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-7-zip"></a>3. Установка 7-Zip

Apache Spark загружается как сжатый файл TGZ. Чтобы извлечь файл, используйте программу-архиватор, например 7-Zip.

* Посетите [страницу загрузок 7-Zip](https://www.7-zip.org/).
* В первой таблице на странице выберите загрузку 32-разрядной (x86) или 64-разрядной версии (x64) в зависимости от вашей операционной системы.
* После завершения загрузки запустите установщик.

![Скачать 7-Zip](https://dotnet.microsoft.com/static/images/7-zip-downloads.png?v=W6qWtFC1tTMKv3YGXz7lBa9F3M22uWyTvkMmunyroNk)

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

Выполните следующие команды, чтобы задать переменные среды, используемые для размещения Apache Spark:

```console
setx HADOOP_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx SPARK_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
```

После установки всего необходимого и настройки переменных среды, откройте **новую** командную строку и выполните следующую команду:

`%SPARK_HOME%\bin\spark-submit --version`

Если команда выполняется и выводит сведения о версии, можно перейти к следующему шагу.

При возникновении ошибки `'spark-submit' is not recognized as an internal or external command` убедитесь, что вы открыли **новую** командную строку.

### <a name="5-install-net-for-apache-spark"></a>5. Установка .NET для Apache Spark

Загрузите выпуск [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) со страницы выпусков .NET для Apache Spark в GitHub. Например, если у вас компьютер Windows и вы планируете использовать .NET Core, [загрузите выпуск netcoreapp 2.1 для Windows x64 ](https://github.com/dotnet/spark/releases/download/v0.5.0/Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip).

Для извлечения Microsoft.Spark.Worker:

* Найдите скачанный файл **Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip**.
* Щелкните правой кнопкой мыши и выберите **7-Zip -> Извлечь файлы…** .
* Введите **C:\bin** в поле **Извлечь в**.
* Снимите флажок под полем **Извлечь в**.
* Нажмите кнопку **ОК**.

![Установка .NET Spark](https://dotnet.microsoft.com/static/images/dotnet-for-spark-extract-with-7-zip.png?v=jwCyum9mL0mGIi4V5zC7yuvLfcj1_nL-QFFD8TClhZk)

### <a name="6-install-winutils"></a>6.  Установка WinUtils

.NET для Apache Spark требует установки WinUtils вместе с Apache Spark. [Скачайте winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe). Затем скопируйте WinUtils в папку **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.

> [!NOTE]
> Если вы используете другую версию Hadoop, которая указывается в конце имени папки установки Spark, [выберите версию WinUtils](https://github.com/steveloughran/winutils), совместимую с вашей версией Hadoop.

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a>7. Установка DOTNET_WORKER_DIR и проверка зависимостей

Выполните следующую команду, чтобы задать переменную среды `DOTNET_WORKER_DIR`, которая используется приложениями .NET для обнаружения .NET для Apache Spark:

`setx DOTNET_WORKER_DIR "C:\bin\Microsoft.Spark.Worker-0.6.0"`

Наконец, перед переходом к следующему разделу еще раз проверьте, можно ли выполнять команды `dotnet`, `java`, `mvn` и `spark-shell` из командной строки.

## <a name="write-a-net-for-apache-spark-app"></a>Написание приложения .NET для Apache Spark

### <a name="1-create-a-console-app"></a>1. Создание консольного приложения

В командной строке выполните следующие команды, чтобы создать новое консольное приложение:

```console
dotnet new console -o mySparkApp
cd mySparkApp
```

Команда `dotnet` создаст для вас приложение `new` типа `console`. Параметр `-o` создаст каталог с именем *mySparkApp*, в котором хранится приложение и используемые им файлы. Команда `cd mySparkApp` изменит каталог на только что созданный каталог приложения.

### <a name="2-install-nuget-package"></a>2. Установка пакета NuGet

Чтобы использовать .NET для Apache Spark в приложении, установите пакет Microsoft.Spark. В командной строке выполните следующую команду:

`dotnet add package Microsoft.Spark --version 0.6.0`

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
            var spark = SparkSession
                .Builder()
                .AppName("word_count_sample")
                .GetOrCreate();

            // Create initial DataFrame.
            DataFrame dataFrame = spark.Read().Text("input.txt");

            // Count words.
            var words = dataFrame
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

### <a name="4-add-data-file"></a>4. Добавление файла данных

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

   ```powershell
   %SPARK_HOME%\bin\spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local bin\Debug\netcoreapp3.0\microsoft-spark-2.4.x-0.6.0.jar dotnet bin\Debug\netcoreapp3.0\mySparkApp.dll
   ```

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
