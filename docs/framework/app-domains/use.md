---
title: "Использование доменов приложений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "домены приложений, сведения"
  - "среда CLR, домены приложений"
  - "среда выполнения, домены приложений"
ms.assetid: c6d99815-e022-4d2c-9420-1d7ab5b9d504
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Использование доменов приложений
Домены приложений предоставляют единицу изоляции для среды CLR.  Они создаются и выполняются внутри процесса.  Домены приложений обычно создаются хостом среды выполнения — приложением, ответственным за загрузку в процесс среды выполнения и выполнение пользовательского кода внутри домена приложения.  Хост среды выполнения создает процесс и домен приложения по умолчанию, а также выполняет внутри него управляемый код.  Хосты среды выполнения включают в себя ASP.NET, Microsoft Internet Explorer и оболочку Windows.  
  
 Для большинства приложений нет необходимости создавать собственный домен приложения: хост среды выполнения создает любые требуемые домены самостоятельно.  Однако можно создать и настроить дополнительные домены приложений, если приложению необходимо изолировать код, а также для использования и выгрузки библиотек DLL.  
  
## В этом подразделе  
 [Практическое руководство. Создание домена приложения](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)  
 Описание способа программного создания домена приложения.  
  
 [Практическое руководство. Выгрузка домена приложения](../../../docs/framework/app-domains/how-to-unload-an-application-domain.md)  
 Описание способа программной выгрузки домена приложения.  
  
 [Практическое руководство. Настройка домена приложения](../../../docs/framework/app-domains/how-to-configure-an-application-domain.md)  
 Начальные сведения о настройке домена приложения.  
  
 [Извлечение сведений о настройке из домена приложения](../../../docs/framework/app-domains/retrieve-setup-information.md)  
 Описание способа загрузки сведений о настройке из домена приложения.  
  
 [Практическое руководство. Загрузка сборок в домен приложения](../../../docs/framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)  
 Описание способа загрузки сборок в домен приложения.  
  
 [Практическое руководство. Получение сведений о типах и членах из сборки](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 Описание способа получения сведений о сборке.  
  
 [Теневое копирование сборок](../../../docs/framework/app-domains/shadow-copy-assemblies.md)  
 Описание того, как теневое копирование позволяет обновлять сборки во время их использования и как настроить теневое копирование.  
  
 [Практическое руководство. Получение уведомлений о первом этапе обработки исключений](../../../docs/framework/app-domains/how-to-receive-first-chance-exception-notifications.md)  
 Объясняет, как можно получать уведомления о возникновении исключений до того, как среда CLR начнет искать обработчики исключений.  
  
 [Разрешение загрузки сборок](../../../docs/framework/app-domains/resolve-assembly-loads.md)  
 Руководство по использованию события <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> для разрешения проблем при загрузке сборок.  
  
## Ссылка  
 <xref:System.AppDomain>  
 Представляет домен приложения.  Описание методов для создания и управления доменами приложений.  
  
## Связанные подразделы  
 [Сборки в среде CLR](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 Общие сведения о функциях, выполняемых сборками.  
  
 [Программирование с использованием сборок](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 Описание способов создания, подписи и установки атрибутов сборок.  
  
 [Emitting Dynamic Methods and Assemblies](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 Описание способов создания динамических сборок.  
  
 [Домены приложений](../../../docs/framework/app-domains/application-domains.md)  
 Общие сведения о доменах приложений.  
  
 [Общие сведения об отражении](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Использование класса **Отражение** для получения сведений о сборке.