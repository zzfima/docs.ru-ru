---
title: Метод IAssemblyEnum::GetNextAssembly
ms.date: 03/30/2017
api_name:
- IAssemblyEnum.GetNextAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73c531378355100fdfca264ea9f96ff4d7c7ceda
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796687"
---
# <a name="iassemblyenumgetnextassembly-method"></a>Метод IAssemblyEnum::GetNextAssembly
Возвращает указатель на следующее значение [IAssemblyName](iassemblyname-interface.md) , содержащееся в этом объекте [IAssemblyEnum](iassemblyenum-interface.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pvReserved`  
 окне Зарезервировано для будущего расширения. `pvReserved`должен быть пустой ссылкой.  
  
 `ppName`  
 заполняет Возвращаемый `IAssemblyName` указатель.  
  
 `dwFlags`  
 окне Зарезервировано для будущего расширения. `dwFlags`значение должно быть равно 0 (нулю).  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** Fusion. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IAssemblyName](iassemblyname-interface.md)
- [Интерфейс IAssemblyEnum](iassemblyenum-interface.md)
