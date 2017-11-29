---
title: "Интерфейс IDefinitionAppId"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDefinitionAppId
api_location: fusion.dll
api_type: COM
f1_keywords: IDefinitionAppId
helpviewer_keywords: IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 382c82ff773d0ab1c046fc131fa87a4f74d19ea6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="idefinitionappid-interface"></a>Интерфейс IDefinitionAppId
Представляет уникальный идентификатор для кода, определяющего приложение в текущей области.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|Возвращает строку форматирования, которая представляет код, в этом `IDefinitionAppId` объекта.|  
|`IDefinitionAppId::put_Codebase`|Задает код это `IDefinitionAppId` объекта на указанное значение форматированной строки.|  
|`IDefinitionAppId::EnumAppPath`|Возвращает указатель интерфейса [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) , содержащий сборки в путь текущего приложения.|  
|`IDefinitionAppId::SetAppPath`|Задает путь приложения для сборки в текущей области, на которое ссылается указанный [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) объекта.|  
|`IDefinitionAppId::get_SubscriptionId`|Получает указатель на строковое представление идентификатора маркера для подписки на это `IDefinitionAppId` объекта.|  
|`IDefinitionAppId::put_SubscriptionId`|Задает идентификатор маркера для подписки на этот `IDefinitionAppId` объекта указанному строковому значению.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Isolation.h  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Фьюжн-интерфейсы](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
