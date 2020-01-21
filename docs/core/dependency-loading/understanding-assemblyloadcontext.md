---
title: Основные сведения об AssemblyLoadContext (.NET Core)
description: Основные концепции, позволяющие понять назначение и поведение AssemblyLoadContext в .NET Core.
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 8a73a432bf8cc72cced77cf6c62a785b72032913
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2019
ms.locfileid: "72303710"
---
# <a name="understanding-systemruntimeloaderassemblyloadcontext"></a>Основные сведения о System.Runtime.Loader.AssemblyLoadContext

Класс <xref:System.Runtime.Loader.AssemblyLoadContext> применяется только в .NET Core. Эта статья служит дополнением к документации по API <xref:System.Runtime.Loader.AssemblyLoadContext>, предоставляя сведения об используемых концепциях.

Эта статья важна для разработчиков, которые реализуют динамическую загрузку, особенно для разработчиков платформ динамической загрузки.

## <a name="what-is-the-assemblyloadcontext"></a>Что такое AssemblyLoadContext?

Каждое приложение .NET Core неявным образом использует <xref:System.Runtime.Loader.AssemblyLoadContext>.
Это поставщик среды выполнения для поиска и загрузки зависимостей. При каждой загрузке зависимости вызывается экземпляр <xref:System.Runtime.Loader.AssemblyLoadContext> для ее поиска.

- Он предоставляет службу поиска, загрузки и кэширования управляемых сборок и других зависимостей.

- Для поддержки динамической загрузки и выгрузки кода он создает изолированный контекст для загрузки кода и всех зависимостей в собственном экземпляре <xref:System.Runtime.Loader.AssemblyLoadContext>.

## <a name="when-do-you-need-multiple-assemblyloadcontext-instances"></a>Зачем может потребоваться несколько экземпляров AssemblyLoadContext?

Один экземпляр <xref:System.Runtime.Loader.AssemblyLoadContext> может загружать ровно одну версию <xref:System.Reflection.Assembly> для каждого простого имени сборки (<xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType>).

Это ограничение может стать проблемой при динамической загрузке модулей кода. Каждый модуль компилируется независимо от других и они могут зависеть от разных версий <xref:System.Reflection.Assembly>. Такая проблема часто возникает, когда разные модули зависят от разных версий широко используемой библиотеки.

Для поддержки динамической загрузки кода API <xref:System.Runtime.Loader.AssemblyLoadContext> предоставляет возможность загружать конфликтующие версии <xref:System.Reflection.Assembly> в одном приложении. Каждый экземпляр <xref:System.Runtime.Loader.AssemblyLoadContext> предоставляет уникальный словарь, который сопоставляет все <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> с конкретными экземплярами <xref:System.Reflection.Assembly>.

Он также поддерживает удобный механизм группирования зависимостей, связанных с модулем кода, для последующей выгрузки.

## <a name="what-is-special-about-the-assemblyloadcontextdefault-instance"></a>Что отличает экземпляр AssemblyLoadContext.Default?

Среда выполнения автоматически заполняет экземпляр <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> при запуске.  Он использует [стандартное зондирование](default-probing.md) для поиска и определения всех статических зависимостей.

Он реализует все самые распространенные сценарии загрузки зависимостей.

## <a name="how-does-assemblyloadcontext-support-dynamic-dependencies"></a>Как AssemblyLoadContext поддерживает динамические зависимости?

<xref:System.Runtime.Loader.AssemblyLoadContext> определяет несколько событий и виртуальных функций, которые можно переопределить.

Экземпляр <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> поддерживает переопределение только для событий.

Все доступные события и виртуальные функции описаны в статьях [ Алгоритм загрузки управляемых сборок](loading-managed.md), [Алгоритм загрузки вспомогательных сборок](loading-resources.md) и [Алгоритм загрузки неуправляемых (собственных) библиотек](loading-unmanaged.md).  В тех статьях указаны относительные положения всех событий и функций в алгоритмах загрузки. Мы не будем дублировать эту информацию в этой статье.

В этом разделе описаны общие принципы работы с соответствующими событиями и функциями.

- **Сохраняйте повторяемость**. Запрос к определенной зависимости должен всегда возвращать одинаковый ответ. Должен возвращаться один и тот же экземпляр загруженной зависимости. Это требование крайне важно для согласованности кэша. В частности, для управляемых сборок мы создаем кэш <xref:System.Reflection.Assembly>. Ключом этого кэша служит простое имя сборки (<xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType>).
- **Старайтесь не создавать исключений**.  Ожидается, что эти функции будут возвращать `null`, а не создавать исключения при отсутствии запрошенной зависимости. Исключения приводят к преждевременному завершению поиска и могут передаваться вызывающему объекту. Исключения следует применять только для непредвиденных ошибок, например при повреждении сборки или нехватке памяти.
- **Избегайте рекурсии**. Имейте в виду, что эти функции и обработчики реализуют правила загрузки для поиска зависимостей. Ваша реализация не должна вызывать API, так как это может привести к рекурсивному поиску. Обычно в этом коде следует вызывать функции загрузки из **AssemblyLoadContext**, которые ожидают аргумент с определенным путем или ссылкой на память.
- **Загружайте в правильный экземпляр AssemblyLoadContext**. Выбор мест для загрузки зависимостей зависит от конкретного приложения.  Такой выбор определяется именно этими событиями и функциями. Когда ваш код вызывает функции загрузки по пути из **AssemblyLoadContext**, их нужно вызывать именно из того экземпляра, в который вы намерены загрузить код. Иногда проще всего будет вернуть значение `null` и оставить обработку загрузки на усмотрение <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>.
- **Помните о проблемах состязания потоков.** Загрузка может инициироваться в нескольких потоках. AssemblyLoadContext избегает состязания потоков, атомарно добавляя сборку в свой кэш. Экземпляр проигравшего процесса просто отклоняется. Не добавляйте в вашу реализацию дополнительную логику, которая не поддерживает правильную работу с несколькими потоками.

