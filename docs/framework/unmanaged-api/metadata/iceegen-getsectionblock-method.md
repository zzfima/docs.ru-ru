---
title: Метод ICeeGen::GetSectionBlock
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionBlock
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 84ccbd7a8be7d90a541fb2d54baa3d7f66d3d31e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746114"
---
# <a name="iceegengetsectionblock-method"></a>Метод ICeeGen::GetSectionBlock
Получает блок разделе базы кода.  
  
 Этот метод является устаревшим и не должны использоваться.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,     
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);   
```  
  
## <a name="parameters"></a>Параметры  
 `section`  
 [in] Раздел, из которого извлекается блок кода.  
  
 `len`  
 [in] Длина блока, который требуется получить.  
  
 `align`  
 [in] Байт, относительно начала данного раздела, с которой необходимо выровнять первого байта блока. Это положение блока в разделе.  
  
 `ppBytes`  
 [out] Указатель на расположение, которое получает адрес извлеченных блока.  
  
## <a name="remarks"></a>Примечания  
 Вызовите `GetSectionBlock` только при наличии особых требований к разделам, которые не обрабатываются другими способами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
