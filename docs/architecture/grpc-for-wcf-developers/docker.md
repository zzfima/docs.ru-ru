---
title: DOCKER-gRPC для разработчиков WCF
description: Создание образов DOCKER для ASP.NET Core приложений gRPC
ms.date: 09/02/2019
ms.openlocfilehash: d23dc46526183b459c36f11bae4def8b1c9b9410
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711297"
---
# <a name="create-docker-images"></a>Создание образов DOCKER

В этом разделе рассматриваются создание образов DOCKER для приложений ASP.NET Core gRPC, готовых к работе в DOCKER, Kubernetes или в других средах контейнеров. Пример приложения, используемый с веб-приложением ASP.NET Core MVC и службой gRPC, доступен в репозитории [DotNet-Architecture/gRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) на сайте GitHub.

## <a name="microsoft-base-images-for-aspnet-core-applications"></a>Базовые образы Майкрософт для приложений ASP.NET Core

Корпорация Майкрософт предоставляет ряд базовых образов для создания и запуска приложений .NET Core. Чтобы создать образ ASP.NET Core 3,0, используйте два базовых образа: 

- Образ пакета SDK для сборки и публикации приложения.
- Образ среды выполнения для развертывания.

| Изображение | Описание |
| ----- | ----------- |
| [mcr.microsoft.com/dotnet/core/sdk](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | Для создания приложений с `docker build`. Не для использования в рабочей среде. |
| [mcr.microsoft.com/dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | Содержит зависимости среды выполнения и ASP.NET Core. Для рабочей среды. |

Для каждого образа существует четыре варианта, основанные на разных дистрибутивах Linux, различающихся по тегам.

| Теги изображений | Linux | Примечания |
| --------- | ----- | ----- |
| 3,0-бустер, 3,0 | Debian 10 | Изображение по умолчанию, если не указан вариант ОС. |
| 3,0-Alpine | Alpine 3,9 | Базовые образы Alpine намного меньше, чем Debian или Ubuntu. |
| 3,0-Disco | Ubuntu 19.04 | |
| 3,0-Бионик | Ubuntu 18.04 | |

Базовый образ Alpine составляет около 100 МБ по сравнению с 200 МБ для образов Debian и Ubuntu. Некоторые программные пакеты или библиотеки могут быть недоступны в управлении пакетами Alpine. Если вы не знаете, какой образ следует использовать, то, вероятно, вам нужно выбрать Debian по умолчанию.

> [!IMPORTANT]
> Убедитесь, что для сборки и среды выполнения используется один и тот же вариант Linux. Приложения, созданные и опубликованные на одном варианте, могут не работать на другом.

## <a name="create-a-docker-image"></a>Создание образа DOCKER

Образ DOCKER определяется *Dockerfile*. Это текстовый файл, содержащий все команды, необходимые для создания приложения, и установки всех зависимостей, необходимых для сборки или запуска приложения. В следующем примере показан самый простой Dockerfile для приложения ASP.NET Core 3,0:

```dockerfile
# Application build steps
FROM mcr.microsoft.com/dotnet/core/sdk:3.0 as builder

WORKDIR /src

COPY . .

RUN dotnet restore

RUN dotnet publish -c Release -o /published src/StockData/StockData.csproj

# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=builder /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

Dockerfile состоит из двух частей: первый использует базовый образ `sdk` для сборки и публикации приложения; второй создает образ среды выполнения из базы `aspnet`. Это связано с тем, что `sdk` образ составляет около 900 МБ по сравнению с 200 МБ для образа среды выполнения, и большая часть его содержимого не требуется во время выполнения.

### <a name="the-build-steps"></a>Этапы сборки

| Шаг | Описание |
| ---- | ----------- |
| `FROM ...` | Объявляет базовый образ и назначает псевдоним `builder`. |
| `WORKDIR /src` | Создает `/src` каталог и задает его в качестве текущего рабочего каталога. |
| `COPY . .` | Копирует все, что находится под текущим каталогом на узле, в текущий каталог на образе. |
| `RUN dotnet restore` | Восстанавливает все внешние пакеты (ASP.NET Core 3,0 Framework предварительно устанавливается вместе с пакетом SDK). |
| `RUN dotnet publish ...` | Создает и публикует сборку выпуска. Обратите внимание, что флаг `--runtime` не требуется. |

### <a name="the-runtime-image-steps"></a>Шаги образа среды выполнения

| Шаг | Описание |
| ---- | ----------- |
| `FROM ...` | Объявляет новый базовый образ. |
| `WORKDIR /app` | Создает `/app` каталог и задает его в качестве текущего рабочего каталога. |
| `COPY --from=builder ...` | Копирует опубликованное приложение из предыдущего образа, используя псевдоним `builder` из первой строки `FROM`. |
| `ENTRYPOINT [ ... ]` | Задает выполнение команды при запуске контейнера. Команда `dotnet` в образе среды выполнения может запускать только DLL-файлы. |

### <a name="https-in-docker"></a>HTTPS в DOCKER

В базовых образах Майкрософт для DOCKER задается `http://+:80`переменной среды `ASPNETCORE_URLS`, что означает, что Kestrel выполняется без протокола HTTPS для этого порта. Если вы используете протокол HTTPS с пользовательским сертификатом (как описано в разделе Локальные [приложения gRPC](self-hosted.md)), его следует переопределить. Задайте переменную среды в части Dockerfile, созданной в образе среды выполнения.

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a>Файл dockerignore

Во многом подобно `.gitignore` файлам, которые исключают определенные файлы и каталоги из системы управления версиями, файл `.dockerignore` можно использовать для исключения копирования файлов и каталогов в образ во время сборки. Это не только экономит время, но и позволяет избежать некоторых ошибок, возникающих из `obj` каталога с компьютера, скопированного в образ. Как минимум, необходимо добавить записи для `bin` и `obj` в файл `.dockerignore`.

```console
bin/
obj/
```

## <a name="build-the-image"></a>Сборка образа

Для решения с одним приложением и, таким способом, одним Dockerfile, проще всего разместить Dockerfile в базовом каталоге. Иными словами, помещайте его в тот же каталог, что и файл `.sln`. В этом случае для создания образа используйте следующую команду `docker build` из каталога, содержащего Dockerfile.

```console
docker build --tag stockdata .
```

Непонятный именованный флаг `--tag` (который можно сократить до `-t`) задает полное имя изображения, включая фактический тег, если он указан. `.` в конце указывает контекст, в котором будет выполняться сборка. текущий рабочий каталог для команд `COPY` в Dockerfile.

При наличии нескольких приложений в одном решении можно разместить Dockerfile для каждого приложения в отдельной папке рядом с файлом `.csproj`. По-прежнему следует выполнять команду `docker build` из базового каталога, чтобы убедиться, что решение и все проекты скопированы в образ. Можно указать Dockerfile ниже текущего каталога с помощью флага `--file` (или `-f`).

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a>Запуск образа в контейнере на компьютере

Чтобы запустить образ в локальном экземпляре DOCKER, используйте команду `docker run`.

```console
docker run -ti -p 5000:80 stockdata
```

Флаг `-ti` подключает текущий терминал к терминалу контейнера и выполняется в интерактивном режиме. `-p 5000:80` публикует (ссылки) порт 80 в контейнере на порт 80 на сетевом интерфейсе localhost.

## <a name="push-the-image-to-a-registry"></a>Отправка образа в реестр

Убедившись, что образ работает, отправьте его в реестр DOCKER, чтобы сделать доступным в других системах. Внутренним сетям потребуется подготавливать реестр DOCKER. Это может быть так же просто, как и [собственный образ docker `registry`](https://docs.docker.com/registry/deploying/) (реестр DOCKER выполняется в контейнере DOCKER), но доступны различные более комплексные решения. Для внешнего общего доступа и использования в облаке доступны различные управляемые реестры, такие как [Реестр контейнеров Azure](https://docs.microsoft.com/azure/container-registry/) или [DOCKER Hub](https://docs.docker.com/docker-hub/repos/).

Чтобы отправить в центр DOCKER, перед именем образа необходимо указать имя пользователя или организации.

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

Чтобы отправить в частный реестр, добавьте перед именем образа имя узла реестра и имя Организации.

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

После того как образ находится в реестре, его можно развернуть на отдельных узлах DOCKER или в подсистеме оркестрации контейнеров, например Kubernetes.

>[!div class="step-by-step"]
>[Назад](self-hosted.md)
>[Вперед](kubernetes.md)
