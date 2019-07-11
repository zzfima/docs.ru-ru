---
title: Метод ICeeGen::GetSectionCreate
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionCreate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionCreate
helpviewer_keywords:
- ICeeGen::GetSectionCreate method [.NET Framework metadata]
- GetSectionCreate method [.NET Framework metadata]
ms.assetid: 154b2460-59ce-4874-a9f2-1b3353486ac5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3de3a9c152f3074339dba330b7827cf795a7e537
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745975"
---
# <a name="iceegengetsectioncreate-method"></a>Метод ICeeGen::GetSectionCreate
Создает и возвращает раздел кода, используя указанные имя и значения флагов.  
  
 Этот метод является устаревшим и не должны использоваться.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `name`  
 [in] Указатель на строку, которая указывает имя создаваемого раздела.  
  
 `flags`  
 [in] Флаги, определяющие параметры.  
  
 `section`  
 [out] Указатель на только что созданный код раздела.  
  
## <a name="remarks"></a>Примечания  
 Вызовите `GetSectionCreate` только при наличии особых требований к разделам, которые не обрабатываются другими способами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
