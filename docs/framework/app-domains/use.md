---
title: "Использование доменов приложений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application domains, about
- common language runtime, application domains
- runtime, application domains
ms.assetid: c6d99815-e022-4d2c-9420-1d7ab5b9d504
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eade3728c8a51785214cf3d8de53d8a64a668f1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="using-application-domains"></a>Использование доменов приложений
Домены приложений предоставляют изолированный модуль для среды CLR. Они создаются и выполняются внутри процесса. Домены приложений обычно создаются хост-приложением среды выполнения — приложением, ответственным за загрузку среды выполнения в процесс и выполнение пользовательского кода внутри домена приложения. Хост-приложение среды выполнения создает процесс и домен приложения по умолчанию, а также выполняет внутри него управляемый код. Хост-приложения среды выполнения включают в себя ASP.NET, Microsoft Internet Explorer и оболочку Windows.  
  
 Для большинства приложений нет необходимости создавать собственный домен приложения: хост-приложение среды выполнения создает все требуемые домены автоматически. Но вы можете создать и настроить дополнительные домены приложений, если приложению необходимо изолировать код или использовать и выгружать библиотеки DLL.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Создание домена приложения](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)  
 Описание того, как создать домен приложения программным способом.  
  
 [Практическое руководство. Выгрузка домена приложения](../../../docs/framework/app-domains/how-to-unload-an-application-domain.md)  
 Описание того, как выгрузить домен приложения программным способом.  
  
 [Практическое руководство. Настройка домена приложения](../../../docs/framework/app-domains/how-to-configure-an-application-domain.md)  
 Содержит общие сведения о настройке домена приложения.  
  
 [Извлечение сведений о настройке из домена приложения](../../../docs/framework/app-domains/retrieve-setup-information.md)  
 Описание того, как извлечь сведения о настройке из домена приложения.  
  
 [Практическое руководство. Загрузка сборок в домен приложения](../../../docs/framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)  
 Описание того, как загрузить сборку в домен приложения.  
  
 [Практическое руководство. Получение сведений о типах и членах из сборки](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 Описание того, как получить сведения о сборке.  
  
 [Теневое копирование сборок](../../../docs/framework/app-domains/shadow-copy-assemblies.md)  
 Описание того, как теневое копирование позволяет обновлять сборки во время их использования и как настроить теневое копирование.  
  
 [Практическое руководство. Получение уведомлений о первом этапе обработки исключений](../../../docs/framework/app-domains/how-to-receive-first-chance-exception-notifications.md)  
 Описывается, как можно получать уведомления о создании исключений до того, как среда CLR начнет искать обработчики исключений.  
  
 [Разрешение загрузки сборок](../../../docs/framework/app-domains/resolve-assembly-loads.md)  
 Содержит инструкции по использованию события <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> для разрешения сбоев загрузки сборок.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.AppDomain>  
 Представляет домен приложения. Предоставляет методы для создания доменов приложений и управления ими.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Сборки в среде CLR](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 Предоставляет обзор функций, которые выполняются сборками.  
  
 [Программирование с использованием сборок](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 Описание способов создания, подписи и установки атрибутов сборок.  
  
 [Предоставление динамических методов и сборок](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 Описание способов создания динамических сборок.  
  
 [Домены приложений](../../../docs/framework/app-domains/application-domains.md)  
 Общие сведения о доменах приложений.  
  
 [Общие сведения о классе Reflection](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Использование класса **Reflection** для получения сведений о сборке.
