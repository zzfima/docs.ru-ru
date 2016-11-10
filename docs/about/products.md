---
title: "Продукты .NET"
description: "Продукты .NET"
keywords: .NET, .NET Core
author: richlander
manager: wpickett
ms.date: 06/23/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 2e38e9d9-8284-46ee-a15f-199adc4f26f4
translationtype: Human Translation
ms.sourcegitcommit: 15c55a87beb64f265a164db918c7721c7690fadf
ms.openlocfilehash: 90deb1903eea6ae1336326ca91f1e7863485dfd1

---

# <a name="net-products"></a>Продукты .NET

.NET — это очень гибкая, универсальная и принципиально кроссплатформенная [спецификация](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md) для разработки программных продуктов. Она используется для всех наиболее популярных типов приложений: классических, мобильных, облачных, игровых и IoT.

В этом документе используется два немного разных термина:

- "продукт .NET" — позволяет создавать приложения для одной или нескольких целевых платформ;
- "реализация .NET" — сочетание среды выполнения, платформы разработки и средств, которые могут выполнять "код .NET", на котором основаны продукты.

## <a name="product-categories"></a>Категории продуктов

Продукты .NET доступны во всех следующих категориях.

### <a name="desktop"></a>Рабочий стол

Классические настольные приложения можно создавать для Windows и macOS.

