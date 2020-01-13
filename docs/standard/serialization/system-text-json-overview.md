---
title: Сериализация и десериализация JSON C# с помощью-.NET
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: c05783963ba521109fb542f247ec9e62fdb5c2d9
ms.sourcegitcommit: dfad244ba549702b649bfef3bb057e33f24a8fb2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2020
ms.locfileid: "75904642"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a>Сериализация и десериализация JSON (маршалинг и расмаршалинг) в .NET — обзор

`System.Text.Json` пространство имен предоставляет функциональные возможности для сериализации и десериализации из нотация объектов JavaScript (JSON).

Структура библиотеки подчеркивает высокую производительность и низкое выделение памяти по расширенному набору функций. Встроенная поддержка UTF-8 оптимизирует процесс чтения и записи текста JSON, закодированного как UTF-8, который является наиболее распространенной кодировкой для данных в Интернете и файлах на диске.

Библиотека также предоставляет классы для работы с объектной моделью документов (DOM) в памяти. Эта функция обеспечивает произвольный доступ только для чтения элементов в JSON-файле или строке. 

## <a name="how-to-get-the-library"></a>Как получить библиотеку

* Библиотека встроена в состав общей платформы [.NET Core 3,0](https://aka.ms/netcore3download) .
* Для других целевых платформ установите пакет NuGet [System. Text. JSON](https://www.nuget.org/packages/System.Text.Json) . Пакет поддерживает:
  * .NET Standard 2,0 и более поздних версий
  * .NET Framework 4.7.2 и более поздних версий
  * .NET Core 2,0, 2,1 и 2,2

## <a name="additional-resources"></a>Дополнительные ресурсы

* [Использование библиотеки](system-text-json-how-to.md)
* [Как выполнить миграцию из Newtonsoft. JSON](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Запись преобразователей](system-text-json-converters-how-to.md)
* [Исходный код System. Text. JSON](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)
* [Справочник по API System. Text. JSON](xref:System.Text.Json)
* [Справочник по API-интерфейсам System. Text. JSON. Serialization](xref:System.Text.Json.Serialization)
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