## <a name="how-are-dynamic-dependencies-isolated"></a>Как изолируются динамические зависимости?

Каждый экземпляр <xref:System.Runtime.Loader.AssemblyLoadContext> представляет уникальную область для экземпляров <xref:System.Reflection.Assembly> и определений <xref:System.Type>.

Между этими зависимостями отсутствует двоичная изоляция. Они изолируются только тем, что не могут найти друга по имени.

Соответственно, в каждом <xref:System.Runtime.Loader.AssemblyLoadContext>:

- <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> может ссылаться на другой экземпляр <xref:System.Reflection.Assembly>;
- <xref:System.Type.GetType%2A?displayProperty=nameWithType> может возвращать другой экземпляр типа для того же типа `name`.

## <a name="how-are-dependencies-shared"></a>Как реализовано совместное использование зависимостей?

Зависимости можно совместно использовать в нескольких экземплярах <xref:System.Runtime.Loader.AssemblyLoadContext>. В общем случае зависимость загружает только один <xref:System.Runtime.Loader.AssemblyLoadContext>.  Другой использует ту же зависимость через ссылку на загруженную сборку.

Такой режим совместного использования обязателен для сборок среды выполнения. Такие сборки можно загружать только в <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>. Это же требование применимо к таким платформам, как `ASP.NET`, `WPF` или `WinForms`.

Мы рекомендуем всегда загружать общие зависимости в <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>. Совместное использование — широко распространенный конструктивный шаблон.

Совместное использование реализуется в коде пользовательского экземпляра <xref:System.Runtime.Loader.AssemblyLoadContext>. <xref:System.Runtime.Loader.AssemblyLoadContext> определяет несколько событий и виртуальных функций, которые можно переопределить. Когда любая из этих функций возвращает ссылку на экземпляр <xref:System.Reflection.Assembly>, который был загружен в другом экземпляре <xref:System.Runtime.Loader.AssemblyLoadContext>, такой экземпляр <xref:System.Reflection.Assembly> становится общим. Стандартный алгоритм загрузки оставляет загрузку на усмотрение <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>, чтобы упростить шаблон совместного доступа.  См. статью [Managed assembly loading algorithm](loading-managed.md) (Алгоритм загрузки управляемых сборок).

## <a name="complications"></a>Усложнения

### <a name="type-conversion-issues"></a>Проблемы с преобразованием типов

Если два экземпляра <xref:System.Runtime.Loader.AssemblyLoadContext> содержат определения типов с одинаковыми `name`, они считаются разными типами. Тип будет считаться одним и тем же только в том случае, если определения поступают из одного экземпляра <xref:System.Reflection.Assembly>.

Дополнительно ситуация осложняется непонятными сообщениями об исключениях, связанных с таким несовпадением типов. Эти типы упоминаются в сообщениях об исключениях только по простым именам. Типичное сообщение об исключении будет иметь такой вид:

> Невозможно преобразовать объект типа "IsolatedType" в тип "IsolatedType".

### <a name="debugging-type-conversion-issues"></a>Отладка проблем с преобразованием типов

При несовпадении двух типов важно получить следующие сведения:

- <xref:System.Type.Assembly?displayProperty=nameWithType> для каждого типа;
- <xref:System.Runtime.Loader.AssemblyLoadContext> для каждого типа, который можно получить через <xref:System.Runtime.Loader.AssemblyLoadContext.GetLoadContext(System.Reflection.Assembly)?displayProperty=nameWithType>.

При наличии двух объектов `a` и `b` будет полезно оценить в отладчике следующие данные:

```csharp
// In debugger look at each assembly's instance, Location, and FullName
a.GetType().Assembly
b.GetType().Assembly
// In debugger look at each AssemblyLoadContext's instance and name
System.Runtime.AssemblyLoadContext.GetLoadContext(a.GetType().Assembly)
System.Runtime.AssemblyLoadContext.GetLoadContext(b.GetType().Assembly)
```

### <a name="resolving-type-conversion-issues"></a>Устранение проблем с преобразованием типов

Для решения таких проблем с преобразованием типов существует два конструктивных шаблона.

1. Используйте общие стандартные типы. Такой общий тип может быть примитивным типом среды выполнения или включать создание нового общего типа в общей сборке.  Часто общий тип является [интерфейсом](../../csharp/language-reference/keywords/interface.md), определенным в сборке приложения. См. также: [Как реализовано совместное использование зависимостей?](#how-are-dependencies-shared)

2. Используйте технологию маршалинга для преобразования одного типа в другой.