- [Универсальные приложения Windows](https://developer.microsoft.com/windows) с [.NET Native](#net-native)
- [Windows Presentation Foundation (WPF)](https://msdn.microsoft.com/library/ms754130.aspx) для Windows с [.NET Framework](#net-framework)
- [Windows Forms](https://msdn.microsoft.com/library/dd30h2yb.aspx) для Windows с [.NET Framework](#net-framework)
- Cocoa для macOS с [Xamarin](#xamarin-sdk)
- [Electron](http://electron.atom.io/) для кроссплатформенных настольных систем с [electron-edge](https://github.com/kexplo/electron-edge)

### <a name="games"></a>Игры

Игры можно создавать для многих настольных ПК, мобильных, консольных и виртуальных устройств, а также устройств дополненной реальности.

- [CRYENGINE](http://docs.cryengine.com/display/CEPROG/CE%23+Programming) с [Mono](#mono)
- [MonoGame](http://www.monogame.net/documentation/?page=main) с [Mono](#mono)
- [Unity](http://docs.unity3d.com/Manual/index.html) с [Mono](#mono)

### <a name="iot"></a>IoT

Можно создавать приложения IoT для Windows 10 IoT Core, включая Raspberry Pi 2/3.

- [Windows 10 IoT Core](https://developer.microsoft.com/windows/iot) с [.NET Native](#net-native)

### <a name="mobile"></a>Мобильный

Можно создавать мобильные приложения для iOS, Android и Windows.

- Приложение iOS с [Xamarin](#xamarin-sdk)
- Приложение Android с [Xamarin](#xamarin-sdk)
- [Универсальное приложение Windows](https://developer.microsoft.com/windows) с [.NET Native](#net-native)

### <a name="web-and-cloud"></a>Веб и облако

Можно создавать облачные и веб-приложения для Windows и Linux.

- [ASP.NET](http://www.asp.net/) для Windows с [.NET Framework](#net-framework)
- [ASP.NET Core](http://docs.asp.net/) для Windows, macOS и Linux с [.NET Core](#net-core)

## <a name="net-implementations"></a>Реализации .NET

Ниже в алфавитном порядке перечислены основные коммерческие реализации, а также реализации .NET с открытым исходным кодом.

### <a name="net-core"></a>.NET Core

.NET Core используется для создания приложений для устройств, веб-приложений, облачных, встроенных и IoT-приложений. Эта реализация имеет [открытый исходный код](https://github.com/dotnet/core) и является кроссплатформенной, поддерживая Windows, Linux и macOS. [ASP.NET Core](http://docs.asp.net/) является наиболее популярной рабочей нагрузкой для .NET Core. Ее можно использовать для создания веб-приложений и служб для локальной среды и облачного развертывания. .NET Core также можно использовать для создания средств, служебных программ и облачных рабочих приложений.

- Дополнительные сведения о [.NET Core](../core/index.md)
- Дополнительные сведения об [ASP.NET Core](http://docs.asp.net/)
- [Загрузить .NET Core](http://dot.net/core)

Ниже перечислены основные характеристики .NET Core.

**Кроссплатформенный характер** — .NET Core поддерживает три семейства операционных систем: Linux, Windows и macOS. Приложения .NET Core являются по умолчанию кроссплатформенными. Можно писать приложения и библиотеки, которые будут выполняться на поддерживаемых операционных системах без изменений.

**Открытый исходный код** - [ — реализация .NET Core](https://github.com/dotnet/core) доступна в службе GitHub по лицензии [MIT](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT) и [Apache 2](https://github.com/dotnet/roslyn/blob/master/License.txt) (покомпонентное лицензирование). Документация распространяется по лицензии [CC-BY](https://github.com/dotnet/docs/blob/master/license.txt). В .NET Core также используется значительный набор модулей с открытым исходным кодом, которые перечисляются в [заметках о выпуске .NET Core](https://github.com/dotnet/core/releases). 

**Простота приобретения** — .NET Core распространяется в разных видах в соответствии с потребностями разработчиков. Вы можете получить .NET Core в составе установщика [SDK .NET Core](https://dot.net/core) (или в виде архива) или с помощью диспетчеров пакетов конкретной ОС, таких как APT и Yum. [Официальные образы .NET Core Docker](https://hub.docker.com/r/microsoft/dotnet/) доступны на Docker Hub. Библиотеки платформы более высокого уровня и экосистема библиотеки .NET доступны на [NuGet](http://www.nuget.org/). 

**Модульная платформа** — .NET Core имеет модульную архитектуру, что позволяет приложениям включать только необходимые библиотеки и зависимости .NET Core. Каждое приложение использует свои версии .NET Core, что устраняет конфликты с общими компонентами. Этот подход соответствует актуальной тенденции в разработке программного обеспечения, предусматривающей использование контейнеров, таких как Docker.

### <a name="net-framework"></a>.NET Framework

Платформа .NET Framework используется для создания приложений для Windows и Windows Server. Ее можно использовать для создания многофункциональных пользовательских интерфейсов с помощью Windows Presentation Framework (WPF) и Windows Forms. Она также поддерживает создание серверных приложений с помощью ASP.NET Web Forms, ASP.NET MVC и Windows Communication Framework (WCF). Visual Studio предоставляет широкие возможности конструктора для платформы .NET Framework, упрощая создание клиентских и серверных приложений. Эта система является лучшим вариантом для написания приложений для Windows.

- Дополнительные сведения о [.NET Framework](https://msdn.microsoft.com/library/w0x726c2.aspx)
- [Загрузить .NET Framework](https://dot.net)

[Windows Forms](https://msdn.microsoft.com/library/dd30h2yb.aspx) позволяет создавать пользовательский интерфейс для классических настольных приложений в стиле "формы поверх данных" быстрее, чем с помощью любой другой технологии. В этом интерфейсе есть конструктор, который позволяет работать с элементами управления пользовательского интерфейса и другими элементами управления путем перетаскивания, сводя большинство задач разработки до простых жестов и создания концептуальной модели.

[Windows Presentation Foundation (WPF)](https://msdn.microsoft.com/library/ms754130.aspx) отделяет код и пользовательский интерфейс за счет описания пользовательского интерфейса с помощью языка разметки [XAML](https://msdn.microsoft.com/library/ms752059.aspx). Система WPF очень гибка и часто используется для пользовательских интерфейсов, в которых требуется более сложная пользовательская модель или более элегантный внешний вид.

[Windows Communication Foundation (WCF)](https://msdn.microsoft.com/library/ms731082.aspx) представляет собой набор библиотек для веб-служб SOAP. Эта программная платформа позволяет создавать службы, которые могут взаимодействовать через различные поддерживаемые протоколы с помощью различных форматов данных, а также могут размещаться в любых нужных процессах. Это определяет одну из основных особенностей WCF: службы не привязаны к какой-либо конкретной стратегии размещения.

[ASP.NET](http://www.asp.net/) — это веб-платформа. В ней есть несколько отдельных частей, которые используются для создания современных и высокопроизводительных веб-приложений. 

- [ASP.NET Web Forms](http://www.asp.net/web-forms) позволяет создавать интерфейс в стиле "формы поверх данных" быстрее, чем большинство других веб-технологий, благодаря конструктору, поддерживающему перетаскивание веб-элементов управления. 
- [ASP.NET MVC](http://www.asp.net/mvc) предоставляет больший контроль над всем веб-конвейером, начиная с уровня HTTP и заканчивая пользовательским интерфейсом. 
- [ASP.NET WebAPI](http://www.asp.net/web-api) — это платформа на базе соглашений для создания служб REST. 
- [SignalR](http://www.asp.net/signalr) позволяет создавать push-взаимодействие с веб-приложениями с помощью протокола [WebSocket](https://en.wikipedia.org/wiki/WebSocket).

### <a name="net-native"></a>.NET Native

.NET Native — это набор встроенных средств сборки для .NET Core. .NET Native представляет собой цепочку инструментов предварительной (AOT) компиляции, которые создают собственные приложения путем компиляции байт-кода промежуточного языка в машинный код. Это означает, что в результате получается двоичный файл, выполняемый операционной системой. Нет никакой компиляции "на лету", во время выполнения. Это оптимизирует скорость запуска, а также дает некоторые преимущества в плане безопасности.

.NET Native в основном используется в приложениях .NET [Universal Windows Platform (UWP)](https://msdn.microsoft.com/library/windows/apps/dn726767.aspx).

### <a name="mono"></a>Mono

[Mono](http://www.mono-project.com/docs/about-mono/) — это оригинальная кроссплатформенная реализация .NET с открытым исходным кодом от сообщества [Mono Project](http://mono-project.com). Теперь она поддерживается корпорацией Майкрософт. Ее можно рассматривать как открытую и кроссплатформенную версию платформы .NET Framework. Ее API выпускаются следом за .NET Framework, а не .NET Core.

Mono состоит из нескольких компонентов:

**Компилятор C#**. Компилятор C# в Mono полностью поддерживает C# 6.

**Среда выполнения Mono**. Среда выполнения реализует ECMA Common Language Infrastructure (CLI). Среда выполнения предоставляет компилятор времени выполнения (JIT), предварительный компилятор (AOT), загрузчик библиотеки, сборщик мусора, систему потоков и функции взаимодействия.

**Базовая библиотека классов**. Платформа Mono предоставляет исчерпывающий набор классов, обеспечивающих солидную основу для создания приложений. Эти классы совместимы с классами Microsoft .Net Framework.

**Библиотека классов Mono**. Mono также предоставляет множество классов сверх базовой библиотеки классов, предоставляемых .NET Framework. Они предлагают дополнительные возможности, которые особенно полезны при создании приложений Linux. Например, это классы для Gtk+, ZIP-файлов, LDAP, OpenGL, Cairo, POSIX, и т. д.

### <a name="xamarin-sdk"></a>Xamarin SDK

[Xamarin SDK](http://open.xamarin.com) используется для создания собственных мобильных приложений и приложений для устройств, в основном для экосистемы Apple и Google. Он основан на Mono и имеет открытый исходный код с лицензией MIT. Его можно использовать для создания приложений iOS и Android для телефонов, планшетов и часов. [Xamarin.Forms](https://www.xamarin.com/forms) — это популярное средство для создания универсальных пользовательских интерфейсов для приложений Apple, Google и Windows.

- Дополнительные сведения об [SDK Xamarin](https://developer.xamarin.com/)
- [Загрузить Xamarin](https://www.xamarin.com/platform)



<!--HONumber=Nov16_HO1-->


