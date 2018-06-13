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
ms.openlocfilehash: 0a0c23c066a6f704c4dfcfbe254e91ab3bc5817e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416245"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a>Метод ICorDebugILFrame2::EnumerateTypeParameters
Возвращает объект ICorDebugTypeEnum, содержащий <xref:System.Type> параметры в этом кадре.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppTyParEnum`  
 Указатель на адрес объекта интерфейса ICorDebugTypeEnum, который позволяет использовать параметры типа перечисления.  
  
 Список параметров типа включает параметры типа класса (если таковые имеются) следуют параметры типа метода (если таковые имеются).  
  
## <a name="remarks"></a>Примечания  
 Используйте [IMetaDataImport2::EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) метод, чтобы определить, сколько параметров типа класса и метод типов параметров, этот список содержит.  
  
 Параметры типа не всегда доступны.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
