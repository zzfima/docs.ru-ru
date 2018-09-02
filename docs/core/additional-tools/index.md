---
title: Дополнительные инструменты .NET Core
description: Обзор дополнительных инструментов, которые поддерживают и расширяют функциональные возможности .NET Core.
author: mlacouture
ms.author: johalex
ms.date: 01/19/2018
ms.custom: mvc
ms.openlocfilehash: ba63ef6cdc092d06e267637112070e7cd5133a45
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43456387"
---
# <a name="net-core-additional-tools"></a>Дополнительные инструменты .NET Core

Этот раздел содержит список инструментов, которые поддерживают и расширяют функциональные возможности .NET Core вместе с инструментами [интерфейса командной строки (CLI) .NET Core](..\tools\index.md).

## <a name="wcf-web-service-reference-toolwcf-web-service-reference-guidemd"></a>[Инструмент WCF Web Service Reference](wcf-web-service-reference-guide.md)

WCF (Windows Communication Foundation) Web Service Reference — это поставщик подключенной службы для Visual Studio, впервые появившийся в [Visual Studio 2017 версии 15.5](https://visualstudio.microsoft.com/news/releasenotes/vs2017-relnotes#WCFTools). Инструмент извлекает метаданные веб-службы в текущем решении, в сетевом расположении или из файла WSDL, а затем создает совместимый с .NET Core исходный файл, определяющий прокси-класс WCF с методами, который можно использовать для доступа к операциям веб-службы.

## <a name="wcf-dotnet-svcutil-tooldotnet-svcutil-guidemd"></a>[Средство WCF dotnet-svcutil](dotnet-svcutil-guide.md)

Средство WCF (Windows Communication Foundation) dotnet-svcutil — это средство .NET Core CLI, которое извлекает метаданные веб-службы в сетевом расположении или из файла WSDL, а затем создает совместимый с .NET Core исходный файл, определяющий прокси-класс WCF с методами, который можно использовать для доступа к операциям веб-службы. Средство **dotnet-svcutil** — это альтернатива поставщика подключенной службы Visual Studio [**WCF Web Service Reference**](wcf-web-service-reference-guide.md), впервые представленного в Visual Studio 2017 15.5. Как и .NET Core CLI, средство **dotnet-svcutil** доступно на платформах Linux, macOS и Windows.

## <a name="xml-serializer-generatorxml-serializer-generatormd"></a>[Генератор сериализации XML](xml-serializer-generator.md)

Являясь аналогом [Генератора сериализации XML (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) для .NET Framework, [NuGet-пакет Microsoft.XmlSerializer.Generator](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) представляет собой решение для библиотек .NET Core и .NET Standard. Он создает сборку сериализации XML для содержащихся в сборке типов, улучшая производительность при запуске сериализации или десериализации XML для объектов этих типов с помощью <xref:System.Xml.Serialization.XmlSerializer>.