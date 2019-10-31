---
title: Метод ICLRStrongName::StrongNameCompareAssemblies
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type:
- apiref
ms.openlocfilehash: fdca03b781e07b709cbc54e673dbaa2a1130fbe3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135149"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a>Метод ICLRStrongName::StrongNameCompareAssemblies
Определяет, отличаются ли две сборки только подписями строгого имени.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `wszAssembly1`  
 окне Путь к первой сборке.  
  
 `wszAssembly2`  
 окне Путь к второй сборке.  
  
 `pdwResult`  
 заполняет Одно из следующих значений:  
  
- `SN_CMP_DIFFERENT` (0) — указывает, что сборки содержат различные данные.  
  
- `SN_CMP_IDENTICAL` (1) — указывает, что сборки точно одинаковы, включая их подписи и контрольные суммы.  
  
- `SN_CMP_SIGONLY` (2) — указывает, что сборки отличаются только сигнатурой и контрольной суммой.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) для списка).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="remarks"></a>Заметки  
 Подпись строгого имени сборки состоит из текстового имени, версии, языка и региональных параметров сборки, а также токена открытого ключа.  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
