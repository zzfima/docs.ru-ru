---
title: Сериализация и десериализация JSON C# с помощью-.NET
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 6561d5e1580e1170369622ebc7bb330ff4e0964f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705786"
---
# <a name="json-serialization-in-net---overview"></a><span data-ttu-id="f435f-102">Сериализация JSON в .NET — обзор</span><span class="sxs-lookup"><span data-stu-id="f435f-102">JSON serialization in .NET - overview</span></span>

<span data-ttu-id="f435f-103">`System.Text.Json` пространство имен предоставляет функциональные возможности для сериализации и десериализации из нотация объектов JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="f435f-103">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="f435f-104">Структура библиотеки подчеркивает высокую производительность и низкое выделение памяти по расширенному набору функций.</span><span class="sxs-lookup"><span data-stu-id="f435f-104">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="f435f-105">Встроенная поддержка UTF-8 оптимизирует процесс чтения и записи текста JSON, закодированного как UTF-8, который является наиболее распространенной кодировкой для данных в Интернете и файлах на диске.</span><span class="sxs-lookup"><span data-stu-id="f435f-105">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="f435f-106">Библиотека также предоставляет классы для работы с объектной моделью документов (DOM) в памяти.</span><span class="sxs-lookup"><span data-stu-id="f435f-106">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="f435f-107">Эта функция обеспечивает произвольный доступ только для чтения элементов в JSON-файле или строке.</span><span class="sxs-lookup"><span data-stu-id="f435f-107">This feature enables random read-only access of the elements in a JSON file or string.</span></span> 

## <a name="how-to-get-the-library"></a><span data-ttu-id="f435f-108">Как получить библиотеку</span><span class="sxs-lookup"><span data-stu-id="f435f-108">How to get the library</span></span>

* <span data-ttu-id="f435f-109">Библиотека встроена в состав общей платформы [.NET Core 3,0](https://aka.ms/netcore3download) .</span><span class="sxs-lookup"><span data-stu-id="f435f-109">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="f435f-110">Для других целевых платформ установите пакет NuGet [System. Text. JSON](https://www.nuget.org/packages/System.Text.Json) .</span><span class="sxs-lookup"><span data-stu-id="f435f-110">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="f435f-111">Пакет поддерживает:</span><span class="sxs-lookup"><span data-stu-id="f435f-111">The package supports:</span></span>
  * <span data-ttu-id="f435f-112">.NET Standard 2,0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="f435f-112">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="f435f-113">.NET Framework 4.6.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="f435f-113">.NET Framework 4.6.1 and later versions</span></span>
  * <span data-ttu-id="f435f-114">.NET Core 2,0, 2,1 и 2,2</span><span class="sxs-lookup"><span data-stu-id="f435f-114">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f435f-115">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="f435f-115">Additional resources</span></span>

* [<span data-ttu-id="f435f-116">Использование библиотеки</span><span class="sxs-lookup"><span data-stu-id="f435f-116">How to use the library</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="f435f-117">Исходный код</span><span class="sxs-lookup"><span data-stu-id="f435f-117">Source code</span></span>](https://github.com/dotnet/runtime/tree/master/src/libraries/System.Text.Json)
* [<span data-ttu-id="f435f-118">Справочник по API</span><span class="sxs-lookup"><span data-stu-id="f435f-118">API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="f435f-119">Стратегия развития</span><span class="sxs-lookup"><span data-stu-id="f435f-119">Roadmap</span></span>](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Text.Json/roadmap/README.md)
* <span data-ttu-id="f435f-120">Проблемы GitHub в репозитории DotNet/corefx</span><span class="sxs-lookup"><span data-stu-id="f435f-120">GitHub issues in the dotnet/corefx repository</span></span>
  * [<span data-ttu-id="f435f-121">Обсуждение разработки System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="f435f-121">Discussion about the development of System.Text.Json</span></span>](https://github.com/dotnet/corefx/issues/33115) <!-- TODO: Issues are still not moved to the new repo-->
  * [<span data-ttu-id="f435f-122">Все проблемы System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="f435f-122">All System.Text.Json issues</span></span>](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)
  * [<span data-ttu-id="f435f-123">Проблемы в System. Text. JSON с меткой JSON-функциональность-doc</span><span class="sxs-lookup"><span data-stu-id="f435f-123">System.Text.Json issues labeled json-functionality-doc</span></span>](https://github.com/dotnet/runtime/labels/json-functionality-doc)
