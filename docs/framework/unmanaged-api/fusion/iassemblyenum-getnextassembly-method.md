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
ms.openlocfilehash: ade404557d65fa073b6a0e66fe8234b41223ecde
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134440"
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
 окне Зарезервировано для будущего расширения. `pvReserved` должен быть пустой ссылкой.  
  
 `ppName`  
 заполняет Возвращаемый указатель `IAssemblyName`.  
  
 `dwFlags`  
 окне Зарезервировано для будущего расширения. значение `dwFlags` должно быть равно 0 (нулю).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IAssemblyName](iassemblyname-interface.md)
- [Интерфейс IAssemblyEnum](iassemblyenum-interface.md)
