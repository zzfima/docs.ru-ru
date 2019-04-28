---
title: Метод ICeeGen::GetSectionDataLen
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionDataLen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionDataLen
helpviewer_keywords:
- ICeeGen::GetSectionDataLen method [.NET Framework metadata]
- GetSectionDataLen method [.NET Framework metadata]
ms.assetid: e2a06ee4-b8ee-49c7-935a-c1031a29eef2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ca01f78cf46d4f7543b949c820eb6b1971687e23
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905480"
---
# <a name="iceegengetsectiondatalen-method"></a>Метод ICeeGen::GetSectionDataLen
Получает длину указанного раздела.  
  
 Этот метод является устаревшим и не должны использоваться.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `section`  
 [in] Раздел данных, длина которого будут извлекаться.  
  
 `dataLen`  
 [out] Возвращаемая длина указанного раздела.  
  
## <a name="remarks"></a>Примечания  
 Вызовите `GetSectionDataLen` только при наличии особых требований к разделам, которые не обрабатываются другими способами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
