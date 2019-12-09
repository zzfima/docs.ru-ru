---
title: Архитектурные компоненты .NET
description: Описание ключевых компонентов архитектуры .NET, таких как .NET Standard, реализации .NET, среды выполнения .NET и инструменты.
author: cartermp
ms.author: mairaw
ms.date: 08/23/2017
ms.technology: dotnet-standard
ms.openlocfilehash: 543f05cd52e62166b8a5ee318a588dee1e8ef76a
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838199"
---
# <a name="net-architectural-components"></a>Архитектурные компоненты .NET

Приложение .NET разрабатывается и выполняется в одной *реализации .NET* или нескольких.  К реализации .NET относятся .NET Framework, .NET Core и Mono. Существует спецификация API, общая для всех реализаций .NET, которая называется .NET Standard. В этой статье дается краткое описание каждого из этих понятий.

## <a name="net-standard"></a>.NET Standard

.NET Standard — это набор API-интерфейсов, которые реализуются библиотекой базовых классов реализации .NET. Фактически это спецификация API .NET, представляющая единый набор контрактов, на основе которых компилируется код. Эти контракты реализуются в каждой реализации .NET. Благодаря этому возможен перенос между различными реализациями .NET, что обеспечивает эффективную работу кода везде.

.NET Standard также является [целевой платформой](glossary.md#target-framework). Если код предназначен для версии .NET Standard, он будет работать в любой реализации .NET, которая поддерживает эту версию .NET Standard.

Дополнительные сведения о .NET Standard и о том, как сделать ее целевой версией, см. [здесь](net-standard.md).

## <a name="net-implementations"></a>Реализации .NET

Каждая реализация .NET включает в себя следующие компоненты.

- Одна среда выполнения или несколько. Примеры CLR для .NET Framework, CoreCLR и CoreRT для .NET Core.
- Библиотека классов, которая реализует .NET Standard, а также может реализовывать дополнительные API-интерфейсы. Примеры: библиотека базовых классов .NET Framework, библиотека базовых классов .NET Core.
- (Необязательно) Одна платформа приложений или несколько. Примеры [ASP.NET](https://www.asp.net/), [Windows Forms](../framework/winforms/windows-forms-overview.md) и [Windows Presentation Foundation (WPF)](../framework/wpf/index.md) входят в .NET Framework и .NET Core.
- (Необязательно) Средства разработки. Некоторые средства разработки, являются общими для нескольких реализаций.

Существуют четыре основные реализации .NET, которые корпорация Майкрософт активно разрабатывает и обслуживает: .NET Core, .NET Framework, Mono и UWP.

### <a name="net-core"></a>.NET Core

.NET Core — это кроссплатформенная реализация .NET, предназначенная для обработки обширного ряда серверных и облачных рабочих нагрузок. Она работает в Windows, macOS и Linux. Она реализует .NET Standard, а значит, любой код, предназначенный для .NET Standard, может работать на .NET Core. [ASP.NET](https://dotnet.microsoft.com/learn/aspnet/what-is-aspnet-core), [Windows Forms](../framework/winforms/windows-forms-overview.md) и [Windows Presentation Foundation (WPF)](../framework/wpf/index.md) работают на основе .NET Core.

Дополнительные сведения о .NET Core см. в [руководстве по .NET Core](../core/index.md) и в разделе [Выбор между .NET Core и .NET Framework для серверных приложений](choosing-core-framework-server.md).

### <a name="net-framework"></a>.NET Framework

.NET Framework является исходной реализацией .NET, выпущенной в 2002 г. Разработчики .NET всегда использовали эту платформу. Версии 4.5 и более поздние реализуют .NET Standard, а значит, любой код, предназначенный для .NET Standard, может работать в этих версиях .NET Framework. Она содержит дополнительные API для Windows, например API для разработки настольных приложений с помощью Windows Forms и WPF. .NET Framework оптимизирована для создания классических приложений Windows.

Дополнительные сведения о платформе .NET Framework см. в [руководстве по .NET Framework](../framework/index.md).

### <a name="mono"></a>Mono

Mono является реализацией .NET, которая в основном используется, если требуется небольшая среда выполнения. Это среда выполнения, которая может работать в приложениях Xamarin на Android, Mac, iOS, tvOS и watchOS, и предназначена для небольших разработок. Mono также подходит для работы игр, созданных на базе подсистемы Unity.

Она поддерживает все текущие опубликованные версии .NET Standard.

Исторически Mono реализовывала крупный API .NET Framework и эмулировала некоторые из наиболее популярных возможностей в Unix. Иногда она использовалась для запуска приложений .NET, которые применяют эти возможности в Unix.

Mono обычно используется с JIT-компилятором, но также располагает полным статическим компилятором (заблаговременная компиляция), который используется на таких платформах, как iOS.

Дополнительные сведения о Mono см. в [соответствующей документации](https://www.mono-project.com/docs/).

### <a name="universal-windows-platform-uwp"></a>Универсальная платформа Windows (UWP)

UWP представляет собой реализацию .NET, которая используется для создания современных приложений Windows с поддержкой сенсорного ввода и программного обеспечения для Интернета вещей (IoT). Она предназначена для объединения различных типов устройств, которые могут потребоваться, включая ПК, планшеты, планшетофоны, телефоны и даже Xbox. UWP предоставляет много служб, таких как централизованный магазин приложений, среда выполнения (AppContainer) и набор API-интерфейсов Windows для использования вместо Win32 (WinRT). Приложения могут быть написаны на C++, C#, VB.NET и JavaScript. При использовании C# и VB.NET API-интерфейсы .NET предоставляются .NET Core.

Дополнительные сведения о UWP см. в разделе [Введение в работу с универсальной платформой Windows](/windows/uwp/get-started/universal-application-platform-guide).

## <a name="net-runtimes"></a>Среды выполнения .NET

Среда выполнения — это среда выполнения для управляемой программы. Операционная система является частью среды выполнения, но не входит в среду выполнения .NET. Ниже приведены несколько примеров сред выполнения .NET.

- Среда CLR для .NET Framework
- Среда CoreCLR для .NET Core
- .NET Native для универсальной платформы Windows 
- Среда выполнения Mono для Xamarin.iOS, Xamarin.Android, Xamarin.Mac и платформы Mono для рабочего стола

## <a name="net-tooling-and-common-infrastructure"></a>Инструменты для .NET и общая инфраструктура

Вы можете использовать широкий набор средств и компонентов инфраструктуры, которые работают в каждой реализации платформы .NET. Они включают в себя, помимо прочих средств, следующее:

- языки .NET и соответствующие компиляторы;
- систему проектов .NET (на основе файлов *CSPROJ*, *VBPROJ* и *FSPROJ*);
- [MSBuild](/visualstudio/msbuild/msbuild), обработчик для сборки проектов;
- [NuGet](/nuget/), диспетчер пакетов корпорации Майкрософт для .NET;
- инструменты для управления сборкой с открытым исходным кодом, например [CAKE](https://cakebuild.net/) и [FAKE](https://fake.build/).

## <a name="applicable-standards"></a>Применимые стандарты

Спецификации языка C# и Common Language Infrastructure (CLI) стандартизированы в [Ecma International®](https://www.ecma-international.org/). Первые выпуски этих стандартов были опубликованы в Ecma в декабре 2001 г.

Последующие редакции стандартов были разработаны группами задач TC49-TG2 (C#) и TC49-TG3 (CLI) в рамках технического комитета по языкам программирования ([TC49](https://www.ecma-international.org/memento/tc49.htm)) и приняты в Генеральной ассамблее Ecma и затем в ISO/IEC JTC 1 в рамках процесса ISO Fast-Track.

### <a name="latest-standards"></a>Новейшие стандарты

Следующие официальные документы Ecma доступны для [C#](http://www.ecma-international.org/publications/standards/Ecma-334.htm) и [CLI](http://www.ecma-international.org/publications/standards/Ecma-335.htm) ([TR-84](http://www.ecma-international.org/publications/techreports/E-TR-084.htm)):

- **Стандарт языка C# (версия 5.0)** : [ECMA-334.pdf](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf)
- **Common Language Infrastructure**: Доступно в форматах [pdf](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-335.pdf) и [zip](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-335.zip).
- **Сведения, полученные из файла XML раздела IV**: Доступно в форматах [pdf](https://www.ecma-international.org/publications/files/ECMA-TR/ECMA%20TR-084.pdf) и [zip](https://www.ecma-international.org/publications/files/ECMA-TR/TR-084.zip).
 
Официальные документы ISO/IEC доступны на странице [общедоступных стандартов](https://standards.iso.org/ittf/PubliclyAvailableStandards/) ISO/IEC. Эти ссылки указываются непосредственно на этой странице:

- **Информационные технологии — языки программирования — C#** : [ISO/IEC 23270:2018](https://standards.iso.org/ittf/PubliclyAvailableStandards/c075178_ISO_IEC_23270_2018.zip)
- **Информационные технологии — Common Language Infrastructure (CLI), разделы I–VI**: [ISO/IEC 23271:2012](https://standards.iso.org/ittf/PubliclyAvailableStandards/c058046_ISO_IEC_23271_2012(E).zip)
- **Информационные технологии — Common Language Infrastructure (CLI) — технический отчет о данных, полученных из файла XML раздела IV**: [ISO/IEC TR 23272:2011](https://standards.iso.org/ittf/PubliclyAvailableStandards/c057955_ISO_IEC_TR_23272_2011.zip)

## <a name="see-also"></a>См. также

- [Выбор между .NET Core и .NET Framework для серверных приложений](choosing-core-framework-server.md)
- [.NET Standard](net-standard.md)
- [Руководство по .NET Core](../core/index.md)
- [Руководство по .NET Framework](../framework/index.md)
- [Руководство по языку C#](../csharp/index.yml)
- [Руководство по языку F#](../fsharp/index.yml)
- [Руководство по VB .NET](../visual-basic/index.yml)
