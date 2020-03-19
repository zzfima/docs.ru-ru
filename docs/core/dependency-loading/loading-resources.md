---
title: Алгоритм загрузки вспомогательных сборок (.NET Core)
description: Подробный алгоритм загрузки вспомогательных сборок в .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: bfdc1d8179d46a13b3d137a87397fa3e573da33c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "72303626"
---
# <a name="satellite-assembly-loading-algorithm"></a>Алгоритм загрузки вспомогательных сборок

Вспомогательные сборки используются для хранения локализованных ресурсов, то есть настроенных для конкретного языка и региональных параметров.

Для вспомогательных сборок используется другой алгоритм загрузки, отличный от алгоритма для обычных управляемых сборок.

## <a name="when-are-satellite-assemblies-loaded"></a>Когда загружаются вспомогательные сборки?

Вспомогательные сборки загружаются вместе с локализованным ресурсом.

Базовый API для загрузки локализованных ресурсов — класс <xref:System.Resources.ResourceManager?displayProperty=fullName>. В конечном итоге именно класс <xref:System.Resources.ResourceManager> будет вызывать метод <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A> для каждого свойства <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.

Интерфейсы API более высокого уровня могут быть абстракцией API нижнего уровня.

## <a name="algorithm"></a>Алгоритм

Процесс использования резервных ресурсов .NET Core включает следующие шаги.

1. Определение экземпляра `active` <xref:System.Runtime.Loader.AssemblyLoadContext>. Во всех случаях экземпляром `active` считается <xref:System.Runtime.Loader.AssemblyLoadContext> исполняемой сборки.

2. Экземпляр `active` пытается загрузить вспомогательную сборку для запрошенного языка и региональных параметров в следующем порядке приоритета:
    - Проверяется кэш.
    - Проверяется каталог выполняемой в данный момент сборки на наличие подкаталога, соответствующего запрошенному <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> (например, `es-MX`).

        > [!NOTE]
        > Эта возможность появилась в .NET Core, начиная с версии 3.0.
        >
        > [!NOTE]
        > В ОС Linux и macOS в именах подкаталогов учитывается регистр. Они должны:
        > - либо точно совпадать с учетом регистра;
        > - либо содержать только строчные буквы.

    - Если `active` — экземпляр <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>, запускается логика [стандартного зондирования для поиска вспомогательных сборок (ресурсов)](default-probing.md#satellite-resource-assembly-probing).

    - Вызывается функция <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType>.

    - Создается событие <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType>.

    - Создается событие <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.

3. Если вспомогательная сборка загружена:
   - Возникает событие <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType>.
   - В сборке выполняется поиск запрошенного ресурса. Если среда выполнения обнаружит ресурс в сборке, она использует его. Если ресурс не найден, поиск продолжается.

    > [!NOTE]
    > Чтобы найти ресурс во вспомогательной сборке, среда выполнения выполняет поиск файла ресурсов по запросу <xref:System.Resources.ResourceManager> для текущего <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>. В файле ресурсов выполняется поиск имени запрошенного ресурса. Если имя не найдено, ресурс обрабатывается как ненайденный.

4. Затем среда выполнения ищет родительские сборки языка и региональных параметров по нескольким уровням, каждый раз повторяя действия 2 и 3.

    Для любого языка и региональных параметров есть только один родительский элемент, определенный свойством <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType>.

    Поиск родительского языка и региональных параметров останавливается, когда свойство <xref:System.Globalization.CultureInfo.Parent%2A> для языка и региональных параметров имеет значение <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType>.

    Для <xref:System.Globalization.CultureInfo.InvariantCulture> выполняется не возврат к шагам 2 и 3, а сразу переход к шагу 5.

5. Если ресурс еще не найден, используется ресурс для языка и региональных параметров по умолчанию.

   Обычно ресурсы для языка региональных параметров по умолчанию включены в основную сборку приложения. Но вы можете указать значение <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType> для свойства <xref:System.Resources.NeutralResourcesLanguageAttribute.Location?displayProperty=nameWithType>. Это означает, что конечным расположением ресурсов по умолчанию будет вспомогательная, а не основная сборка.

    > [!NOTE]
    > Если ничего не найдено, применяется язык и региональные параметры по умолчанию. Поэтому мы рекомендуем всегда включать полный набор ресурсов в файл ресурсов по умолчанию. Это помогает избежать появления исключений. Полный набор обеспечивает запасной вариант для всех ресурсов и гарантирует, что у пользователю всегда будет доступ хотя бы к одному ресурсу, даже если он не связан с определенным языком и региональными параметрами.

6. Итак:
   - если среда выполнения не находит файл ресурсов для стандартного (резервного) языка и региональных параметров, возникает исключение <xref:System.Resources.MissingManifestResourceException> или <xref:System.Resources.MissingSatelliteAssemblyException>;
   - если файл ресурсов найден, но запрошенного ресурса в нем нет, то запрос возвращает `null`.
