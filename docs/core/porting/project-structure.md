---
title: "Организация проекта для поддержки .NET Framework и .NET Core"
description: "Организация проекта для поддержки .NET Framework и .NET Core"
keywords: .NET, .NET Core
author: conniey
manager: wpickett
ms.date: 07/18/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 3af62252-1dfa-4336-8d2f-5cfdb57d7724
translationtype: Human Translation
ms.sourcegitcommit: 15c55a87beb64f265a164db918c7721c7690fadf
ms.openlocfilehash: ca63b25bb5f5e98167aaa8b74a7204fcd77b3523

---

# <a name="organizing-your-project-to-support-net-framework-and-net-core"></a>Организация проекта для поддержки .NET Framework и .NET Core

Эта статья призвана помочь владельцем проектов, которым требуется скомпилировать свои решения одновременно для .NET Framework и .NET Core.  В ней описываются несколько вариантов организации проектов, которые могут помочь разработчикам достичь этой цели.  Ниже приводятся несколько типичных сценариев, которые следует принять во внимание при выборе способа компоновки проекта с помощью .NET Core.  Они могут не охватывать все конкретные случаи.

* [**Объединение существующих проектов и проектов .NET Core в единые проекты**][option-xproj]
  
  *Преимущества*
  * Упрощение процесса сборки благодаря компиляции одного, а не нескольких проектов, каждый из которых предназначен для отдельной версии .NET Framework или платформы.
  * Упрощение управления файлами исходного кода для проектов, предназначенных для различных платформ, так как управлять приходится только одним файлом проекта.  При использовании альтернативных подходов добавление и удаление файлов исходного кода требует синхронизации этих изменений с другими проектами вручную.
  * Простое создание пакета NuGet для использования.
  * Позволяет писать код для конкретной версии .NET Framework в библиотеках посредством директив компилятора.
  
  *Неподдерживаемые сценарии*
  * Не позволяет разработчикам, не имеющим среды Visual Studio 2015, открывать существующие проекты. Для поддержки предыдущих версий Visual Studio лучше [хранить файлы проектов в разных папках](#support-vs).
  * Не позволяет совместно использовать библиотеку .NET Core в разных типах проектов в одном файле решения. Для поддержки такого сценария лучше [создать переносимую библиотеку классов](#support-pcl).
  * Не позволяет использовать модификации сборки или загрузки проекта, которые поддерживаются целями и задачами MSBuild. Для поддержки такого сценария лучше [создать переносимую библиотеку классов](#support-pcl).

* [**Разделяйте существующие проекты и новые проекты .NET Core**][option-xproj-folder]
  
  *Преимущества*
  * Продолжение работы над существующими проектами, причем разработчикам и участникам, у которых нет Visual Studio 2015, не нужно производить обновление.
  * Снижение вероятности появления новых ошибок в существующих проектах, так как в них не требуется обработка кода.

* [**Сохранение текущих проектов и создание переносимых библиотек классов (PCL), предназначенных для .NET Core**][option-pcl]

  *Преимущества*
  * Ссылки на библиотеки .NET Core в классических и веб-проектах, предназначенных для полной версии .NET Framework, в рамках одного решения.
  * Поддержка изменений в процессе сборки или загрузки проекта. Такими изменениями может быть включение задач и целей MSBuild в файл `*.csproj`.

  *Неподдерживаемые сценарии*
  * Не позволяет писать код для определенной версии .NET Framework, так как [предопределенные символы препроцессора][how-to-multitarget] не поддерживаются.

## <a name="example"></a>Пример

Рассмотрим показанный ниже репозиторий.

![Существующий проект][example-initial-project]

[**Исходный код**][example-initial-project-code]

В зависимости от ограничений и сложности существующих проектов добавить поддержку .NET Core для этого репозитория можно несколькими разными способами, описанными ниже.

## <a name="replace-existing-projects-with-a-multitargeted-net-core-project-xproj"></a>Замена существующих проектов проектом .NET Core (XPROJ), предназначенным для различных платформ

Репозиторий можно реорганизовать так, что все существующие файлы `*.csproj` будут удалены и будет создан единственный файл `*.xproj`, предназначенный для нескольких платформ.  Это удобно по той причине, что один проект можно компилировать для разных платформ.  Это также позволяет управлять различными параметрами компиляции, зависимостями и т. д. для каждой целевой платформы.

![Создание файла XPROJ, предназначенного для различных платформ][example-xproj]

[**Исходный код**][example-xproj-code]

Обратите внимание на следующие изменения:
* добавление `global.json`;
* замена `packages.config` и `*.csproj` на `project.json` и `*.xproj`;
* изменения в [файле project.json проекта Car][example-xproj-projectjson] и связанном с ним [тестовом проекте ][example-xproj-projectjson-test] с целью поддержки сборки для текущей платформы .NET Framework, а также других платформ.

## <a name="create-a-portable-class-library-pcl-to-target-net-core"></a>Создание переносимой библиотеки классов (PCL), предназначенной для .NET Core

Если существующие проекты содержат сложные операции или свойства сборки в файле `*.csproj`, может быть проще создать библиотеку PCL.

![][example-pcl]

[**Исходный код**][example-pcl-code]

Обратите внимание на следующие изменения:
*  Переименование `project.json` в `{project-name}.project.json`
    * Позволяет предотвратить возможный конфликт в Visual Studio при попытке восстановить пакеты для библиотек в том же каталоге. Дополнительные сведения см. на странице [вопросов и ответов по NuGet](https://docs.nuget.org/consume/nuget-faq#working-with-packages) в разделе _I have multiple projects in the same folder, how can I use separate packages.config or project.json files for each project?_ (У меня несколько проектов в одной папке. Как разделить файлы packages.config или project.json для каждого проекта?).
    *  **Альтернативный вариант**: создайте библиотеку PCL в другой папке и используйте ссылку на первоначальный исходный код, чтобы избежать этой проблемы.  Размещение библиотеки PCL в другой папке имеет дополнительное преимущество: пользователи, у которых нет Visual Studio 2015, могут по-прежнему работать со старыми проектами, не загружая новое решение.
*  Для нацеливания на .NET Standard после создания библиотеки PCL в Visual Studio откройте **свойства проекта**. В разделе **Целевые платформы** щелкните ссылку **Нацелить на стандартную платформу .NET**.  Чтобы отменить это изменение, выполните те же самые действия.

## <a name="keep-existing-projects-and-create-a-net-core-project"></a>Сохранение существующих проектов и создание проекта .NET Core

При наличии существующих проектов, предназначенных для более старых платформ, можно оставить эти проекты без изменения и использовать проект .NET Core для новых платформ.

![Проект .NET Core с существующей библиотекой PCL в другой папке][example-xproj-different-folder]

[**Исходный код**][example-xproj-different-code]

Обратите внимание на следующие изменения:
* Проект .NET Core и существующие проекты хранятся в разных папках.
    * Это позволяет избежать упомянутой выше проблемы при восстановлении пакетов, которая возникает из-за наличия нескольких файлов project.json или package.config в одной папке.
    * Хранение проектов в разных папках делает необязательным наличие Visual Studio 2015 (из-за использования файлов project.json).  Вы можете создать отдельное решение, которое открывает только старые проекты.

## <a name="see-also"></a>См. также

Дополнительные указания по переходу на использование файлов project.json и XPROJ см. в [документации по переносу в .NET Core][porting-doc].

[porting-doc]: index.md
[example-initial-project]: media/project-structure/project.png " Существующий проект"
[example-initial-project-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library/

[example-xproj]: media/project-structure/project.xproj.png " Создание файла XPROJ, предназначенного для различных платформ"
[example-xproj-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-xproj/
[example-xproj-projectjson]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-xproj/src/Car/project.json
[example-xproj-projectjson-test]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-xproj/tests/Car.Tests/project.json

[example-xproj-different-folder]: media/project-structure/project.xproj.different.png " Проект .NET Core с существующей библиотекой PCL в другой папке"
[example-xproj-different-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-xproj-keep-csproj/

[example-pcl]: media/project-structure/project.pcl.png " Библиотека PCL, предназначенная для .NET Core"
[example-pcl-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-pcl

[option-xproj]: #replace-existing-projects-with-a-multi-targeted-net-core-project-xproj
[option-pcl]: #create-a-portable-class-library-pcl-to-target-net-core
[option-xproj-folder]: #keep-existing-projects-and-create-a-net-core-project

[how-to-multitarget]: ../tutorials/libraries.md#how-to-multitarget



<!--HONumber=Nov16_HO1-->


