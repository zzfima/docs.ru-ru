---
title: Функция CreateAssemblyCache
ms.date: 03/30/2017
api_name:
- CreateAssemblyCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyCache
helpviewer_keywords:
- CreateAssemblyCache function [.NET Framework fusion]
ms.assetid: 348c7c8c-8578-46ae-97cf-480d6015c3c6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf78ded62f11b336d9f5fe0f3a205275ae37189b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669992"
---
# <a name="createassemblycache-function"></a>Функция CreateAssemblyCache
Возвращает указатель на новый [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) экземпляр, представляющий глобальный кэш сборок.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a>Параметры  
 `ppAsmCache`  
 [out] Возвращенный `IAssemblyCache` указатель.  
  
 `dwReserved`  
 [in] Зарезервировано для будущего расширения. `dwReserved` должно быть 0 (ноль).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Fusion.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [Глобальные статические функции Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [Глобальный кэш сборок](../../../../docs/framework/app-domains/gac.md)
