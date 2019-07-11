---
title: Метод ICorDebugILFrame2::EnumerateTypeParameters
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugILFrame2 interface [.NET Framework debugging]
- ICorDebugILFrame2::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 722d0d74-e0df-491f-98c4-62d501dfaf6f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2e53bfb46579cc51b7ad88ef7de2b9f8d2f9390
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758770"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a>Метод ICorDebugILFrame2::EnumerateTypeParameters
Возвращает объект, содержащий ICorDebugTypeEnum <xref:System.Type> параметры в этом кадре.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppTyParEnum`  
 Указатель на адрес объекта интерфейса ICorDebugTypeEnum, позволяющий перечисления параметров типа.  
  
 Список параметров типа включает параметры типа класса (если таковые имеются) следуют параметры типа метода (если таковые имеются).  
  
## <a name="remarks"></a>Примечания  
 Используйте [IMetaDataImport2::EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) метод, чтобы определить, сколько параметров типа класса и метода параметры, этот список содержит типа.  
  
 Параметры типа не всегда доступны.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
