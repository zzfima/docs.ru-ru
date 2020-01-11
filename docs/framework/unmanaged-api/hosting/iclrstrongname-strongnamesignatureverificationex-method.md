---
title: Метод ICLRStrongName::StrongNameSignatureVerificationEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureVerificationEx method [.NET Framework hosting]
ms.assetid: dbd2f662-208b-4174-b301-5c99af91040f
topic_type:
- apiref
ms.openlocfilehash: fbc9ea6aab9f0c3d9be95e6affcd04342ce4c5cc
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901078"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a>Метод ICLRStrongName::StrongNameSignatureVerificationEx
Возвращает значение, указывающее, содержит ли манифест сборки по указанному пути подпись строгого имени.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `wszFilePath`  
 окне Путь к переносимому исполняемому файлу (exe или DLL) для проверяемой сборки.  
  
 `fForceVerification`  
 [in] `true` выполнить проверку, даже если необходимо переопределить параметры реестра; в противном случае `false`.  
  
 `pfWasVerified`  
 [out] `true`, если подпись строгого имени была проверена; в противном случае `false`. `pfWasVerified` также имеет значение `false`, если проверка прошла успешно из-за параметров реестра.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`, если проверка прошла успешно; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).  
  
## <a name="remarks"></a>Заметки  
 Метод [метод iclrstrongname:: StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) предоставляет такую возможность, как метод [метод iclrstrongname:: StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) . Однако второй входной параметр и выходной параметр для [метод iclrstrongname:: StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) относятся к типу `BOOLEAN` вместо `DWORD`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Метод StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
