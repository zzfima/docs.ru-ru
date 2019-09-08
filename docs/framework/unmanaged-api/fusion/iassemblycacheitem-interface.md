---
title: Интерфейс IAssemblyCacheItem
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: ccc9387a-9f44-4f4f-bf8f-0ea6d2afa21b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 193604068e379d62107b25f2bc348cd7c8bc6e98
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796707"
---
# <a name="iassemblycacheitem-interface"></a>Интерфейс IAssemblyCacheItem
Представляет отдельную сборку в глобальном кэше сборок.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод AbortItem](iassemblycacheitem-abortitem-method.md)|Позволяет сборке в глобальном кэше сборок выполнять операции очистки до ее освобождения.|  
|[Метод Commit](iassemblycacheitem-commit-method.md)|Фиксирует в памяти ссылку на кэшированную сборку.|  
|[Метод CreateStream](iassemblycacheitem-createstream-method.md)|Создает поток с указанными именем и форматом.|  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** Fusion. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы Fusion](fusion-interfaces.md)
- [Глобальный кэш сборок](../../app-domains/gac.md)
- [Интерфейс IAssemblyCache](iassemblycache-interface.md)
