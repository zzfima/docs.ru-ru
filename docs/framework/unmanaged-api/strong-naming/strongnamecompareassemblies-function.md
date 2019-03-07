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
ms.openlocfilehash: dd3813d977f94db4168da8c888485b323f4072ad
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471281"
---
# <a name="strongnamecompareassemblies-function"></a>Функция StrongNameCompareAssemblies
Определяет, отличаются ли две сборки только подписями строгого имени.  
  
 Эта функция является устаревшей. Используйте [ICLRStrongName::StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) метод вместо этого.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
-   `SN_CMP_DIFFERENT` (0) — указывает, что сборки содержат разные данные.  
  
-   `SN_CMP_IDENTICAL` (1) — указывает, что сборки идентичны, включая их подписи и контрольной суммы.  
  
-   `SN_CMP_SIGONLY` (2) — указывает, что сборки отличаются только подпись и контрольная сумма.  
  
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
