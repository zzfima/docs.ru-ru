---
title: Дополнительные инструменты интерфейса командной строки
description: Общие сведения о дополнительных инструментах, которые поддерживают и расширяют функциональные возможности .NET Core.
author: mlacouture
ms.date: 12/02/2019
ms.custom: mvc, seodec18
ms.openlocfilehash: 39c2dd6de8e9a8faad0ab19bd162f09abf6801eb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344116"
---
# <a name="net-core-additional-tools-overview"></a>Общие сведения о дополнительных инструментах .NET Core

Этот раздел содержит список инструментов, которые поддерживают и расширяют функциональные возможности .NET Core вместе с инструментами [интерфейса командной строки (CLI) .NET Core](../tools/index.md).

## <a name="net-core-uninstall-tooluninstall-toolmd"></a>[Средство удаления .NET Core](uninstall-tool.md)

С помощью [средства удаления .NET Core](https://dotnet.microsoft.com/download/dotnet-core/uninstall-tool) (`dotnet-core-uninstall`) можно удалять пакеты SDK и среду выполнения .NET Core в системе с целью сохранить только нужные версии этих компонентов. Указать удаляемые версии можно с помощью ряда параметров.

## <a name="wcf-web-service-reference-toolwcf-web-service-reference-guidemd"></a>[Инструмент WCF Web Service Reference](wcf-web-service-reference-guide.md)

WCF (Windows Communication Foundation) Web Service Reference — это поставщик подключенной службы для Visual Studio, впервые появившийся в [Visual Studio 2017 версии 15.5](/visualstudio/releasenotes/vs2017-relnotes-v15.5#WCFTools). Это средство позволяет извлечь метаданные из веб-службы в текущем решении, сетевого расположения или WSDL-файла. Оно создает совместимый с .NET Core исходный файл, определяя прокси-класс WCF с методами, которые можно использовать для доступа к операциям веб-службы.

## <a name="wcf-dotnet-svcutil-tooldotnet-svcutil-guidemd"></a>[Средство WCF dotnet-svcutil](dotnet-svcutil-guide.md)

Средство WCF (Windows Communication Foundation) dotnet-svcutil — это средство интерфейса командной строки .NET Core, которое извлекает метаданные из веб-службы в сетевом расположении или WSDL-файла. Оно создает совместимый с .NET Core исходный файл, определяя прокси-класс WCF с методами, которые можно использовать для доступа к операциям веб-службы.

Средство **dotnet-svcutil** — это альтернатива поставщика подключенной службы Visual Studio [**WCF Web Service Reference**](wcf-web-service-reference-guide.md), впервые представленного в Visual Studio 2017 версии 15.5. Как и .NET Core CLI, средство **dotnet-svcutil** доступно на платформах Linux, macOS и Windows.

## <a name="wcf-dotnet-svcutilxmlserializer-tooldotnet-svcutilxmlserializer-guidemd"></a>[Средство WCF dotnet-svcutil.xmlserializer](dotnet-svcutil.xmlserializer-guide.md)

В .NET Framework можно создать предварительную сборку сериализации с помощью средства svcutil. Пакет NuGet dotnet-svcutil.xmlserializer предоставляет аналогичные возможности в .NET Core. Он создает код сериализации C# для типов в клиентском приложении, которые используются в контракте службы WCF и которые можно сериализовать с помощью <xref:System.Xml.Serialization.XmlSerializer>. Это улучшает начальную производительность сериализации XML при сериализации или десериализации объектов этих типов.

## <a name="xml-serializer-generatorxml-serializer-generatormd"></a>[Генератор сериализации XML](xml-serializer-generator.md)

Являясь аналогом [Генератора сериализации XML (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) для .NET Framework, [NuGet-пакет Microsoft.XmlSerializer.Generator](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) представляет собой решение для библиотек .NET Core и .NET Standard. Он создает сборку сериализации XML для содержащихся в сборке типов, улучшая производительность при запуске сериализации или десериализации XML для объектов этих типов с помощью <xref:System.Xml.Serialization.XmlSerializer>.
