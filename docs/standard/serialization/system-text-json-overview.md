---
title: Сериализация JSON в .NET
author: tdykstra
ms.author: tdykstra
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: 6cb45fded220b6123dbf4461f5f1cf1c3556ff69
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083098"
---
# <a name="json-serialization-in-net"></a><span data-ttu-id="5cdad-102">Сериализация JSON в .NET</span><span class="sxs-lookup"><span data-stu-id="5cdad-102">JSON serialization in .NET</span></span>

<span data-ttu-id="5cdad-103">`System.Text.Json` Пространство имен предоставляет функциональные возможности для сериализации в нотация объектов JavaScript (JSON) и обратно.</span><span class="sxs-lookup"><span data-stu-id="5cdad-103">The `System.Text.Json` namespace provides functionality for serializing to and from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="5cdad-104">Структура библиотеки подчеркивает высокую производительность и низкое выделение памяти по расширенному набору функций.</span><span class="sxs-lookup"><span data-stu-id="5cdad-104">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="5cdad-105">Встроенная поддержка UTF-8 оптимизирует процесс чтения и записи текста JSON, закодированного как UTF-8, который является наиболее распространенной кодировкой для данных в Интернете и файлах на диске.</span><span class="sxs-lookup"><span data-stu-id="5cdad-105">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="5cdad-106">Библиотека также предоставляет классы для работы с объектной моделью документов (DOM) в памяти.</span><span class="sxs-lookup"><span data-stu-id="5cdad-106">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="5cdad-107">Эта функция обеспечивает произвольный доступ только для чтения элементов в JSON-файле или строке.</span><span class="sxs-lookup"><span data-stu-id="5cdad-107">This feature enables random read-only access of the elements in a JSON file or string.</span></span> 

## <a name="how-to-get-the-library"></a><span data-ttu-id="5cdad-108">Как получить библиотеку</span><span class="sxs-lookup"><span data-stu-id="5cdad-108">How to get the library</span></span>

* <span data-ttu-id="5cdad-109">Библиотека встроена в состав общей платформы [.NET Core 3,0](https://aka.ms/netcore3download) .</span><span class="sxs-lookup"><span data-stu-id="5cdad-109">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="5cdad-110">Для других целевых платформ установите пакет NuGet [System. Text. JSON](https://www.nuget.org/packages/System.Text.Json) .</span><span class="sxs-lookup"><span data-stu-id="5cdad-110">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="5cdad-111">Пакет поддерживает:</span><span class="sxs-lookup"><span data-stu-id="5cdad-111">The package supports:</span></span>
  * <span data-ttu-id="5cdad-112">.NET Standard 2,0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="5cdad-112">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="5cdad-113">.NET Framework 4,61 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="5cdad-113">.NET Framework 4.61 and later versions</span></span>
  * <span data-ttu-id="5cdad-114">.NET Core 2,0 и более поздние версии</span><span class="sxs-lookup"><span data-stu-id="5cdad-114">.NET Core 2.0 and later versions</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5cdad-115">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="5cdad-115">Additional resources</span></span>

* [<span data-ttu-id="5cdad-116">Использование библиотеки</span><span class="sxs-lookup"><span data-stu-id="5cdad-116">How to use the library</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="5cdad-117">Исходный код</span><span class="sxs-lookup"><span data-stu-id="5cdad-117">Source code</span></span>](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json)
* [<span data-ttu-id="5cdad-118">Справочник по API</span><span class="sxs-lookup"><span data-stu-id="5cdad-118">API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="5cdad-119">Стратегия развития</span><span class="sxs-lookup"><span data-stu-id="5cdad-119">Roadmap</span></span>](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/roadmap/README.md)
* <span data-ttu-id="5cdad-120">Проблемы GitHub в репозитории DotNet/corefx</span><span class="sxs-lookup"><span data-stu-id="5cdad-120">GitHub issues in the dotnet/corefx repository</span></span>
  * [<span data-ttu-id="5cdad-121">Обсуждение разработки System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="5cdad-121">Discussion about the development of System.Text.Json</span></span>](https://github.com/dotnet/corefx/issues/33115)
  * [<span data-ttu-id="5cdad-122">Все проблемы System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="5cdad-122">All System.Text.Json issues</span></span>](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)
  * [<span data-ttu-id="5cdad-123">Проблемы в System. Text. JSON с меткой JSON-функциональность-doc</span><span class="sxs-lookup"><span data-stu-id="5cdad-123">System.Text.Json issues labeled json-functionality-doc</span></span>](https://github.com/dotnet/corefx/labels/json-functionality-doc)
