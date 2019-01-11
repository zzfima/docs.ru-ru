---
title: Схема параметров запуска
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 0a03438968f487f574606f415fb9d43223030038
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222159"
---
# <a name="startup-settings-schema"></a>Схема параметров запуска

Параметры запуска определяют версию среды CLR, в которой должно выполняться приложение.  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<requiredRuntime>](requiredruntime-element.md)|Указывает, что приложение поддерживает только версию 1.0 среды CLR. Приложения, созданные с помощью среды выполнения версии 1.1, должны использовать элемент **\<supportedRuntime>**.|  
|[\<supportedRuntime>](supportedruntime-element.md)|Указывает, какие версии среды CLR поддерживает приложение.|  
|[\<startup>](startup-element.md)|Содержит элементы **\<requiredRuntime>** и **\<supportedRuntime>**.|  
  
## <a name="see-also"></a>См. также

- [Схема файла конфигурации](../index.md)  
- [Практическое руководство. Настройка приложения для поддержки .NET Framework 4 или более поздней версии](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)