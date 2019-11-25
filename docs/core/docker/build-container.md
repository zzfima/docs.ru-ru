---
title: Руководство "Контейнеризация приложений с помощью Docker"
description: Из этого руководства вы узнаете, как контейнеризировать приложение .NET Core с помощью Docker.
ms.date: 06/26/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: b344731c7d356f3705d9909b6901234f91ec7d6d
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72521886"
---
# <a name="tutorial-containerize-a-net-core-app"></a>Учебник. Контейнеризация приложения .NET Core

В этом руководстве показано, как создать образ Docker, содержащий приложение .NET Core. Этот образ можно использовать для создания контейнеров в вашей локальной среде разработки, частном или общедоступном облаке.

Вы узнаете, как:

> [!div class="checklist"]
>
> - создать и опубликовать простое приложение .NET Core;
> - создать и настроить Dockerfile для .NET Core;
> - Создание образа Docker
> - создать и запустить контейнер Docker.

Вы также узнаете о задачах сборки и развертывания контейнера Docker для приложения .NET Core. *Платформа Docker* использует *модуль Docker* для быстрой сборки и упаковки приложений в качестве *образов Docker*. Эти образы имеют формат *Dockerfile* и предназначены для развертывания и запуска в многоуровневом контейнере.

## <a name="prerequisites"></a>Предварительные требования

Установите следующие необходимые компоненты:

