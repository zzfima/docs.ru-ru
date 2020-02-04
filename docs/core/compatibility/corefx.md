---
title: Критические изменения в библиотеке базовых классов — .NET Core
description: Список критических изменений в библиотеке базовых классов .NET CoreFx.
ms.date: 09/20/2019
ms.openlocfilehash: eb416a0b061bfe50db330627c0ea68e0ba0c9079
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116505"
---
# <a name="corefx-breaking-changes"></a>Критические изменения CoreFx

CoreFx предоставляет примитивы и другие общие типы, используемые в .NET Core.

На этой странице описаны следующие критические изменения:

- [Интерфейсы API, сообщающие версию, теперь сообщают версию продукта, а не файла](#apis-that-report-version-now-report-product-and-not-file-version)
- [Пользовательские экземпляры EncoderFallbackBuffer не поддерживают рекурсивный откат](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively)
- [Изменено поведение форматирования и анализа при наличии плавающей запятой](#floating-point-formatting-and-parsing-behavior-changed)
- [Операции синтаксического анализа с плавающей запятой больше не завершаются ошибкой и не вызывают исключение OverflowException](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception)
- [Исключение InvalidAsynchronousStateException перенесено в другую сборку](#invalidasynchronousstateexception-moved-to-another-assembly)
- [В .NET Core 3.0 применяются рекомендации по Юникоду при замене некорректных последовательностей байтов UTF-8](#net-core-30-follows-unicode-best-practices-when-replacing-ill-formed-utf-8-byte-sequences)
- [Класс TypeDescriptionProviderAttribute перенесен в другую сборку](#typedescriptionproviderattribute-moved-to-another-assembly)
- [ZipArchiveEntry больше не обрабатывает архивы с несогласованными размерами записей](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes)
- [Тип исключения сериализатора JSON изменен с JsonException на NotSupportedException](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception)
- [Внесены изменения в семантику (string)null в Utf8JsonWriter](#change-in-semantics-of-stringnull-in-utf8jsonwriter)
- [Методы JsonEncodedText.Encode содержат дополнительный аргумент JavaScriptEncoder](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument)
- [Изменена подпись JsonFactoryConverter.CreateConverter](#jsonfactoryconvertercreateconverter-signature-changed)
- [Внесены изменения в API JsonElement](#jsonelement-api-changes)
- [Во встроенные типы структур добавлены частные поля](#private-fields-added-to-built-in-struct-types)
- [Изменено значение по умолчанию для UseShellExecute](#change-in-default-value-of-useshellexecute)

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

## <a name="net-core-30-preview-9"></a>.NET Core 3.0 (предварительная версия 9)

[!INCLUDE[JSON serializer exception type changed from JsonException to NotSupportedException](~/includes/core-changes/corefx/3.0/serializer-throws-notsupportedexception.md)]

***

## <a name="net-core-30-preview-8"></a>.NET Core 3.0 (предварительная версия 8)

[!INCLUDE[Change in semantics of (string)null in Utf8JsonWriter](~/includes/core-changes/corefx/3.0/change-in-null-in-utf8jsonwriter.md)]

***

[!INCLUDE[JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument](~/includes/core-changes/corefx/3.0/jsonencodedtext-encode-has-additional-argument.md)]

***

[!INCLUDE[JsonFactoryConverter.CreateConverter signature changed](~/includes/core-changes/corefx/3.0/jsonfactoryconverter-createconverter.md)]

***

## <a name="net-core-30-preview-7"></a>.NET Core 3.0 (предварительная версия 7)

[!INCLUDE[JsonElement API changes](~/includes/core-changes/corefx/3.0/jsonelement-api-changes.md)]

***

## <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***
