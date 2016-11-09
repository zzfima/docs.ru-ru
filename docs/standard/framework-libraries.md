---
title: "Библиотеки платформы"
description: "Библиотеки платформы"
keywords: .NET, .NET Core
author: richlander
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 7b77b6c1-8367-4602-bff3-91e4c05ac643
translationtype: Human Translation
ms.sourcegitcommit: 093b852fe1ed2307ebce914381fe47388b435c95
ms.openlocfilehash: 7283ed099cefa4b0e137869724f8e87dda0d451a

---

# <a name="framework-libraries"></a>Библиотеки платформы

Платформа .NET имеет обширный стандартный набор библиотек классов, которые называются библиотеками базовых классов (базовый набор) или библиотеками классов платформы (полный набор). Эти библиотеки предоставляют реализации для многих общих и зависящих от приложений типов, алгоритмы, а также функциональные возможности. Как коммерческие библиотеки, так и библиотеки, предоставленные сообществом, основаны на библиотеках классов платформы, что позволяет получить удобные готовые библиотеки для обширного набора вычислительных задач.

Определенный набор таких библиотек предоставляется с каждой реализацией .NET. API в библиотеке базовых классов (BCL) могут иметь любую реализацию .NET, так как они интересуют разработчиков и требуются популярным библиотекам для выполнения. Библиотеки для конкретных приложений, основанные на библиотеке базовых классов, такой как ASP.NET, будут доступны не во всех реализациях .NET.

## <a name="base-class-libraries"></a>Библиотеки базовых классов

Библиотеки BCL предоставляют большинство фундаментальных типов и программных функций и являются основой для всех других библиотек классов .NET. Их задача — предоставить наиболее общие реализации без возможного смещения в сторону какой-либо рабочей нагрузки. Производительность всегда имеет важное значение, так как приложения могут предпочитать определенную политику, например низкую задержку вместо высокой пропускной способности или малый объем занимаемой памяти вместо низкой загрузки ЦП. В общем случае эти библиотеки должны демонстрировать высокую производительность и представлять золотую середину с точки зрения различных подходов к производительности. Для большинства приложений такой подход уже доказал свою эффективность.

## <a name="primitive-types"></a>Типы-примитивы

.NET включает набор типов-примитивов, которые (в разной степени) используются во всех приложениях. Эти типы содержат данные, например числа, строки, байты и произвольные объекты. Язык C# содержит ключевые слова для таких типов. Ниже приведен некоторый набор этих типов с соответствующими ключевыми словами C#.

*   [System.Object](https://msdn.microsoft.com/library/system.object.aspx) ([object](https://msdn.microsoft.com/library/9kkx3h3c.aspx))  — исходный базовый класс в системе типов CLR. Это корень иерархии типов.
*   [System.Int16](https://msdn.microsoft.com/library/system.int16.aspx) ([short](https://msdn.microsoft.com/library/ybs77ex4.aspx)) — 16-разрядный целочисленный тип со знаком. Также имеется и [UInt16](https://msdn.microsoft.com/library/system.uint16.aspx) без знака.
*   [System.Int32](https://msdn.microsoft.com/library/system.int32.aspx) ([int](https://msdn.microsoft.com/library/5kzh1b5w.aspx)) — 32-разрядный целочисленный тип со знаком. Также имеется и [UInt32](https://msdn.microsoft.com/library/x0sksh43.aspx) без знака.
*   [System.Single](https://msdn.microsoft.com/library/system.single.aspx) ([float](https://msdn.microsoft.com/library/b1e65aza.aspx)) — 32-разрядный тип с плавающей запятой.
*   [System.Decimal](https://msdn.microsoft.com/library/system.decimal.aspx) ([decimal](https://msdn.microsoft.com/library/364x0z75.aspx)) — 128-разрядный десятичный тип.
*   [System.Byte](https://msdn.microsoft.com/library/system.byte.aspx) ([byte](https://msdn.microsoft.com/library/5bdb6693.aspx)) — 8-разрядный целочисленный тип без знака, который представляет байт памяти.
*   [System.Boolean](https://msdn.microsoft.com/library/system.boolean.aspx) ([bool](https://msdn.microsoft.com/library/c8f5xwh7.aspx)) — логический тип, который представляет значение "true" или "false".
*   [System.Char](https://msdn.microsoft.com/library/system.char.aspx) ([char](https://msdn.microsoft.com/library/x9h8tsay.aspx)) — 16-разрядный числовой тип, который представляет символ в Юникоде.
*   [System.String](https://msdn.microsoft.com/library/system.string.aspx) ([string](https://msdn.microsoft.com/library/362314fe.aspx)) — представляет набор символов. Отличается от `char[]`, но позволяет индексировать по каждому отдельному `char` в `string`.

## <a name="data-structures"></a>Структуры данных

.NET содержит набор структур данных, которые пригодятся практически в любом приложении .NET. В основном это коллекции, но присутствуют и другие типы.

*   [Array](https://msdn.microsoft.com/library/system.array.aspx) — представляет массив строго типизированных объектов, доступных по индексу. Имеет фиксированный размер, соответствующий конструкции.
*   [List](https://msdn.microsoft.com/library/6sh2ey19.aspx) — представляет строго типизированный список объектов, доступных по индексу. Его размер изменяется автоматически по мере надобности.
*   [Dictionary](https://msdn.microsoft.com/library/xfhwa508.aspx) — представляет коллекцию значений, которые индексируются по ключу. Обратиться к значениям можно с помощью ключа. Его размер изменяется автоматически по мере надобности.
*   [Uri](https://msdn.microsoft.com/library/system.uri.aspx) — обеспечивает объектное представление универсального кода ресурсов (URI), а также простой доступ к его частям.
*   [DateTime](https://msdn.microsoft.com/library/system.datetime.aspx) — представляет текущее время, обычно выраженное как дата и время суток.

## <a name="utility-apis"></a>Служебные API

.NET содержит набор служебных API, которые предоставляют функциональные возможности для множества важных задач.

*   [HttpClient](https://msdn.microsoft.com/library/system.net.http.httpclient.aspx) — API для отправки HTTP-запросов и получения HTTP-ответов от ресурса с заданным URI.
*   [XDocument](https://msdn.microsoft.com/library/system.xml.linq.xdocument.aspx) — API для загрузки и запроса XML-документов с помощью LINQ.
*   [StreamReader](https://msdn.microsoft.com/library/system.io.streamreader.aspx) — API для чтения файлов ([StreamWriter](https://msdn.microsoft.com/library/system.io.stringwriter.aspx)), который может использоваться и для их записи.

## <a name="appmodel-apis"></a>API моделей приложений

Существует множество моделей приложений от разных компаний, которые можно использовать с платформой .NET.

*   [ASP.NET](http://asp.net) — предоставляет веб-платформу для создания веб-сайтов и служб. Поддерживается в Windows, Linux и macOS (зависит от версии ASP.NET).



<!--HONumber=Nov16_HO1-->


