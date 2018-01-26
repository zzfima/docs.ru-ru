---
title: "Конфигурация"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86a6e12f-73b5-450e-8725-f4ca5fe0702c
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bfd61ea70fcae443d4a76403ed6c10c874407c4d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="configuration"></a>Конфигурация
В этом разделе перечислены все исключения, вызываемые конфигурацией [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
## <a name="exception-list"></a>Список исключений  
  
|Код ресурса|Строка ресурса|  
|-------------------|---------------------|  
|ConfigBindingCannotBeConfigured|Не удается настроить привязку на конечной точке службы.|  
|ConfigElementKeyNull|Определенный элемент конфигурации не может иметь значение null.|  
|ConfigExtensionTypeNotRegisteredInCollection|Определенный тип расширения не зарегистрирован в определенной коллекции расширений.|  
|ConfigIndexOutOfRange|Значение определенного атрибута находится за пределами допустимого диапазона.|  
|ConfigInvalidBindingConfigurationName|В определенной конфигурации отсутствует привязка с определенным именем.|  
|ConfigInvalidBindingName|В определенной конфигурации отсутствует привязка с определенным именем. Это значение недопустимо для привязки.|  
|ConfigInvalidCommonEndpointBehaviorType|Не удается добавить определенное расширение поведения в распространенное поведение конечной точки, поскольку оно не реализует определенный тип.|  
|ConfigInvalidCommonServiceBehaviorType|Не удается добавить определенное расширение поведения в распространенное поведение службы, поскольку оно не реализует определенный тип.|  
|ConfigInvalidEndpointBehaviorType|Не удается добавить определенное расширение поведения в определенное поведение конечной точки, поскольку тип базового поведения не реализует интерфейс IServiceBehavior.|  
|ConfigInvalidExtensionType|Чтобы определенный тип можно было использовать в коллекции, он должен быть производным от определенного расширения.|  
|ConfigInvalidServiceBehaviorType|Не удается добавить определенное расширение поведения в поведение службы с определенным именем, поскольку тип базового поведения не реализует интерфейс IServiceBehavior.|  
|ConfigMessageEncodingAlreadyInBinding|Не удается добавить определенный элемент кодирования сообщений. В определенной привязке уже существует другой элемент кодирования сообщений. В каждой привязке может быть только один элемент кодирования сообщений.|  
|ConfigNoExtensionCollectionAssociatedWithType|Не удается найти коллекцию расширений, связанную с расширением определенного типа.|  
|ConfigSectionNotFound|Не удается создать определенный раздел конфигурации. В файле Machine.config отсутствует информация. Проверьте, правильно ли зарегистрирован этот раздел конфигурации и правильно ли указано его имя. В случае, если это раздел Windows Communication Foundation, выполните команду "ServiceModelReg.exe -i", чтобы устранить эту ошибку.|  
|ConfigTransportAlreadyInBinding|Не удается добавить определенный элемент транспорта. Другой элемент транспорта уже существует в определенной привязке. В каждой привязке может быть только один элемент кодирования сообщений.|