- [Пакет .NET для Core версии 2.2](https://dotnet.microsoft.com/download)\.
Если у вас установлена платформа .NET Core, воспользуйтесь командой `dotnet --info`, чтобы определить версию пакета SDK.

- [Docker Community Edition](https://www.docker.com/products/docker-desktop).

- Временная рабочая папка для *Dockerfile* и примера приложения .NET Core. В этом руководстве имя `docker-working` используется в качестве рабочей папки.

### <a name="use-sdk-version-22"></a>Использование пакета SDK версии 2.2

Если вы работаете с пакетом SDK более новой версии (например, 3.0), убедитесь, что приложение использует версию 2.2. Создайте файл с именем *global.json* в рабочей папке и вставьте в него следующий код JSON:

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

Сохраните этот файл. При наличии такого файла .NET Core будет использовать версию 2.2 для всех команд `dotnet`, вызванных из этого каталога и его подкаталогов.

## <a name="create-net-core-app"></a>Создание приложения .NET Core

Вам нужно создать приложение .NET Core для выполнения контейнера Docker. Откройте терминал, создайте рабочую папку, если вы еще этого не сделали, и войдите в нее. Выполните следующую команду в рабочей папке, чтобы создать проект во вложенной папке с именем *app*:

```dotnetcli
dotnet new console -o app -n myapp
```

Дерево папок будет выглядеть следующим образом:

```
docker-working
│   global.json
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    └───obj
            myapp.csproj.nuget.cache
            myapp.csproj.nuget.g.props
            myapp.csproj.nuget.g.targets
            project.assets.json
```

Команда `dotnet new` создает папку с именем *app* и приложение Hello World. Войдите в папку *app* и выполните команду `dotnet run`. Вы увидите следующие выходные данные:

```console
> dotnet run
Hello World!
```

Шаблон по умолчанию создает приложение, которое выводит текст в терминал и затем завершает работу. В этом руководстве описано, как использовать приложение с бесконечным циклом выполнения. Откройте файл *Program.cs* в текстовом редакторе. Файл должен содержать следующий код:

```csharp
using System;

namespace myapp
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

Замените его кодом, который считает числа каждую секунду:

```csharp
using System;

namespace myapp
{
    class Program
    {
        static void Main(string[] args)
        {
            var counter = 0;
            var max = args.Length != 0 ? Convert.ToInt32(args[0]) : -1;
            while (max == -1 || counter < max)
            {
                counter++;
                Console.WriteLine($"Counter: {counter}");
                System.Threading.Tasks.Task.Delay(1000).Wait();
            }
        }
    }
}
```

Сохраните файл и протестируйте программу еще раз с помощью команды `dotnet run`. Помните, что это приложение выполняется бесконечно. Остановите его с помощью команды отмены, нажав клавиши <kbd>CTRL</kbd>+<kbd>C</kbd>. Вы увидите следующие выходные данные:

```console
> dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

Если приложению передать число в командной строке, оно досчитает до такого числа и завершит работу. Введите команду `dotnet run -- 5`, чтобы приложение досчитало до пяти.

> [!NOTE]
> Все параметры после `--` не передаются команде `dotnet run`, а передаются в приложение.

## <a name="publish-net-core-app"></a>Публикация приложения .NET Core

Прежде чем добавить приложение .NET Core в образ Docker, опубликуйте его. Убедитесь, что выполняемый контейнер запускает опубликованную версию приложения.

Из рабочей папки перейдите в папку *app* с примером исходного кода и выполните следующую команду:

```dotnetcli
dotnet publish -c Release
```

Эта команда компилирует приложение и помещает результат в папку *publish*. Путь к папке *publish* из рабочей папки должен быть таким: `.\app\bin\Release\netcoreapp2.2\publish\`

Получите список файлов для папки publish, чтобы убедиться в наличии файла *myapp.dll*. Из папки *app* выполните одну из следующих команд:

```console
> dir bin\Release\netcoreapp2.2\publish
 Directory of C:\docker-working\app\bin\Release\netcoreapp2.2\publish

04/05/2019  11:00 AM    <DIR>          .
04/05/2019  11:00 AM    <DIR>          ..
04/05/2019  11:00 AM               447 myapp.deps.json
04/05/2019  11:00 AM             4,608 myapp.dll
04/05/2019  11:00 AM               448 myapp.pdb
04/05/2019  11:00 AM               154 myapp.runtimeconfig.json
```

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/netcoreapp2.2/publish
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
```

## <a name="create-the-dockerfile"></a>Создание файла Dockerfile

Файл *Dockerfile* используется командой `docker build` для создания образа контейнера. Это текстовый файл с именем *Dockerfile* и без расширения.

В окне терминала перейдите к каталогу на один уровень выше рабочей папки, созданной ранее. Создайте файл с именем *Dockerfile* в рабочей папке и откройте его в текстовом редакторе. Добавьте следующую команду в первую строку файла:

```dockerfile
FROM mcr.microsoft.com/dotnet/core/runtime:2.2
```

Команда `FROM` указывает Docker вызвать образ с тегом **2.2** из репозитория **mcr.microsoft.com/dotnet/core/runtime**. Убедитесь, что вы вызываете среду выполнения .NET Core, версия которой соответствует версии среды выполнения, с которой работает пакет SDK. Например, приложение, созданное в предыдущем разделе, использует пакет SDK для .NET Core версии 2.2. Также было создано приложение для .NET Core 2.2. Поэтому базовый образ, который указан в файле *Dockerfile*, должен иметь тег **2.2**.

Сохраните файл *Dockerfile*. Структура каталогов рабочей папки должна выглядеть следующим образом. Некоторые файлы и папки на более глубоком уровне были вырезаны для экономии места в статье:

```
docker-working
│   Dockerfile
│   global.json
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    ├───bin
    │   └───Release
    │       └───netcoreapp2.2
    │           └───publish
    │                   myapp.deps.json
    │                   myapp.dll
    │                   myapp.pdb
    │                   myapp.runtimeconfig.json
    │
    └───obj
```

В терминале выполните следующую команду:

```console
docker build -t myimage -f Dockerfile .
```

Docker обработает все строки файла *Dockerfile*. Символ `.` в команде `docker build` используется, чтобы выполнить с помощью Docker поиск файла *Dockerfile* в текущей папке. Эта команда создает образ и локальный репозиторий с именем **myimage**, который указывает на такой образ. После завершения работы этой команды выполните команду `docker images`, чтобы просмотреть список установленных образов:

```console
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
myimage                                 latest              d51bb4452469        2 days ago          314MB
```

Обратите внимание, что два образа имеют одинаковое значение **IMAGE ID**. Это связано с тем, что единственная команда в файле *Dockerfile* создает новый образ на основе существующего. Добавим в файл *Dockerfile* еще две команды. Каждая команда создает новый уровень образа, а последняя команда представляет образ, на который будет указывать репозиторий **myimage**.

```dockerfile
COPY app/bin/Release/netcoreapp2.2/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

Команда `COPY` предписывает Docker скопировать указанную папку на вашем компьютере в папку в контейнере. В этом примере папка *publish* копируется в папку с именем *app* в контейнере.

Следующая команда `ENTRYPOINT` используется, чтобы настроить с помощью Docker контейнер для запуска в качестве исполняемого файла. При запуске контейнера выполняется команда `ENTRYPOINT`. После выполнения команды контейнер автоматически остановится.

В окне терминала выполните команду `docker build -t myimage -f Dockerfile .`, а после ее выполнения — команду `docker images`.

```console
> docker build -t myimage -f Dockerfile .
Sending build context to Docker daemon  819.7kB
Step 1/3 : FROM mcr.microsoft.com/dotnet/core/runtime:2.2
 ---> d51bb4452469
Step 2/3 : COPY app/bin/Release/netcoreapp2.2/publish/ app/
 ---> a1e98ac62017
Step 3/3 : ENTRYPOINT ["dotnet", "app/myapp.dll"]
 ---> Running in f34da5c18e7c
Removing intermediate container f34da5c18e7c
 ---> ddcc6646461b
Successfully built ddcc6646461b
Successfully tagged myimage:latest

> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              ddcc6646461b        10 seconds ago      314MB
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
```

Каждая команда в файле *Dockerfile* создает уровень и экземпляр **IMAGE ID**. Последний экземпляр **IMAGE ID** (ваш идентификатор будет отличаться) имеет значение **ddcc6646461b**. Теперь вы создадите контейнер на основе этого образа.

## <a name="create-a-container"></a>Создание контейнера

Теперь, когда у вас есть образ, содержащий приложение, вы можете создать контейнер. Контейнер можно создать двумя способами. Сначала создайте остановленный контейнер.

```console
> docker create myimage
0e8f3c2ca32ce773712a5cca38750f41259a4e54e04bdf0946087e230ad7066c
```

Команда `docker create` выше создает контейнер на основе образа **myimage**. В выходных данных этой команды присутствует **CONTAINER ID** (ваш идентификатор будет отличаться) созданного контейнера. Чтобы просмотреть список *всех* контейнеров, воспользуйтесь командой `docker ps -a`:

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               boring_matsumoto
```

### <a name="manage-the-container"></a>Управление контейнером

Каждому контейнеру присваивается случайное имя, с помощью которого можно обращаться к этому экземпляру контейнера. Например, созданный автоматически контейнер получил имя **boring_matsumoto** (имя вашего контейнера будет отличаться), которое можно использовать для запуска контейнера. Чтобы переопределить автоматически созданное имя и указать другое, используйте параметр `docker create --name`.

В следующем примере используется команда `docker start` для запуска контейнера, а затем — команда `docker ps` для отображения только запущенных контейнеров:

```console
> docker start boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           boring_matsumoto
```

Аналогично, команда `docker stop` останавливает контейнер. В следующем примере используется команда `docker stop` для остановки контейнера, а затем — команда `docker ps` для подтверждения того, что контейнеры не запущены:

```console
> docker stop boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a>Подключение к контейнеру

После запуска контейнера вы можете подключиться к нему, чтобы просмотреть выходные данные. С помощью команд `docker start` и `docker attach` запустите контейнер и просмотрите поток вывода. В этом примере команда, вызываемая нажатием клавиш <kbd>CTRL+C</kbd>, используется для отключения от запущенного контейнера. Это может привести к завершению процесса в контейнере и его последующей остановке. Параметр `--sig-proxy=false` гарантирует, что команда, вызываемая нажатием клавиш <kbd>CTRL+C</kbd>, не остановит процесс в контейнере.

После отключения от контейнера снова подключитесь к нему, чтобы убедиться в том, что он продолжает работать и считать числа.

```console
> docker start boring_matsumoto
boring_matsumoto

> docker attach --sig-proxy=false boring_matsumoto
Counter: 7
Counter: 8
Counter: 9
^C

> docker attach --sig-proxy=false boring_matsumoto
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a>Удаление контейнера

В рамках этого руководства предполагается, что вам не нужны контейнеры, которые запущены, но не выполняют полезные действия. Удалите созданный ранее контейнер. Если контейнер запущен, остановите его.

```console
> docker stop boring_matsumoto
```

В примере ниже выводится список всех контейнеров, а затем используется команда `docker rm` для удаления контейнера. После этого выполняется повторная проверка наличия запущенных контейнеров.

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             boring_matsumoto

> docker rm boring_matsumoto
boring_matsumoto

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a>Однократный запуск

Docker предоставляет единую команду `docker run` для создания и запуска контейнера. Она исключает необходимость в поочередном выполнении команд `docker create` и `docker start`. Вы также можете настроить ее для автоматического удаления контейнера при его остановке. Например, команда `docker run -it --rm` выполняет две операции. Сначала она автоматически подключается к контейнеру с помощью текущего терминала, а потом, после завершения работы контейнера, удаляет его:

```console
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

Во время выполнения `docker run -it` команда, вызываемая нажатием клавиш <kbd>CTRL+C</kbd>, остановит процесс, запущенный в контейнере. А это в свою очередь приведет к остановке контейнера. Так как в команде указан параметр `--rm`, контейнер автоматически удалится после остановки процесса. Убедитесь, что он больше не существует:

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a>Изменение команды ENTRYPOINT

Команда `docker run` также позволяет изменить команду `ENTRYPOINT` из файла *Dockerfile* для запуска другой программы, но только для соответствующего контейнера. Например, воспользуйтесь указанной ниже командой, чтобы запустить `bash` или `cmd.exe`. При необходимости измените команду.

#### <a name="windows"></a>Windows

В этом примере команда `ENTRYPOINT` изменена на `cmd.exe`. Нажав клавиши <kbd>CTRL</kbd>+<kbd>C</kbd>, вы можете завершить процесс и остановить контейнер.

```console
> docker run -it --rm --entrypoint "cmd.exe" myimage

Microsoft Windows [Version 10.0.17763.379]
(c) 2018 Microsoft Corporation. All rights reserved.

C:\>dir
 Volume in drive C has no label.
 Volume Serial Number is 3005-1E84

 Directory of C:\

04/09/2019  08:46 AM    <DIR>          app
03/07/2019  10:25 AM             5,510 License.txt
04/02/2019  01:35 PM    <DIR>          Program Files
04/09/2019  01:06 PM    <DIR>          Users
04/02/2019  01:35 PM    <DIR>          Windows
               1 File(s)          5,510 bytes
               4 Dir(s)  21,246,517,248 bytes free

C:\>^C
```

#### <a name="linux"></a>Linux

В этом примере команда `ENTRYPOINT` изменена на `bash`. Команда `quit` позволяет завершить процесс и остановить контейнер.

```bash
root@user:~# docker run -it --rm --entrypoint "bash" myimage
root@8515e897c893:/# ls app
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
root@8515e897c893:/# exit
exit
```

## <a name="essential-commands"></a>Основные команды

Docker предоставляет множество команд для операций с контейнером и образами. Для управления контейнерами в основном используются такие команды Docker:

- [docker build](https://docs.docker.com/engine/reference/commandline/build/)
- [docker run](https://docs.docker.com/engine/reference/commandline/run/)
- [docker ps](https://docs.docker.com/engine/reference/commandline/ps/)
- [docker stop](https://docs.docker.com/engine/reference/commandline/stop/)
- [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
- [docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)
- [docker image](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a>Очистка ресурсов

В этом руководстве описано, как создать контейнеры и образы. При желании эти ресурсы можно удалить. Ниже представлены команды, которые позволяют сделать следующее:

01. Вывести список всех контейнеров.

    ```console
    > docker ps -a
    ```

02. Остановить запущенные контейнеры. `CONTAINER_NAME` представляет имя, автоматически назначаемое контейнеру.

    ```console
    > docker stop CONTAINER_NAME
    ```

03. Удалить контейнер.

    ```console
    > docker rm CONTAINER_NAME
    ```

Затем удалите все ненужные образы на компьютере. Удалите образ, созданный с помощью файла *Dockerfile*, а затем удалите образ .NET Core, на основе которого был создан файл *Dockerfile*. Вы можете использовать значение **IMAGE ID** или строку в формате **РЕПОЗИТОРИЙ:МЕТКА**.

```console
docker rmi myimage:latest
docker rmi mcr.microsoft.com/dotnet/core/runtime:2.2
```

С помощью команды `docker images` просмотрите список установленных образов.

> [!NOTE]
> Файлы образов могут иметь большой размер. Как правило, удаляются временные контейнеры, созданные в ходе тестирования и разработки приложения. При этом рекомендуется оставить базовые образы с установленной средой выполнения, если на ее основе вы планируете создавать другие образы.

## <a name="next-steps"></a>Следующие шаги

- [Изучите руководство по микрослужбам ASP.NET Core.](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
- [Узнайте больше о службах Azure, которые поддерживают контейнеры.](https://azure.microsoft.com/overview/containers/)
- [Ознакомьтесь с командами Dockerfile.](https://docs.docker.com/engine/reference/builder/)
- [Изучите инструменты Visual Studio для контейнеров](/visualstudio/containers/overview)
