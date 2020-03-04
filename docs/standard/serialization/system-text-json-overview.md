---
title: Сериализация и десериализация JSON C# с помощью-.NET
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 660a2831aa6a807486fc47eae880bcd11347c547
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159550"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a><span data-ttu-id="d89c6-102">Сериализация и десериализация JSON (маршалинг и расмаршалинг) в .NET — обзор</span><span class="sxs-lookup"><span data-stu-id="d89c6-102">JSON serialization and deserialization (marshalling and unmarshalling) in .NET - overview</span></span>

<span data-ttu-id="d89c6-103">`System.Text.Json` пространство имен предоставляет функциональные возможности для сериализации и десериализации из нотация объектов JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="d89c6-103">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="d89c6-104">Структура библиотеки подчеркивает высокую производительность и низкое выделение памяти по расширенному набору функций.</span><span class="sxs-lookup"><span data-stu-id="d89c6-104">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="d89c6-105">Встроенная поддержка UTF-8 оптимизирует процесс чтения и записи текста JSON, закодированного как UTF-8, который является наиболее распространенной кодировкой для данных в Интернете и файлах на диске.</span><span class="sxs-lookup"><span data-stu-id="d89c6-105">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="d89c6-106">Библиотека также предоставляет классы для работы с объектной моделью документов (DOM) в памяти.</span><span class="sxs-lookup"><span data-stu-id="d89c6-106">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="d89c6-107">Эта функция обеспечивает произвольный доступ только для чтения элементов в JSON-файле или строке.</span><span class="sxs-lookup"><span data-stu-id="d89c6-107">This feature enables random read-only access of the elements in a JSON file or string.</span></span>

## <a name="how-to-get-the-library"></a><span data-ttu-id="d89c6-108">Как получить библиотеку</span><span class="sxs-lookup"><span data-stu-id="d89c6-108">How to get the library</span></span>

* <span data-ttu-id="d89c6-109">Библиотека встроена в состав общей платформы [.NET Core 3,0](https://aka.ms/netcore3download) .</span><span class="sxs-lookup"><span data-stu-id="d89c6-109">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="d89c6-110">Для других целевых платформ установите [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="d89c6-110">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="d89c6-111">Пакет поддерживает:</span><span class="sxs-lookup"><span data-stu-id="d89c6-111">The package supports:</span></span>
  * <span data-ttu-id="d89c6-112">.NET Standard 2,0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="d89c6-112">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="d89c6-113">.NET Framework 4.7.2 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="d89c6-113">.NET Framework 4.7.2 and later versions</span></span>
  * <span data-ttu-id="d89c6-114">.NET Core 2,0, 2,1 и 2,2</span><span class="sxs-lookup"><span data-stu-id="d89c6-114">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d89c6-115">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="d89c6-115">Additional resources</span></span>

* [<span data-ttu-id="d89c6-116">Использование библиотеки</span><span class="sxs-lookup"><span data-stu-id="d89c6-116">How to use the library</span></span>](system-text-json-how-to.md)
* <span data-ttu-id="d89c6-117">[Переход с Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="d89c6-117">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* [<span data-ttu-id="d89c6-118">Запись преобразователей</span><span class="sxs-lookup"><span data-stu-id="d89c6-118">How to write converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="d89c6-119">[исходный код System.Text.Json](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="d89c6-119">[System.Text.Json source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)</span></span>
* <span data-ttu-id="d89c6-120">[Справочник по System.Text.Json API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="d89c6-120">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="d89c6-121">[System.Text.Json. Справочник по API сериализации](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="d89c6-121">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
