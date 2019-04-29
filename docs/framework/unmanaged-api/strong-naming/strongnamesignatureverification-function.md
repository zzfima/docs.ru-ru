---
title: Функция StrongNameSignatureVerification
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerification
helpviewer_keywords:
- StrongNameSignatureVerification function [.NET Framework strong naming]
ms.assetid: 933758dd-231e-4382-8819-242c0a13a4b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c398663b84637d2551b0d94bd59b9e0994721ba5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792630"
---
# <a name="strongnamesignatureverification-function"></a>Функция StrongNameSignatureVerification
Получает значение, указывающее, содержит ли находящийся по указанному пути манифест сборки подпись строгого имени, которая проверяется в соответствии с заданными флагами.  
  
 Эта функция является устаревшей. Используйте [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) метод вместо этого.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `wszFilePath`  
 [in] Путь к переносимого исполняемого файла (.dll или .exe) для сборки для проверки.  
  
 `dwInFlags`  
 [in] Флаги для изменения поведения проверки. Поддерживаются следующие значения:  
  
- `SN_INFLAG_FORCE_VER` (0x00000001) — проверка производится, даже если это необходимо переопределить параметры реестра.  
  
- `SN_INFLAG_INSTALL` (0x00000002) — указывает, что это в первый раз, проверка манифеста.  
  
- `SN_INFLAG_ADMIN_ACCESS` (0x00000004) — указывает, что кэш будет предоставлять доступ только к пользователям, имеющим права администратора.  
  
- `SN_INFLAG_USER_ACCESS` (0x00000008) — указывает, что сборка будет доступен только для текущего пользователя.  
  
- `SN_INFLAG_ALL_ACCESS` (0x00000010) — указывает, что кэш будет предоставлять никаких гарантий, ограничения доступа.  
  
- `SN_INFLAG_RUNTIME` (0x80000000) — зарезервировано для внутренней отладки.  
  
 `pdwOutFlags`  
 [out] Флаги, указывающие, был ли проверен подписи строгого имени. Поддерживается следующее значение:  
  
- `SN_OUTFLAG_WAS_VERIFIED` (0x00000001) — это значение присваивается `false` для указания, что проверка выполнена успешно из-за параметров реестра.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true` Если проверка прошла успешно; в противном случае `false`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** StrongName.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [Метод StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
