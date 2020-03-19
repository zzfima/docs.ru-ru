---
title: Алгоритм загрузки управляемых сборок (.NET Core)
description: Подробный алгоритм загрузки управляемых сборок в .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 312a320676be6eb453697e0704ab771a6707618b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "73973498"
---
# <a name="managed-assembly-loading-algorithm"></a>Алгоритм загрузки управляемых сборок

Управляемые сборки обнаруживаются и загружаются по специальному алгоритму, который состоит из нескольких этапов.

Для всех управляемых сборок, за исключением вспомогательных сборок и сборок `WinRT`, используется один и тот же алгоритм.

## <a name="when-are-managed-assemblies-loaded"></a>Когда загружаются управляемые сборки?

Чаще всего загрузку управляемой сборки активирует статическая ссылка на сборку. Эти ссылки добавляются в компилятор каждый раз, когда код обращается к типу, который определен в другой сборке. Такие сборки среда выполнения загружает (`load-by-name`) по мере необходимости.

Прямое использование конкретных интерфейсов API также приведет к загрузке сборки:

|API  |Описание  |`Active` <xref:System.Runtime.Loader.AssemblyLoadContext> |
|---------|---------|---------|
|<xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromAssemblyName%2A?displayProperty=nameWithType>|`Load-by-name`|Экземпляр [this](../../csharp/language-reference/keywords/this.md).|
|<xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromAssemblyPath%2A?displayProperty=nameWithType><p><xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromNativeImagePath%2A?displayProperty=nameWithType>|Загрузка на основе пути.|Экземпляр [this](../../csharp/language-reference/keywords/this.md).|
<xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromStream%2A?displayProperty=nameWithType>|Загрузка из объекта.|Экземпляр [this](../../csharp/language-reference/keywords/this.md).|
|<xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType>|Загрузка на основе пути в новый экземпляр <xref:System.Runtime.Loader.AssemblyLoadContext>.|Новый экземпляр <xref:System.Runtime.Loader.AssemblyLoadContext>.|
<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>|Загрузка на основе пути в новый экземпляр <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>.<p>Добавляет обработчик <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving> в <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>. Обработчик загрузит зависимости сборки из своего каталога.|Экземпляр класса <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>.|
|<xref:System.Reflection.Assembly.Load(System.Reflection.AssemblyName)?displayProperty=nameWithType><p><xref:System.Reflection.Assembly.Load(System.String)?displayProperty=nameWithType><p><xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>|`Load-by-name`.|Выводится из вызывающего объекта.<p>Лучше использовать методы <xref:System.Runtime.Loader.AssemblyLoadContext>.|
|<xref:System.Reflection.Assembly.Load(System.Byte[])?displayProperty=nameWithType><p><xref:System.Reflection.Assembly.Load(System.Byte[],System.Byte[])?displayProperty=nameWithType>|Загрузка из объекта в новый экземпляр <xref:System.Runtime.Loader.AssemblyLoadContext>.|Новый экземпляр <xref:System.Runtime.Loader.AssemblyLoadContext>.|
<xref:System.Type.GetType(System.String)?displayProperty=nameWithType><p><xref:System.Type.GetType(System.String,System.Boolean)?displayProperty=nameWithType><p><xref:System.Type.GetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType>|`Load-by-name`.|Выводится из вызывающего объекта.<p>Лучше использовать методы <xref:System.Type.GetType%2A?displayProperty=nameWithType> с аргументом `assemblyResolver`.|
<xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>|Если в типе `name` описан полный универсальный тип сборки, активируется `Load-by-name`.|Выводится из вызывающего объекта.<p>Лучше использовать <xref:System.Type.GetType%2A?displayProperty=nameWithType> для полных имен типов сборки.|
<xref:System.Activator.CreateInstance(System.String,System.String)?displayProperty=nameWithType><p><xref:System.Activator.CreateInstance(System.String,System.String,System.Object[])?displayProperty=nameWithType><p><xref:System.Activator.CreateInstance(System.String,System.String,System.Boolean,System.Reflection.BindingFlags,System.Reflection.Binder,System.Object[],System.Globalization.CultureInfo,System.Object[])?displayProperty=nameWithType>|`Load-by-name`.|Выводится из вызывающего объекта.<p>Лучше использовать методы <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>, принимающие аргумент <xref:System.Type>.|

## <a name="algorithm"></a>Алгоритм

Ниже приведен алгоритм загрузки управляемой сборки средой выполнения.

1. Определяется `active` <xref:System.Runtime.Loader.AssemblyLoadContext>.

    - Для ссылки на статическую сборку `active` <xref:System.Runtime.Loader.AssemblyLoadContext> обозначает экземпляр, который загрузил ссылающуюся сборку.
    - Предпочитаемые API-интерфейсы делают экземпляр `active` <xref:System.Runtime.Loader.AssemblyLoadContext> явным.
    - Другие API-интерфейсы выводят `active` <xref:System.Runtime.Loader.AssemblyLoadContext>. Для этих API-интерфейсов используется свойство <xref:System.Runtime.Loader.AssemblyLoadContext.CurrentContextualReflectionContext?displayProperty=nameWithType>. Если его значение равно `null`, то используется выводимый экземпляр <xref:System.Runtime.Loader.AssemblyLoadContext>.
    - См. приведенную выше таблицу.

2. Для методов `Load-by-name` активный класс <xref:System.Runtime.Loader.AssemblyLoadContext> загружает сборку. Порядок приоритета:
    - Проверяется свойство `cache-by-name`.

    - Вызывается функция <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType>.

    - Проверяется кэш экземпляров <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> и выполняется логика [стандартного зондирования для поиска управляемой сборки](default-probing.md#managed-assembly-default-probing).

    - Вызывается событие <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> для активного класса AssemblyLoadContext.

    - Создается событие <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.

3. Для других типов загрузок `active` <xref:System.Runtime.Loader.AssemblyLoadContext> загружает сборку. Порядок приоритета:
    - Проверяется свойство `cache-by-name`.

    - Выполняется загрузка на основе указанного пути или из необработанного объекта сборки.

4. В любом случае, если загружена новая сборка, выполняется следующее:
   - Возникает событие <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType>.
   - Добавляется ссылка в `cache-by-name` экземпляра <xref:System.Runtime.Loader.AssemblyLoadContext> сборки.

5. Если сборка найдена, добавляется соответствующая ссылка в `cache-by-name` экземпляра `active` <xref:System.Runtime.Loader.AssemblyLoadContext>.
