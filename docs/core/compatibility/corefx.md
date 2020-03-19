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
# <a name="corefx-breaking-changes"></a>Критические изменения CoreFx

CoreFx предоставляет примитивы и другие общие типы, используемые в .NET Core.

На этой странице описаны следующие критические изменения:

| Критическое изменение | Представленная версия |
| - | :-: |
| [Интерфейсы API, сообщающие версию, теперь сообщают версию продукта, а не файла](#apis-that-report-version-now-report-product-and-not-file-version) | 3.0 |
| [Пользовательские экземпляры EncoderFallbackBuffer не поддерживают рекурсивный откат](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | 3.0 |
| [Изменено поведение форматирования и анализа при наличии плавающей запятой](#floating-point-formatting-and-parsing-behavior-changed) | 3.0 |
| [Операции синтаксического анализа с плавающей запятой больше не завершаются ошибкой и не вызывают исключение OverflowException](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | 3.0 |
| [Исключение InvalidAsynchronousStateException перенесено в другую сборку](#invalidasynchronousstateexception-moved-to-another-assembly) | 3.0 |
| [В .NET Core 3.0 применяются рекомендации по Юникоду при замене некорректных последовательностей байтов UTF-8](#net-core-30-follows-unicode-best-practices-when-replacing-ill-formed-utf-8-byte-sequences) | 3.0 |
| [Класс TypeDescriptionProviderAttribute перенесен в другую сборку](#typedescriptionproviderattribute-moved-to-another-assembly) | 3.0 |
| [ZipArchiveEntry больше не обрабатывает архивы с несогласованными размерами записей](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | 3.0 |
| [Тип исключения сериализатора JSON изменен с JsonException на NotSupportedException](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception) | 3.0 |
| [Внесены изменения в семантику (string)null в Utf8JsonWriter](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | 3.0 |
| [Методы JsonEncodedText.Encode содержат дополнительный аргумент JavaScriptEncoder](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | 3.0 |
| [Изменена подпись JsonFactoryConverter.CreateConverter](#jsonfactoryconvertercreateconverter-signature-changed) | 3.0 |
| [Внесены изменения в API JsonElement](#jsonelement-api-changes) | 3.0 |
| [FieldInfo.SetValue вызывает исключение для статических полей и полей только для инициализации](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | 3.0 |
| [Во встроенные типы структур добавлены частные поля](#private-fields-added-to-built-in-struct-types) | 2.1 |
| [Изменено значение по умолчанию для UseShellExecute](#change-in-default-value-of-useshellexecute) | 2.1 |
| [Версии OpenSSL в macOS](#openssl-versions-on-macos) | 2.1 |
| [Исключение UnauthorizedAccessException, вызванное FileSystemInfo.Attributes](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | 1.0 |

## <a name="net-core-30"></a>.NET Core 3.0

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

## <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a>.NET Core 1.0

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***
