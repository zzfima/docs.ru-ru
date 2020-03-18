---
title: Дополнительные средства
description: Общие сведения о дополнительных инструментах, которые поддерживают и расширяют функциональные возможности .NET Core.
author: mlacouture
ms.date: 02/13/2020
ms.custom: mvc
ms.openlocfilehash: c0224a1cc6cbb9ae6fa88e5f869c47a1e84289e0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "77451529"
---
# <a name="net-core-additional-tools-overview"></a>Общие сведения о дополнительных инструментах .NET Core

Этот раздел содержит список инструментов, которые поддерживают и расширяют функциональные возможности .NET Core вместе с .NET Core CLI.

## <a name="net-core-uninstall-tool"></a>Средство удаления .NET Core

С помощью [средства удаления .NET Core](https://github.com/dotnet/cli-lab/releases) (`dotnet-core-uninstall`) можно удалять пакеты SDK и среду выполнения .NET Core в системе с целью сохранить только нужные версии этих компонентов. Указать удаляемые версии можно с помощью ряда параметров.

## <a name="net-core-diagnostic-tools"></a>Средства диагностики .NET Core

[dotnet-counters](../diagnostics/dotnet-counters.md) — это средство мониторинга производительности для первого уровня мониторинга работоспособности и анализа производительности.

[dotnet-dump](../diagnostics/dotnet-dump.md) предоставляет способ сбора и анализа дампов ядра Windows и Linux без собственного отладчика.

[dotnet-trace](../diagnostics/dotnet-trace.md) собирает данные профилирования из приложения, которые могут помочь в сценариях, когда необходимо выяснить, почему приложение работает медленно.

## <a name="wcf-web-service-reference-tool"></a>Инструмент WCF Web Service Reference

Инструмент WCF (Windows Communication Foundation) [Web Service Reference](wcf-web-service-reference-guide.md) — это поставщик подключенной службы для Visual Studio, впервые появившийся в [Visual Studio 2017 версии 15.5](/visualstudio/releasenotes/vs2017-relnotes-v15.5#WCFTools). Это средство позволяет извлечь метаданные из веб-службы в текущем решении, сетевого расположения или WSDL-файла. Оно создает совместимый с .NET Core исходный файл, определяя прокси-класс WCF с методами, которые можно использовать для доступа к операциям веб-службы.

## <a name="wcf-dotnet-svcutil-tool"></a>Средство WCF dotnet-svcutil

WCF [dotnet-svcutil](dotnet-svcutil-guide.md) — это средство .NET, которое извлекает метаданные из веб-службы, расположенной в сети, или из WSDL-файла. Оно создает совместимый с .NET Core исходный файл, определяя прокси-класс WCF с методами, которые можно использовать для доступа к операциям веб-службы.

Средство **dotnet-svcutil** — это альтернатива поставщика подключенной службы Visual Studio [**WCF Web Service Reference**](wcf-web-service-reference-guide.md), впервые представленного в Visual Studio 2017 версии 15.5. Как и .NET, средство **dotnet-svcutil** доступно на платформах Linux, macOS и Windows.

## <a name="wcf-dotnet-svcutilxmlserializer-tool"></a>Средство WCF dotnet-svcutil.xmlserializer

В .NET Framework можно создать предварительную сборку сериализации с помощью средства svcutil. Пакет WCF [dotnet-svcutil.xmlserializer](dotnet-svcutil.xmlserializer-guide.md) предоставляет аналогичные возможности в .NET Core. Он создает код сериализации C# для типов в клиентском приложении, которые используются в контракте службы WCF и которые можно сериализовать с помощью <xref:System.Xml.Serialization.XmlSerializer>. Это улучшает начальную производительность сериализации XML при сериализации или десериализации объектов этих типов.

## <a name="xml-serializer-generator"></a>Генератор сериализации XML

Являясь аналогом [Генератора сериализации XML (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) для .NET Framework, [NuGet-пакет Microsoft.XmlSerializer.Generator](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) представляет собой решение для библиотек .NET Core и .NET Standard. Он создает сборку сериализации XML для содержащихся в сборке типов, улучшая производительность при запуске сериализации или десериализации XML для объектов этих типов с помощью <xref:System.Xml.Serialization.XmlSerializer>.
