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
ms.openlocfilehash: c855d6f85c3cbfa6d81a1fbce3ef5b83abb3f583
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795405"
---
# <a name="createassemblycache-function"></a>Функция CreateAssemblyCache
Возвращает указатель на новый экземпляр [IAssemblyCache](iassemblycache-interface.md) , представляющий глобальный кэш сборок.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a>Параметры  
 `ppAsmCache`  
 заполняет Возвращаемый `IAssemblyCache` указатель.  
  
 `dwReserved`  
 окне Зарезервировано для будущего расширения. `dwReserved`значение должно быть равно 0 (нулю).  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** Fusion. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IAssemblyCache](iassemblycache-interface.md)
- [Глобальные статические функции Fusion](fusion-global-static-functions.md)
- [Глобальный кэш сборок](../../app-domains/gac.md)
