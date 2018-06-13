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
manager: markl
ms.openlocfilehash: 59f0441b79244eb529be338495c32af886a5f2b3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745101"
---
# <a name="startup-settings-schema"></a>Схема параметров запуска
Параметры запуска определяют версию среды CLR, в которой должно выполняться приложение.  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<requiredRuntime>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|Указывает, что приложение поддерживает только версию 1.0 среды CLR. Приложения, созданные с помощью среды выполнения версии 1.1, должны использовать элемент **\<supportedRuntime>**.|  
|[\<supportedRuntime>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|Указывает, какие версии среды CLR поддерживает приложение.|  
|[\<startup>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)|Содержит элементы **\<requiredRuntime>** и **\<supportedRuntime>**.|  
  
## <a name="see-also"></a>См. также  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<PaveOver> Указание используемой версии среды выполнения](http://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
