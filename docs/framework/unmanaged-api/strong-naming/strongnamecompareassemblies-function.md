---
title: Функция StrongNameCompareAssemblies
ms.date: 03/30/2017
api_name:
- StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameCompareAssemblies
helpviewer_keywords:
- StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3693a42db8e32a4bb7a399f8c930da011130893
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778734"
---
# <a name="strongnamecompareassemblies-function"></a>Функция StrongNameCompareAssemblies
Определяет, отличаются ли две сборки только подписями строгого имени.  
  
 Эта функция является устаревшей. Используйте [ICLRStrongName::StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) метод вместо этого.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `wszAssembly1`  
 [in] Путь к первой сборки.  
  
 `wszAssembly2`  
 [in] Путь к вторую сборку.  
  
 `pdwResult`  
 [out] Одно из следующих значений:  
  
- `SN_CMP_DIFFERENT` (0) — указывает, что сборки содержат разные данные.  
  
- `SN_CMP_IDENTICAL` (1) — указывает, что сборки идентичны, включая их подписи и контрольной суммы.  
  
- `SN_CMP_SIGONLY` (2) — указывает, что сборки отличаются только подпись и контрольная сумма.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true` После успешного выполнения; в противном случае `false`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** StrongName.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="remarks"></a>Примечания  
 Подпись строгого имени сборки состоит из текстовое имя сборки, версию, язык и региональные параметры и маркер открытого ключа.  
  
 Если `StrongNameCompareAssemblies` функция не завершена, вызвать [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.  
  
## <a name="see-also"></a>См. также

- [Метод StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
