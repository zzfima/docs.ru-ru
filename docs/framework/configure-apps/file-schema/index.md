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
ms.openlocfilehash: c3b5518b4b86c2e6f47825d552f49579c5ac0a6d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921032"
---
# <a name="configuration-file-schema-for-the-net-framework"></a><span data-ttu-id="d562c-102">Схема файлов конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d562c-102">Configuration file schema for the .NET Framework</span></span>

<span data-ttu-id="d562c-103">Файлы конфигурации — это стандартные XML-файлы, которые можно использовать для изменения параметров и установки политик для приложений.</span><span class="sxs-lookup"><span data-stu-id="d562c-103">Configuration files are standard XML files that you can use to change settings and set policies for your apps.</span></span> <span data-ttu-id="d562c-104">Схема конфигурации .NET Framework состоит из элементов, которые можно использовать в файлах конфигурации для управления поведением приложений.</span><span class="sxs-lookup"><span data-stu-id="d562c-104">The .NET Framework configuration schema consists of elements that you can use in configuration files to control the behavior of your apps.</span></span> <span data-ttu-id="d562c-105">Оглавление данного раздела отражает иерархию схемы для запуска, среды выполнения, сети и других типов параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d562c-105">The table of contents for this section reflects the schema hierarchy for startup, runtime, network, and other types of configuration settings.</span></span>

<span data-ttu-id="d562c-106">Сведения о типах, формате и расположении файлов конфигурации см. в статье [Настройка приложений](../index.md).</span><span class="sxs-lookup"><span data-stu-id="d562c-106">For information about the types, format, and location of configuration files, see the article [Configuring Apps](../index.md).</span></span> <span data-ttu-id="d562c-107">Для редактирования файлов конфигурации напрямую необходимо иметь представление о языке XML.</span><span class="sxs-lookup"><span data-stu-id="d562c-107">Familiarize yourself with XML if you want to edit the configuration files directly.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d562c-108">В тегах и атрибутах XML в файлах конфигурации учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="d562c-108">XML tags and attributes in configuration files are case-sensitive.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d562c-109">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="d562c-109">In this section</span></span>

<span data-ttu-id="d562c-110">[Элемент **\<configuration>** ](configuration-element.md). Описание элемента `<configuration>`, который является элементом верхнего уровня для всех файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d562c-110">[**\<configuration>** Element](configuration-element.md) Describes the `<configuration>` element, which is the top-level element for all configuration files.</span></span>

<span data-ttu-id="d562c-111">[Элемент **\<assemblyBinding>** ](assemblybinding-element-for-configuration.md) Определяет политику привязки сборок на уровне конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d562c-111">[**\<assemblyBinding>** Element](assemblybinding-element-for-configuration.md) Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="d562c-112">[Элемент **\<linkedConfiguration>** ](linkedconfiguration-element.md). Задает файл конфигурации, который следует включить.</span><span class="sxs-lookup"><span data-stu-id="d562c-112">[**\<linkedConfiguration>** Element](linkedconfiguration-element.md) Specifies a configuration file to include.</span></span>

<span data-ttu-id="d562c-113">[Схема параметров запуска](./startup/index.md). Описание элементов, определяющих версию среды CLR, которая будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="d562c-113">[Startup Settings Schema](./startup/index.md) Describes the elements that specify which version of the common language runtime to use.</span></span>

<span data-ttu-id="d562c-114">[Схема параметров среды выполнения](./runtime/index.md). Описание элементов настройки привязки сборок и поведения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d562c-114">[Runtime Settings Schema](./runtime/index.md) Describes the elements that configure assembly binding and runtime behavior.</span></span>

<span data-ttu-id="d562c-115">[Схема параметров сети](./network/index.md). Описание элементов, указывающих способ подключения платформы .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="d562c-115">[Network Settings Schema](./network/index.md) Describes the elements that specify how the .NET Framework connects to the Internet.</span></span>

<span data-ttu-id="d562c-116">[Схема параметров шифрования](./cryptography/index.md). Описание элементов, с помощью которых можно сопоставить понятные имена алгоритмов с классами, реализующими алгоритмы шифрования.</span><span class="sxs-lookup"><span data-stu-id="d562c-116">[Cryptography Settings Schema](./cryptography/index.md) Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

<span data-ttu-id="d562c-117">[Схема разделов конфигурации](configuration-sections-schema.md). Описание элементов, используемых для создания и применения разделов конфигурации с пользовательскими параметрами.</span><span class="sxs-lookup"><span data-stu-id="d562c-117">[Configuration Sections Schema](configuration-sections-schema.md) Describes the elements used to create and use configuration sections for custom settings.</span></span>

