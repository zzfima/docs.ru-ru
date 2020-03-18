---
ms.openlocfilehash: 99153bb9cf3287951a1e52e716c799ee64eb82ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78950991"
---
# <a name="labels-and-projects-roadmap"></a>Стратегия применения меток и проектов

Группа по работе с документацией по .NET широко применяет в своей работе [метки GitHub](https://github.com/dotnet/docs/labels). Фильтрами по комбинациям меток мы можем быстро выбрать интересующие нас разделы на [веб-сайте документации по .NET](https://docs.microsoft.com/dotnet).

Мы также используем [проекты GitHub](https://github.com/dotnet/docs/projects) для организации спринтов и других групп задач для достижения конкретной цели.

В этой стратегии объясняется, как мы используем эти организационные средства, а также есть ссылки на удобные фильтры по некоторым важным областям.

## <a name="labels"></a>Подписи

Если вы впервые участвуете в работе c [dotnet/docs](https://github.com/dotnet/docs), начните со списка проблем [up-for-grabs](https://github.com/dotnet/docs/labels/up-for-grabs). В него включены проблемы с довольно узкой областью. Это отличный путь для первого вклада в работу. В представлении "up-for-grabs" вы можете отфильтровать проблемы по областям и приоритетам. Проблемы, которые хорошо подходят для начинающих, мы обозначаем меткой [good-first-issue](https://github.com/dotnet/docs/labels/good-first-issue), и они помогут вам внести первый небольшой вклад.

Мы используем метки для классификации проблем несколькими способами:

- [руководства по .NET](#find-a-single-net-guide) и [разделы руководства](#search-one-section-of-a-guide);
- [целевые выпуски](#releases);
- [Приоритет](#priority)

Объединяя метки из каждого набора (руководство, выпуск, приоритет), вы можете создать узкие срезы для поиска проблем, с которыми вы намерены работать.

### <a name="find-a-single-net-guide"></a>Поиск конкретного руководства по .NET

Мы используем метки для каждой из электронных книг по архитектуре и для каждого руководства по .NET.

![:book: руководство на светло-зеленом фоне](./images/guide.png "Префикс для меток руководств по архитектуре")

Электронные книги по архитектуре обозначаются префиксом `:book: guide` и имеют светло-зеленый фон. Это развернутые описания, относящиеся к рекомендуемой архитектуре. Вот пример списка текущих проблем, которые отфильтрованы по каждому из руководств по архитектуре .NET.

- [Веб-приложения ASP.NET Core](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20ASP.NET%20Core%20web%20apps)
- [Blazor](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Blazor)
- [Полностью облачные](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Cloud%20Native)
- [Жизненный цикл Docker](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Docker%20lifecycle)
- [gRPC](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20gRPC)
- [Модернизация с помощью контейнеров Windows](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Modernizing%20w%2F%20Windows%20containers)
- [Микрослужбы .NET](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20.NET%20Microservices)
- [Бессерверные приложения](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Serverless%20apps)

Этот же стиль меток применяется к [рекомендациям по проектированию платформы](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Framework%20Design%20Guidelines). Для этой области используется та же структура меток, но запросы на вытягивание от сообщества здесь не рекомендуются. Эти материалы переиздаются по индивидуальным разрешениям и не должны редактироваться.

![:books: Область на темно-синем фоне](./images/area.png "Префикс для меток области руководства по .NET")

Каждое из руководств по .NET обозначено префиксом `:books: Area` и имеет темно-синий фон. Вот пример списка текущих проблем, которые отфильтрованы по каждому из руководств .NET.

- [Справочник по интерфейсам API](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20API%20Reference)
- [Пакет SDK Azure для .NET](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Azure%20.NET%20SDk)
- [Руководство по языку C#](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20C%23%20Guide)
- [Руководство по классическим приложениям](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Desktop%20Guide)
- [Руководство по языку F#](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20F%23%20Guide)
- [Руководство по ML.NET](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20ML.NET%20Guide)
- [Руководство по архитектуре .NET](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Architecture%20Guide) — может быть удалено
- [Руководство по .NET Core](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Core%20Guide)
- [Руководство по .NET для Apache Spark](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20for%20Apache%20Spark%20Guide)
- [Руководство по .NET Framework](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Framework%20Guide)
- [Руководство по .NET](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Guide)
- [Справочник по API Roslyn](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Roslyn%20API%20Reference) — может быть удален.
- [Руководство по Visual Basic](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Visual%20Basic%20Guide)

#### <a name="search-one-section-of-a-guide"></a>Поиск по одному разделу руководства

![:card_file_box: Область на светло-синем фоне](./images/technology.png "Префикс для меток вложенных областей руководства по .NET")

Руководства по .NET достаточно большие, а эти метки позволяют дополнительно ограничить область поиска конкретным разделом руководства. Каждая из вложенных областей руководств по .NET обозначено префиксом `:card_file_box: Technology` и имеет светло-синий фон. Многие из этих меток применяются к нескольким руководствам, а другие — только к одному из них. Применив фильтр по области, добавьте одну из этих меток, чтобы ограничить область поиска проблем.

- AppCompat
- Асинхронная задача
- Дополнительные возможности C#
- Компилятор C#
- Основы C#
- Начало работы с C#
- Справочник по языку C#
- Безопасность значений NULL в C#
- Новые возможности C#
- CLI
- Доступ к данным
- Docker
- Установщики
- LINQ
- NCL
- .NET Standard
- API Roslyn
- Безопасность
- WCF
- WF
- WIF
- WinForms
- WPF

### <a name="releases"></a>Выпуски

![:checkered_flag: Выпуск на темно-желтом фоне](./images/release.png "Префикс для меток выпуска")

Проблемы, помеченные для конкретного выпуска, обозначаются префиксом `:checkered_flag: Release:` и отображаются на темно-желтом фоне.

- .NET Core 2.2
- .NET Core 3.0

### <a name="priority"></a>Priority

Метки приоритета содержат символ `P`, за которым следует одна цифра. Чем меньше число, тем выше приоритет.

- P0
- P1
- P2

### <a name="what-about-the-other-labels"></a>Какие еще бывают метки?

Группы по работе над содержимым используют много других меток для управления разными классификациями проблем. Если вы не входите в такую группу, остальные метки можно смело игнорировать.

## <a name="projects"></a>Проекты

Желающим внести вклад следует ознакомиться со статьей [Проекты для участников сообщества .NET](https://github.com/dotnet/docs/projects/35). Мы создали несколько колонок по обслуживанию, обновлению документации и задач по созданию содержимого. Возможно, так вам будет удобно найти интересные задачи. (Обратите внимание, что представление проектов можно отфильтровать по описанным выше меткам.)

У нас есть еще два способа применения проектов.

- Типы проектов по месяцам и годам. Выполняют роль досок Scrum для рабочего плана по каждому месяцу.
- Группы продолжительных задач. Используются для упорядочения задач, направленных на конкретную цель, если общий объем работ рассчитан на нескольких месяцев.
