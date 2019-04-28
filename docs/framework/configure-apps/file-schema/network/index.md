---
title: Схема параметров сети
ms.date: 03/30/2017
helpviewer_keywords:
- elements [.NET Framework], network configuration elements
- sending data, network configuration elements
- receiving data, network configuration elements
- configuration settings [.NET Framework], networks
- Internet, network configuration elements
- network configuration elements
- network settings
- connections [.NET Framework], network configuration elements
- network resources, network configuration elements
ms.assetid: f1de5a0f-76c5-4833-819f-5222b8146340
ms.openlocfilehash: 71d945e6046a8648a812de939f197429bc695808
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674536"
---
# <a name="network-settings-schema"></a>Схема параметров сети
Параметры сети определяют способ подключения .NET Framework к Интернету. В приведенной ниже таблице описывается назначение каждого дочернего элемента конфигурации для [элемента \<system.Net> (параметры сети)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md).  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[Элемент \<authenticationModules> (параметры сети)](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|Определяет модули, используемые для проверки подлинности интернет-запросов.|  
|[Элемент \<connectionManagement> (параметры сети)](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|Задает максимальное число подключений к узлам в Интернете.|  
|[Элемент \<defaultProxy> (параметры сети)](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Задает прокси-сервер, используемый для HTTP-запросов к Интернету.|  
|[Элемент \<mailSettings> (параметры сети)](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|Содержит параметры отправки почты.|  
|[Элемент \<requestCaching> (сетевые параметры)](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Определяет механизм кэширования для сетевых запросов.|  
|[Элемент \<webRequestModules> (параметры сети)](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Задает модули, используемые для запроса данных от узлов в Интернете.|  
  
 Параметры универсальных кодов ресурсов (URI) определяют, как платформа .NET Framework обрабатывает веб-адреса, выраженные с использованием URI. В приведенной ниже таблице описывается назначение каждого дочернего элемента конфигурации для [элемента \<Uri> (параметры URI)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md).  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[Элемент \<idn> (параметры URI)](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|Определяет, применяется ли к доменным именам анализ международных доменных имен (IDN).|  
|[Элемент \<iriParsing> (параметры URI)](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|Определяет, применяется ли к <xref:System.Uri> анализ международных идентификаторов ресурсов (IRI) и применяются ли правила анализа IRI.|  
|[Элемент \<schemeSettings> (параметры URI)](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|Определяет, как <xref:System.Uri> анализируется для определенных схем.|  
  
## <a name="see-also"></a>См. также

- [Настройка веб-приложений](../../../../../docs/framework/network-programming/configuring-internet-applications.md)
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
