---
title: Метод IAssemblyName::GetDisplayName
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetDisplayName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetDisplayName
helpviewer_keywords:
- GetDisplayName method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::GetDisplayName method [.NET Framework fusion]
ms.assetid: 9a26547a-9a34-4284-a463-78a7d4b496cf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38f48f2d95829d2c8111065e5f4ede4e43a16d63
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796661"
---
# <a name="iassemblynamegetdisplayname-method"></a>Метод IAssemblyName::GetDisplayName
Возвращает удобное для восприятия имя сборки, на которую ссылается этот объект [IAssemblyName](iassemblyname-interface.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `szDisplayName`  
 заполняет Строковый буфер, содержащий имя сборки, на которую указывает ссылка.  
  
 `pccDisplayName`  
 [вход, выход] Размер `szDisplayName` в расширенных символах, включая символ конца null.  
  
 `dwDisplayFlags`  
 окне Побитовое сочетание значений [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) , влияющих на функции `szDisplayName`.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** Fusion. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IAssemblyName](iassemblyname-interface.md)
- [Перечисления Fusion](fusion-enumerations.md)
