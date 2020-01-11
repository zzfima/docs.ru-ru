---
title: Метод ICLRStrongName::StrongNameSignatureVerification
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerification
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerification method [.NET Framework hosting]
- StrongNameSignatureVerification method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 734dc4d1-0a76-4736-b5ac-cb4253b3dd49
topic_type:
- apiref
ms.openlocfilehash: 6375fd8e4a314403267a4cdf2e8356677e9e7a06
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899490"
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a>Метод ICLRStrongName::StrongNameSignatureVerification
Возвращает значение, указывающее, содержит ли манифест сборки по указанному пути подпись строгого имени, которая проверяется в соответствии с заданными флагами.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `wszFilePath`  
 окне Путь к переносимому исполняемому файлу (DLL или exe), для которого проверяется сборка.  
  
 `dwInFlags`  
 окне Флаги для изменения поведения проверки. Поддерживаются следующие значения.  
  
- `SN_INFLAG_FORCE_VER` (0x00000001) — принудительная проверка, даже если необходимо переопределить параметры реестра.  
  
- `SN_INFLAG_INSTALL` (0x00000002) — указывает, что это первый раз при проверке манифеста.  
  
- `SN_INFLAG_ADMIN_ACCESS` (0x00000004) — указывает, что кэш будет разрешать доступ только тем пользователям, у которых есть права администратора.  
  
- `SN_INFLAG_USER_ACCESS` (0x00000008) — указывает, что сборка будет доступна только текущему пользователю.  
  
- `SN_INFLAG_ALL_ACCESS` (0x00000010) — указывает, что кэш не предоставляет никаких гарантий ограничения доступа.  
  
- `SN_INFLAG_RUNTIME` (0x80000000) — зарезервировано для внутренней отладки.  
  
 `pdwOutFlags`  
 заполняет Флаги, указывающие, была ли проверена подпись строгого имени. Поддерживается следующее значение:  
  
- `SN_OUTFLAG_WAS_VERIFIED` (0x00000001) — это значение равно `false`, чтобы указать, что проверка прошла из-за параметров реестра.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Метод StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
