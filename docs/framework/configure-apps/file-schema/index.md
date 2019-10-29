---
title: Схема файлов конфигурации для .NET Framework
ms.date: 05/01/2017
helpviewer_keywords:
- .NET Framework application configuration, configuration schema
- machine configuration files
- application configuration files, schema
- app.config files, schema
- schema configuration settings
- schemas, configuration settings
- enterprisesec.config files
- well-formed XML
- enterprisesec configuration files
- security.config files
- security [.NET Framework], configuration files
- application development [.NET Framework], schema
- XML tags
- container tags
- machine.config files
- configuration schema [.NET Framework]
- configuration settings [.NET Framework], applications
- configuration file reference [.NET Framework]
ms.assetid: 69003d39-dc8a-460c-a6be-e6d93e690b38
ms.openlocfilehash: 35ed53fc480e218df595794f80af2458f3ecec38
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039159"
---
# <a name="configuration-file-schema-for-the-net-framework"></a>Схема файлов конфигурации для .NET Framework

Файлы конфигурации — это стандартные XML-файлы, которые можно использовать для изменения параметров и установки политик для приложений. Схема конфигурации .NET Framework состоит из элементов, которые можно использовать в файлах конфигурации для управления поведением приложений. Оглавление данного раздела отражает иерархию схемы для запуска, среды выполнения, сети и других типов параметров конфигурации.

Сведения о типах, формате и расположении файлов конфигурации см. в разделе [Настройка приложений](../index.md). Для редактирования файлов конфигурации напрямую необходимо иметь представление о языке XML.

> [!IMPORTANT]
> В тегах и атрибутах XML в файлах конфигурации учитывается регистр.

## <a name="in-this-section"></a>В данном разделе

[элемент **> конфигурации\<** ](configuration-element.md)\
Элемент верхнего уровня для всех файлов конфигурации.

[ **\<элемент > assemblyBinding** ](assemblybinding-element-for-configuration.md)\
Определяет политику привязки сборок на уровне конфигурации.

[ **\<элемент > линкедконфигуратион** ](linkedconfiguration-element.md)\
Указание файла конфигурации, который следует включить.

\ [схемы параметров запуска](./startup/index.md)
Элементы, указывающие используемую версию среды CLR.

\ [схемы параметров среды выполнения](./runtime/index.md)
Элементы, которые настраивают привязку сборки и поведение во время выполнения.

[Схема параметров сети](./network/index.md)\
Элементы, указывающие, как .NET Framework подключается к Интернету.

\ [схемы параметров шифрования](./cryptography/index.md)
Элементы, которые сопоставляют понятные имена алгоритмов с классами, реализующими алгоритмы шифрования.

\ [схемы разделов конфигурации](configuration-sections-schema.md)
Элементы, используемые для создания и использования разделов конфигурации для пользовательских параметров.

\ [схемы параметров трассировки и отладки](./trace-debug/index.md)
Элементы, задающих переключатели и прослушиватели трассировки.

[Схема параметров поставщика языка и компилятора](./compiler/index.md)\
Элементы, задающих конфигурацию компилятора для доступных поставщиков языков.

\ [схемы параметров приложения](application-settings-schema.md)
Элементы, которые позволяют приложению Windows Forms или ASP.NET сохранять и извлекать параметры приложения и области пользователя.

\ [схемы параметров приложения](./appsettings/index.md)
Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения.

\ [схемы веб-параметров](./web/index.md)
Элементы для настройки работы ASP.NET с ведущим приложением, например IIS. Используются в файлах *Aspnet.config*.

\ [схемы конфигурации Windows Forms](winforms/index.md)
Все элементы в разделе конфигурации приложения Windows Forms, включая настройки с поддержкой нескольких мониторов и высокого DPI.

\ [схемы конфигурации WCF](./wcf/index.md)
Все элементы, которые позволяют настроить службу WCF и клиентские приложения.

[Синтаксис директив WCF](./wcf-directive/index.md)\
Описывает директиву `@ServiceHost`, которая определяет атрибуты, зависящие от страницы, используемые компилятором SVC.

[Схема конфигурации WIF](windows-identity-foundation/index.md)\
Все элементы схемы конфигурации Windows Identity Foundation (WIF).

## <a name="related-sections"></a>Связанные разделы

\ [схемы параметров удаленного взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))
Описание элементов, настраивающих клиентские и серверные приложения, реализующие удаленное взаимодействие.

\ [схемы параметров ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))
Описание элемента, управляющего поведением веб-приложений ASP.NET.

\ [схемы параметров веб-служб](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))
Описание элемента, управляющего поведением веб-служб ASP.NET Web и их клиентов.

[Настройка приложений .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100))\
Описание способов настройки безопасности, привязки сборок и удаленного взаимодействия в платформе .NET Framework.
