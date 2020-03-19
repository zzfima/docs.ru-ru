---
title: Критические изменения в библиотеке базовых классов
description: Список критических изменений в библиотеке базовых классов .NET CoreFx.
ms.date: 09/20/2019
ms.openlocfilehash: 56a3cf4f4c00a79752d5a98bb086bb9f8c0614b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147579"
---
# <a name="corefx-breaking-changes"></a><span data-ttu-id="cceeb-103">Критические изменения CoreFx</span><span class="sxs-lookup"><span data-stu-id="cceeb-103">CoreFx breaking changes</span></span>

<span data-ttu-id="cceeb-104">CoreFx предоставляет примитивы и другие общие типы, используемые в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cceeb-104">CoreFx provides the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="cceeb-105">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="cceeb-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="cceeb-106">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="cceeb-106">Breaking change</span></span> | <span data-ttu-id="cceeb-107">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="cceeb-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="cceeb-108">Интерфейсы API, сообщающие версию, теперь сообщают версию продукта, а не файла</span><span class="sxs-lookup"><span data-stu-id="cceeb-108">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="cceeb-109">3.0</span><span class="sxs-lookup"><span data-stu-id="cceeb-109">3.0</span></span> |
| [<span data-ttu-id="cceeb-110">Пользовательские экземпляры EncoderFallbackBuffer не поддерживают рекурсивный откат</span><span class="sxs-lookup"><span data-stu-id="cceeb-110">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="cceeb-111">3.0</span><span class="sxs-lookup"><span data-stu-id="cceeb-111">3.0</span></span> |
| [<span data-ttu-id="cceeb-112">Изменено поведение форматирования и анализа при наличии плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="cceeb-112">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="cceeb-113">3.0</span><span class="sxs-lookup"><span data-stu-id="cceeb-113">3.0</span></span> |
| [<span data-ttu-id="cceeb-114">Операции синтаксического анализа с плавающей запятой больше не завершаются ошибкой и не вызывают исключение OverflowException</span><span class="sxs-lookup"><span data-stu-id="cceeb-114">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="cceeb-115">3.0</span><span class="sxs-lookup"><span data-stu-id="cceeb-115">3.0</span></span> |
| [<span data-ttu-id="cceeb-116">Исключение InvalidAsynchronousStateException перенесено в другую сборку</span><span class="sxs-lookup"><span data-stu-id="cceeb-116">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="cceeb-117">3.0</span><span class="sxs-lookup"><span data-stu-id="cceeb-117">3.0</span></span> |
| [<span data-ttu-id="cceeb-118">В .NET Core 3.0 применяются рекомендации по Юникоду при замене некорректных последовательностей байтов UTF-8</span><span class="sxs-lookup"><span data-stu-id="cceeb-118">NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences</span></span>](#net-core-30-follows-unicode-best-practices-when-replacing-ill-formed-utf-8-byte-sequences) | <span data-ttu-id="cceeb-119">3.0</span><span class="sxs-lookup"><span data-stu-id="cceeb-119">3.0</span></span> |
| [<span data-ttu-id="cceeb-120">Класс TypeDescriptionProviderAttribute перенесен в другую сборку</span><span class="sxs-lookup"><span data-stu-id="cceeb-120">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="cceeb-121">3.0</span><span class="sxs-lookup"><span data-stu-id="cceeb-121">3.0</span></span> |
| [<span data-ttu-id="cceeb-122">ZipArchiveEntry больше не обрабатывает архивы с несогласованными размерами записей</span><span class="sxs-lookup"><span data-stu-id="cceeb-122">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="cceeb-123">3.0</span><span class="sxs-lookup"><span data-stu-id="cceeb-123">3.0</span></span> |
| [<span data-ttu-id="cceeb-124">Тип исключения сериализатора JSON изменен с JsonException на NotSupportedException</span><span class="sxs-lookup"><span data-stu-id="cceeb-124">JSON serializer exception type changed from JsonException to NotSupportedException</span></span>](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception) | <span data-ttu-id="cceeb-125">3.0</span><span class="sxs-lookup"><span data-stu-id="cceeb-125">3.0</span></span> |
| [<span data-ttu-id="cceeb-126">Внесены изменения в семантику (string)null в Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="cceeb-126">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | <span data-ttu-id="cceeb-127">3.0</span><span class="sxs-lookup"><span data-stu-id="cceeb-127">3.0</span></span> |
| [<span data-ttu-id="cceeb-128">Методы JsonEncodedText.Encode содержат дополнительный аргумент JavaScriptEncoder</span><span class="sxs-lookup"><span data-stu-id="cceeb-128">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | <span data-ttu-id="cceeb-129">3.0</span><span class="sxs-lookup"><span data-stu-id="cceeb-129">3.0</span></span> |
| [<span data-ttu-id="cceeb-130">Изменена подпись JsonFactoryConverter.CreateConverter</span><span class="sxs-lookup"><span data-stu-id="cceeb-130">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed) | <span data-ttu-id="cceeb-131">3.0</span><span class="sxs-lookup"><span data-stu-id="cceeb-131">3.0</span></span> |
| [<span data-ttu-id="cceeb-132">Внесены изменения в API JsonElement</span><span class="sxs-lookup"><span data-stu-id="cceeb-132">JsonElement API changes</span></span>](#jsonelement-api-changes) | <span data-ttu-id="cceeb-133">3.0</span><span class="sxs-lookup"><span data-stu-id="cceeb-133">3.0</span></span> |
| [<span data-ttu-id="cceeb-134">FieldInfo.SetValue вызывает исключение для статических полей и полей только для инициализации</span><span class="sxs-lookup"><span data-stu-id="cceeb-134">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="cceeb-135">3.0</span><span class="sxs-lookup"><span data-stu-id="cceeb-135">3.0</span></span> |
| [<span data-ttu-id="cceeb-136">Во встроенные типы структур добавлены частные поля</span><span class="sxs-lookup"><span data-stu-id="cceeb-136">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="cceeb-137">2.1</span><span class="sxs-lookup"><span data-stu-id="cceeb-137">2.1</span></span> |
| [<span data-ttu-id="cceeb-138">Изменено значение по умолчанию для UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="cceeb-138">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="cceeb-139">2.1</span><span class="sxs-lookup"><span data-stu-id="cceeb-139">2.1</span></span> |
| [<span data-ttu-id="cceeb-140">Версии OpenSSL в macOS</span><span class="sxs-lookup"><span data-stu-id="cceeb-140">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="cceeb-141">2.1</span><span class="sxs-lookup"><span data-stu-id="cceeb-141">2.1</span></span> |
| [<span data-ttu-id="cceeb-142">Исключение UnauthorizedAccessException, вызванное FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="cceeb-142">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="cceeb-143">1.0</span><span class="sxs-lookup"><span data-stu-id="cceeb-143">1.0</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="cceeb-144">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="cceeb-144">.NET Core 3.0</span></span>

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/3.0/version-information-changes.md)]

***

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/3.0/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

***

[!INCLUDE[Floating point formatting and parsing behavior changes](~/includes/core-changes/corefx/3.0/floating-point-changes.md)]

***

[!INCLUDE[Floating-point parsing operations no longer fail or throw an OverflowException](~/includes/core-changes/corefx/3.0/floating-point-parsing-does-not-overflow.md)]

***

[!INCLUDE[InvalidAsynchronousStateException moved to another assembly](~/includes/core-changes/corefx/3.0/move-invalidasynchronousstateexception.md)]

***

[!INCLUDE[NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences](~/includes/core-changes/corefx/3.0/net-core-3-0-follows-unicode-utf8-best-practices.md)]

***

[!INCLUDE[TypeDescriptionProviderAttribute moved to another assembly](~/includes/core-changes/corefx/3.0/move-typedescriptionproviderattribute.md)]

***

[!INCLUDE[ZipArchiveEntry no longer handles archives with inconsistent entry sizes](~/includes/core-changes/corefx/3.0/ziparchiveentry-and-inconsistent-entry-sizes.md)]

***

[!INCLUDE[JSON serializer exception type changed from JsonException to NotSupportedException](~/includes/core-changes/corefx/3.0/serializer-throws-notsupportedexception.md)]

***

[!INCLUDE[Change in semantics of (string)null in Utf8JsonWriter](~/includes/core-changes/corefx/3.0/change-in-null-in-utf8jsonwriter.md)]

***

[!INCLUDE[JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument](~/includes/core-changes/corefx/3.0/jsonencodedtext-encode-has-additional-argument.md)]

***

[!INCLUDE[JsonFactoryConverter.CreateConverter signature changed](~/includes/core-changes/corefx/3.0/jsonfactoryconverter-createconverter.md)]

***

[!INCLUDE[JsonElement API changes](~/includes/core-changes/corefx/3.0/jsonelement-api-changes.md)]

***

[!INCLUDE [FieldInfo.SetValue throws exception for static, init-only fields](~/includes/core-changes/corefx/3.0/fieldinfo-setvalue-exception.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="cceeb-145">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cceeb-145">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="cceeb-146">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="cceeb-146">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***
