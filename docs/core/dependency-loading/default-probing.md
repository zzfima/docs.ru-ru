---
title: Стандартное зондирование (.NET Core)
description: Общие сведения о логике зондирования для поиска зависимостей в System.Runtime.Loader.AssemblyLoadContext.Default (.NET Core).
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 500ee6ee863b1f311970a9e718936f57f7d4efd6
ms.sourcegitcommit: 10db6551ea3c971470cf5d2cc21ba1cbcefe5c55
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2019
ms.locfileid: "72303686"
---
# <a name="default-probing"></a>Стандартное зондирование

Экземпляр <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> отвечает за поиск зависимостей сборки. В этой статье описана логика зондирования этого экземпляра <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>.

## <a name="host-configured-probing-properties"></a>Свойства зондирования, настроенные узлом

Когда запускается среда выполнения, узел среды выполнения предоставляет набор именованных свойств зондирования, которые позволяют настроить пути зондирования в <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>.

Все свойства зондирования являются необязательными. Если свойство есть, оно представляет собой строковое значение со списком абсолютных путей с разделителями. В качестве разделителя используется символ ";" в ОС Windows или ":" на всех других платформах.

|Имя свойства                 |ОПИСАНИЕ  |
|------------------------------|---------|
|`TRUSTED_PLATFORM_ASSEMBLIES`   | Список путей к файлам сборок платформы и приложения. |
|`PLATFORM_RESOURCE_ROOTS`       | Список путей к каталогам, в которых выполняется поиск вспомогательных сборок ресурсов. |
|`NATIVE_DLL_SEARCH_DIRECTORIES` | Список путей к каталогам, в которых выполняется поиск неуправляемых (собственных) сборок.        |
|`APP_PATHS`                     | Список путей к каталогам, в которых выполняется поиск управляемых сборок. |
|`APP_NI_PATHS`                  | Список путей к каталогам, в которых выполняется поиск собственных образов для управляемых сборок. |

### <a name="how-are-the-properties-populated"></a>Как задаются свойства?

Для установки значений свойств есть два основных сценария. Выбор между ними зависит от наличия файла *\<myapp>.deps.json*.

- Если файл *\*.deps.json* есть, для свойств зондирования задаются данные из этого файла.
- Если файла *\*.deps.json* нет, предполагается, что все зависимости размещаются в каталоге приложения. В этом случае для свойств зондирования задается содержимое этого каталога.

Кроме того, аналогичным образом обрабатываются файлы *\*.deps.json* для всех упоминаемых платформ.

И, наконец, могут добавляться дополнительные зависимости из переменной среды `ADDITIONAL_DEPS`.

### <a name="how-do-i-see-the-probing-properties-from-managed-code"></a>Как узнать свойства зондирования из управляемого кода?

Каждое свойство можно получить, вызвав функцию <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> с именем свойства. Список имен содержится в приведенной выше таблице.

### <a name="how-do-i-debug-the-probing-properties-construction"></a>Как выполнять отладку формирования свойств зондирования?

Среда выполнения .NET Core будет выводить полезные сообщения трассировки, если настроены определенные переменные среды:

|Переменная среды        |ОПИСАНИЕ  |
|----------------------------|---------|
|`COREHOST_TRACE=1`          |Включение трассировки.|
|`COREHOST_TRACEFILE=<path>` |Трассировка по указанному пути вместо стандартного `stderr`.|
|`COREHOST_TRACE_VERBOSITY`  |Настройка уровня детализации в диапазоне от 1 (минимальный) до 4 (максимальный).|

## <a name="managed-assembly-default-probing"></a>Стандартное зондирование для управляемой сборки

При зондировании для поиска управляемой сборки <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> выполняет перебор в следующем порядке:

- файлы, соответствующие <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> в `TRUSTED_PLATFORM_ASSEMBLIES` (без учета расширений);
- собственные сборки в файлах образов, расположенных в `APP_NI_PATHS`, с известным расширением файла;
- файлы сборок, расположенные в `APP_PATHS`, с известным расширением файла.

## <a name="satellite-resource-assembly-probing"></a>Зондирование для поиска вспомогательной сборки (ресурса)

Чтобы найти вспомогательную сборку для определенного языка и региональных параметров, создайте структуру путей к файлам.

Для каждого пути в `PLATFORM_RESOURCE_ROOTS` и далее в `APP_PATHS` добавьте строку <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>, затем символ разделения каталогов, строку <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> и расширение .dll.

Если есть любой файл с одним из таких имен, попробуйте загрузить и вернуть его.

## <a name="unmanaged-native-library-probing"></a>Зондирование для поиска неуправляемых (собственных) библиотек

При зондировании для поиска неуправляемой библиотеки, подходящие варианты проверяются в `NATIVE_DLL_SEARCH_DIRECTORIES`.