<span data-ttu-id="d562c-118">[Схема параметров трассировки и отладки](./trace-debug/index.md). Описание элементов, определяющих переключатели и прослушиватели трассировки.</span><span class="sxs-lookup"><span data-stu-id="d562c-118">[Trace and Debug Settings Schema](./trace-debug/index.md) Describes the elements that specify trace switches and listeners.</span></span>

<span data-ttu-id="d562c-119">[Схема параметров поставщиков языков и компиляторов](./compiler/index.md). Параметры поставщиков языков и компиляторов определяют элементы конфигурации компиляторов для доступных поставщиков языков.</span><span class="sxs-lookup"><span data-stu-id="d562c-119">[Compiler and Language Provider Settings Schema](./compiler/index.md) Describes the elements that specify compiler configuration for available language providers.</span></span>

<span data-ttu-id="d562c-120">[Схема прикладных параметров](application-settings-schema.md). Описание элементов, позволяющих приложению Windows Forms или ASP.NET сохранять и извлекать параметры области определения приложения и параметры области пользователя.</span><span class="sxs-lookup"><span data-stu-id="d562c-120">[Application Settings Schema](application-settings-schema.md) Describes the elements that enable a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span>

<span data-ttu-id="d562c-121">[Схема параметров приложения](./appsettings/index.md). Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="d562c-121">[App Settings Schema](./appsettings/index.md) Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="d562c-122">[Схема веб-параметров](./web/index.md). Все элементы схемы веб-параметров, в том числе элементы настройки способов работы ASP.NET с ведущими приложениями, такими как службы IIS.</span><span class="sxs-lookup"><span data-stu-id="d562c-122">[Web Settings Schema](./web/index.md) All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="d562c-123">Используются в файлах *Aspnet.config*.</span><span class="sxs-lookup"><span data-stu-id="d562c-123">Used in *Aspnet.config* files.</span></span>

<span data-ttu-id="d562c-124">[Схема конфигурации Windows Forms](winforms/index.md). Все элементы в разделе конфигурации приложения Windows Forms, который включает в себя такие настройки, как поддержка нескольких мониторов и высокого DPI.</span><span class="sxs-lookup"><span data-stu-id="d562c-124">[Windows Forms Configuration Schema](winforms/index.md) All elements in the Windows Forms application configuration section, which includes customizations such as multi-monitor and high DPI support.</span></span>

<span data-ttu-id="d562c-125">[Схема конфигурации WCF](./wcf/index.md). Все элементы, которые позволяют настроить службу WCF и клиентские приложения.</span><span class="sxs-lookup"><span data-stu-id="d562c-125">[WCF Configuration Schema](./wcf/index.md) All elements that enable you to configure WCF service and client applications.</span></span>

<span data-ttu-id="d562c-126">[Синтаксис директивы WCF](./wcf-directive/index.md). Описание директивы `@ServiceHost`, которая определяет относящиеся к странице атрибуты, используемые компилятором SVC.</span><span class="sxs-lookup"><span data-stu-id="d562c-126">[WCF Directive Syntax](./wcf-directive/index.md) Describes the `@ServiceHost` directive, which defines page-specific attributes used by the .svc compiler.</span></span>

<span data-ttu-id="d562c-127">[Схема конфигурации WIF](windows-identity-foundation/index.md). Все элементы схемы конфигурации Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="d562c-127">[WIF Configuration Schema](windows-identity-foundation/index.md) All elements of the Windows Identity Foundation (WIF) configuration schema.</span></span>

## <a name="related-sections"></a><span data-ttu-id="d562c-128">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="d562c-128">Related sections</span></span>

<span data-ttu-id="d562c-129">[Схема параметров удаленного взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)). Описание элементов, настраивающих клиентские и серверные приложения, реализующие удаленное взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="d562c-129">[Remoting Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)) Describes the elements that configure client and server applications that implement remoting.</span></span>

<span data-ttu-id="d562c-130">[Схема параметров ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)). Описание элементов, управляющих поведением веб-приложений ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d562c-130">[ASP.NET Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)) Describes the elements that control the behavior of ASP.NET Web applications.</span></span>

<span data-ttu-id="d562c-131">[Схема параметров веб-служб](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)). Описание элементов, которые управляют поведением веб-служб ASP.NET и их клиентов.</span><span class="sxs-lookup"><span data-stu-id="d562c-131">[Web Services Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)) Describes the elements that control the behavior of ASP.NET Web services and their clients.</span></span>

<span data-ttu-id="d562c-132">[Настройка приложений .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100)). Описание способов настройки безопасности, привязки сборок и удаленного взаимодействия в платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d562c-132">[Configuring .NET Framework Apps](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100)) Describes how to configure security, assembly binding, and remoting in the .NET Framework.</span></span>
