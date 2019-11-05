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
ms.openlocfilehash: 2493b5338824e1eab3f82a9023bbcced59a98fc8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134465"
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
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы Fusion](fusion-interfaces.md)
- [Глобальный кэш сборок](../../app-domains/gac.md)
- [Интерфейс IAssemblyCache](iassemblycache-interface.md)
