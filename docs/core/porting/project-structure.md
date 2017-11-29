---
title: "Организация проекта для поддержки .NET Framework и .NET Core"
description: "Эта статья поможет владельцам проектов, которые хотят скомпилировать свое решение одновременно для .NET Framework и .NET Core."
keywords: ".NET, .NET Core, .NET Framework, макет проекта, поддержка нескольких платформ"
author: conniey
ms.author: mairaw
ms.date: 04/06/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 3af62252-1dfa-4336-8d2f-5cfdb57d7724
ms.openlocfilehash: 93bec65e3bbee93855d6f5bce5e2d6cea8bb9f3d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="organizing-your-project-to-support-net-framework-and-net-core"></a>Организация проекта для поддержки .NET Framework и .NET Core

Эта статья поможет владельцам проектов, которые хотят скомпилировать свое решение одновременно для .NET Framework и .NET Core. В ней описываются несколько вариантов организации проектов, которые могут помочь разработчикам достичь этой цели. Следующий список содержит несколько типичных сценариев, которые следует принимать во внимание при выборе макета проекта .NET Core. Этот список может охватывать не все необходимые случаи. Устанавливайте приоритеты в зависимости от потребностей вашего проекта.

* [**Объединение существующих проектов и проектов .NET Core в единые проекты**][option-csproj]

  *Преимущества*
  * Упрощение процесса сборки благодаря компиляции одного, а не нескольких проектов, каждый из которых предназначен для отдельной версии .NET Framework или платформы.
  * Упрощение управления файлами исходного кода для проектов, предназначенных для различных платформ, благодаря тому, что вам приходится управлять только одним файлом проекта. При использовании альтернативных подходов добавление и удаление файлов исходного кода требует синхронизации этих изменений с другими проектами вручную.
  * Простое создание пакета NuGet для использования.
  * Позволяет писать код для конкретной версии .NET Framework в библиотеках посредством директив компилятора.

  *Неподдерживаемые сценарии*
  * Для открытия существующих проектов разработчики должны использовать Visual Studio 2017. Для поддержки предыдущих версий Visual Studio лучше [хранить файлы проектов в разных папках](#support-vs).

* <a name="support-vs"></a>[**Разделение существующих и новых проектов .NET Core**][option-csproj-folder]

  *Преимущества*
  * Продолжение работы над существующими проектами для разработчиков и участников, у которых нет Visual Studio 2017.
  * Снижение вероятности появления новых ошибок в существующих проектах, так как не требуется обработка кода.

## <a name="example"></a>Пример

Рассмотрим показанный ниже репозиторий.

![Существующий проект][example-initial-project]

[**Исходный код**][example-initial-project-code]

В зависимости от ограничений и сложности существующих проектов добавить поддержку .NET Core для этого репозитория можно несколькими способами, которые описаны ниже.

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a>Замена существующих проектов на проект .NET Core, предназначенный для нескольких платформ

Измените файлы в репозитории, удалив все существующие файлы *\*.csproj* и создав единственный файл *\*.csproj*, предназначенный для нескольких платформ. Это удобно по той причине, что один проект можно компилировать для разных платформ. Это также позволяет управлять различными параметрами компиляции и зависимостями для каждой целевой платформы.

![Создание файла CSPROJ, предназначенного для нескольких платформ][example-csproj]

[**Исходный код**][example-csproj-code]

Обратите внимание на следующие изменения:
* Замена файлов *packages.config* и *\*.csproj* на новый файл [.NET Core*\*.csproj*][example-csproj-netcore]. Пакеты NuGet указываются с помощью `<PackageReference> ItemGroup`.

## <a name="keep-existing-projects-and-create-a-net-core-project"></a>Сохранение существующих проектов и создание проекта .NET Core

При наличии существующих проектов, предназначенных для более старых платформ, можно оставить эти проекты без изменения и использовать проект .NET Core для новых платформ.

![Проект .NET Core с существующим проектом в другой папке][example-csproj-different-folder]

[**Исходный код**][example-csproj-different-code]

Обратите внимание на следующие изменения:
* Проект .NET Core и существующие проекты хранятся в разных папках.
    * Размещение проектов в разных папках позволяет обойтись без Visual Studio 2017. Вы можете создать отдельное решение, которое открывает только старые проекты.

## <a name="see-also"></a>См. также

Дополнительные указания по переходу на .NET Core [документации по переходу на .NET Core][porting-doc].

[porting-doc]: index.md
[example-initial-project]: media/project-structure/project.png "Существующий проект"
[example-initial-project-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library/

[example-csproj]: media/project-structure/project.csproj.png "Создание файла CSPROJ, предназначенного для нескольких платформ"
[example-csproj-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-csproj/
[example-csproj-netcore]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-csproj/src/Car/Car.csproj

[example-csproj-different-folder]: media/project-structure/project.csproj.different.png "Проект .NET Core с существующей библиотекой PCL в другой папке"
[example-csproj-different-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-csproj-keep-existing/

[option-csproj]: #replace-existing-projects-with-a-multi-targeted-net-core-project
[option-csproj-folder]: #keep-existing-projects-and-create-a-net-core-project
