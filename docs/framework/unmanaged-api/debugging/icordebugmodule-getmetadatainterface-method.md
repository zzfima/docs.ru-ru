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
ms.openlocfilehash: fb96949e22b4edfc0e64780a54bb38da44eb8369
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129548"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a>Метод ICorDebugModule::GetMetaDataInterface
Возвращает объект интерфейса метаданных, который может использоваться для проверки метаданных модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `riid`  
 окне Идентификатор ссылки, указывающий интерфейс метаданных.  
  
 `ppObj`  
 заполняет Указатель на адрес объекта `T:IUnknown`, который является одним из [интерфейсов метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).  
  
## <a name="remarks"></a>Заметки  
 Отладчик может использовать метод `GetMetaDataInterface`, чтобы создать копию исходных метаданных для модуля, который необходимо сделать для изменения этого модуля. Отладчик вызывает `GetMetaDataInterface`, чтобы получить объект интерфейса [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) для модуля, а затем вызывает метод [IMetaDataEmit:: саветомемори](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) , чтобы сохранить копию метаданных модуля в памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метаданные](../../../../docs/framework/unmanaged-api/metadata/index.md)
