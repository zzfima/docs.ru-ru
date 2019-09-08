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
ms.openlocfilehash: 8943df861b1bff2b28c68d0233fc336d1b5d4579
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798946"
---
# <a name="strongnamesignatureverification-function"></a>Функция StrongNameSignatureVerification
Получает значение, указывающее, содержит ли находящийся по указанному пути манифест сборки подпись строгого имени, которая проверяется в соответствии с заданными флагами.  
  
 Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `wszFilePath`  
 окне Путь к переносимому исполняемому файлу (DLL или exe), для которого проверяется сборка.  
  
 `dwInFlags`  
 окне Флаги для изменения поведения проверки. Поддерживаются следующие значения:  
  
- `SN_INFLAG_FORCE_VER`(0x00000001) — принудительная проверка, даже если необходимо переопределить параметры реестра.  
  
- `SN_INFLAG_INSTALL`(0x00000002) — указывает, что это первый раз при проверке манифеста.  
  
- `SN_INFLAG_ADMIN_ACCESS`(0x00000004) — указывает, что кэш будет разрешать доступ только тем пользователям, у которых есть права администратора.  
  
- `SN_INFLAG_USER_ACCESS`(0x00000008) — указывает, что сборка будет доступна только текущему пользователю.  
  
- `SN_INFLAG_ALL_ACCESS`(0x00000010) — указывает, что кэш не предоставляет никаких гарантий ограничения доступа.  
  
- `SN_INFLAG_RUNTIME`(0x80000000) — зарезервировано для внутренней отладки.  
  
 `pdwOutFlags`  
 заполняет Флаги, указывающие, была ли проверена подпись строгого имени. Поддерживается следующее значение:  
  
- `SN_OUTFLAG_WAS_VERIFIED`(0x00000001) — это значение `false` указывает, что проверка прошла удачно из-за параметров реестра.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`значение, если проверка прошла успешно; в противном случае —. `false`  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** StrongName. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [Метод StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
