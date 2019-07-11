---
title: Функция LoadStringRC
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9047bf973224cdbc1f67463ef70f15f81089f827
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768468"
---
# <a name="loadstringrc-function"></a>Функция LoadStringRC
Преобразовывает значение HRESULT в сообщение об ошибке с помощью языка и региональных параметров по умолчанию текущего потока.  
  
 Эта функция является устаревшим в .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `iResourceID`  
 [in] Значение HRESULT.  
  
 `szBuffer`  
 [out] Буфер, который содержит сообщение об ошибке после успешного завершения.  
  
 `iMax`  
 [in] Размер буфера сообщений ошибок.  
  
 `bQuiet`  
 [in] Игнорируется.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок объектов модели компонентов (COM), как определено в файле WinError.h, помимо следующих значений.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_INVALIDARG|`szBuffer` имеет значение null или `iMax` равно нулю (0).|  
  
## <a name="remarks"></a>Примечания  
 Если метод завершается успешно, `szBuffer` содержит пустую строку.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Библиотек MSCorEE.dll и Mscorwks.dll. Используйте библиотеку MSCorEE.dll вместо "Mscorwks.dll", чтобы обеспечить целевых правильную версию платформы .NET Framework.  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция LoadStringRCEx](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
