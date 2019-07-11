---
title: Метод ICorDebugModule::GetMetaDataInterface
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetMetaDataInterface
helpviewer_keywords:
- ICorDebugModule::GetMetaDatainterface method [.NET Framework debugging]
- GetMetaDatainterface method [.NET Framework debugging]
ms.assetid: 30d906f2-cf35-4fa9-9d4c-0c31b58c9f3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 398c48bfd30020efdb57861991c9541d412d3e0d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763436"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a>Метод ICorDebugModule::GetMetaDataInterface
Получает объект интерфейс метаданных, который может использоваться для просмотра метаданных для модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `riid`  
 [in] Идентификатор ссылки, указывающий интерфейс метаданных.  
  
 `ppObj`  
 [out] Указатель на адрес `T:IUnknown` объект, который является одним из [интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).  
  
## <a name="remarks"></a>Примечания  
 Можно использовать отладчик `GetMetaDataInterface` метод для создания копии исходных метаданных для модуля, которая необходима для редактирования этого модуля. Отладчик вызывает `GetMetaDataInterface` для получения [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) объект интерфейса для модуля, затем вызывает [IMetaDataEmit::SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) для сохранения копии метаданных модуля памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метаданные](../../../../docs/framework/unmanaged-api/metadata/index.md)
