---
title: "Схема файлов конфигурации для .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "конфигурация приложений .NET Framework, схема конфигурации"
  - "файлы app.config, схема"
  - "файлы конфигурации приложений, схема"
  - "разработка приложений [платформа .NET Framework], схема"
  - "схема конфигурации [платформа .NET Framework]"
  - "параметры конфигурации [платформа .NET Framework], приложения"
  - "теги контейнеров"
  - "файлы конфигурации enterprisesec"
  - "файлы enterprisesec.config"
  - "файлы конфигурации компьютера"
  - "файлы machine.config"
  - "параметры конфигурации схемы"
  - "схемы, параметры конфигурации"
  - "безопасность [платформа .NET Framework], файлы конфигурации"
  - "файлы security.config"
  - "правильные документы XML"
  - "XML-теги"
ms.assetid: 69003d39-dc8a-460c-a6be-e6d93e690b38
caps.latest.revision: 20
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 18
---
# Схема файлов конфигурации для .NET Framework
Файлы конфигурации — это стандартные XML\-файлы, которые можно использовать для изменения параметров и установки политик для приложений.  Схема конфигурации .NET Framework состоит из элементов, которые можно использовать в файлах конфигурации для управления поведением приложений.  Оглавление данного раздела отражает иерархию схемы для запуска, среды выполнения, сети и других типов параметров конфигурации.  
  
 Дополнительные сведения о типах, формате и расположении файлов конфигурации см. в разделе [Настройка приложений](../../../../docs/framework/configure-apps/index.md).  Для редактирования файлов конфигурации необходимо иметь представление о языке XML.  
  
> [!IMPORTANT]
>  В тегах и атрибутах XML в файлах конфигурации учитывается регистр.  
  
## В этом подразделе  
 [Элемент \<configuration\>](../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
 Описание элемента `<configuration>`, который является элементом верхнего уровня для всех файлов конфигурации.  
  
 [Элемент \<assemblyBinding\>](../../../../docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)  
 Определяет политику привязки сборок на уровне конфигурации.  
  
 [Элемент \<linkedConfiguration\>](../../../../docs/framework/configure-apps/file-schema/linkedconfiguration-element.md)  
 Указание файла конфигурации, который следует включить.  
  
 [Схема параметров запуска](../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 Описание элементов, определяющих версию среды CLR, которая будет использоваться.  
  
 [Схема параметров среды выполнения](../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 Описание элементов настройки привязки сборок и поведения во время выполнения.  
  
 [Схема параметров сети](../../../../docs/framework/configure-apps/file-schema/network/index.md)  
 Описание элементов, указывающих способ подключения платформы .NET Framework к Интернету.  
  
 [Схема параметров криптографии](../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 Описание элементов, с помощью которых можно сопоставить понятные имена алгоритмов с классами, реализующими алгоритмы шифрования.  
  
 [Схема разделов конфигурации](../../../../docs/framework/configure-apps/file-schema/configuration-sections-schema.md)  
 Описание элементов, используемых для создания и применения разделов конфигурации с пользовательскими параметрами.  
  
 [Схема параметров трассировки и отладки](../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 Описание элементов, определяющих переключатели и прослушиватели трассировки.  
  
 [Схема параметров поставщиков языков и компиляторов](../../../../docs/framework/configure-apps/file-schema/compiler/index.md)  
 Описание элемента, задающего параметры конфигурации компилятора для доступных поставщиков языков.  
  
 [Схема параметров приложения](../../../../docs/framework/configure-apps/file-schema/application-settings-schema.md)  
 Описание элементов, позволяющих приложению Windows Forms или ASP.NET сохранять и извлекать параметры области определения приложения и параметры области пользователя.  
  
 [Схема веб\-параметров](../../../../docs/framework/configure-apps/file-schema/web/index.md)  
 Все элементы схемы веб\-параметров, в том числе элементы настройки способов работы ASP.NET с ведущими приложениями, такими как службы IIS.  Используются в файлах aspnet.config.  
  
## Связанные подразделы  
 [Remoting Settings Schema](http://msdn.microsoft.com/ru-ru/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e)  
 Описание элементов, настраивающих клиентские и серверные приложения, реализующие удаленное взаимодействие.  
  
 [Схема параметров ASP.NET](http://msdn.microsoft.com/library/b5ysx397\(v=vs.100\).aspx)  
 Описание элемента, управляющего поведением веб\-приложений ASP.NET.  
  
 [Web Services Settings Schema](http://msdn.microsoft.com/ru-ru/f84d6d55-1add-4eb7-ae46-33df5833ea2e)  
 Описание элемента, управляющего поведением веб\-служб ASP.NET Web и их клиентов.  
  
 [Configuring .NET Framework Apps](http://msdn.microsoft.com/ru-ru/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)  
 Описание способов настройки безопасности, привязки сборок и удаленного взаимодействия в платформе .NET Framework.