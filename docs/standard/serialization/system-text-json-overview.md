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
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a><span data-ttu-id="aa49e-102">Сериализация и десериализация JSON (маршалинг и расмаршалинг) в .NET — обзор</span><span class="sxs-lookup"><span data-stu-id="aa49e-102">JSON serialization and deserialization (marshalling and unmarshalling) in .NET - overview</span></span>

<span data-ttu-id="aa49e-103">`System.Text.Json` пространство имен предоставляет функциональные возможности для сериализации и десериализации из нотация объектов JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="aa49e-103">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="aa49e-104">Структура библиотеки подчеркивает высокую производительность и низкое выделение памяти по расширенному набору функций.</span><span class="sxs-lookup"><span data-stu-id="aa49e-104">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="aa49e-105">Встроенная поддержка UTF-8 оптимизирует процесс чтения и записи текста JSON, закодированного как UTF-8, который является наиболее распространенной кодировкой для данных в Интернете и файлах на диске.</span><span class="sxs-lookup"><span data-stu-id="aa49e-105">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="aa49e-106">Библиотека также предоставляет классы для работы с объектной моделью документов (DOM) в памяти.</span><span class="sxs-lookup"><span data-stu-id="aa49e-106">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="aa49e-107">Эта функция обеспечивает произвольный доступ только для чтения элементов в JSON-файле или строке.</span><span class="sxs-lookup"><span data-stu-id="aa49e-107">This feature enables random read-only access of the elements in a JSON file or string.</span></span> 

## <a name="how-to-get-the-library"></a><span data-ttu-id="aa49e-108">Как получить библиотеку</span><span class="sxs-lookup"><span data-stu-id="aa49e-108">How to get the library</span></span>

* <span data-ttu-id="aa49e-109">Библиотека встроена в состав общей платформы [.NET Core 3,0](https://aka.ms/netcore3download) .</span><span class="sxs-lookup"><span data-stu-id="aa49e-109">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="aa49e-110">Для других целевых платформ установите пакет NuGet [System. Text. JSON](https://www.nuget.org/packages/System.Text.Json) .</span><span class="sxs-lookup"><span data-stu-id="aa49e-110">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="aa49e-111">Пакет поддерживает:</span><span class="sxs-lookup"><span data-stu-id="aa49e-111">The package supports:</span></span>
  * <span data-ttu-id="aa49e-112">.NET Standard 2,0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="aa49e-112">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="aa49e-113">.NET Framework 4.7.2 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="aa49e-113">.NET Framework 4.7.2 and later versions</span></span>
  * <span data-ttu-id="aa49e-114">.NET Core 2,0, 2,1 и 2,2</span><span class="sxs-lookup"><span data-stu-id="aa49e-114">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="aa49e-115">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="aa49e-115">Additional resources</span></span>

* [<span data-ttu-id="aa49e-116">Использование библиотеки</span><span class="sxs-lookup"><span data-stu-id="aa49e-116">How to use the library</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="aa49e-117">Как выполнить миграцию из Newtonsoft. JSON</span><span class="sxs-lookup"><span data-stu-id="aa49e-117">How to migrate from Newtonsoft.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="aa49e-118">Запись преобразователей</span><span class="sxs-lookup"><span data-stu-id="aa49e-118">How to write converters</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="aa49e-119">Исходный код System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="aa49e-119">System.Text.Json source code</span></span>](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)
* [<span data-ttu-id="aa49e-120">Справочник по API System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="aa49e-120">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="aa49e-121">Справочник по API-интерфейсам System. Text. JSON. Serialization</span><span class="sxs-lookup"><span data-stu-id="aa49e-121">System.Text.Json.Serialization API reference</span></span>](xref:System.Text.Json.Serialization)
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
