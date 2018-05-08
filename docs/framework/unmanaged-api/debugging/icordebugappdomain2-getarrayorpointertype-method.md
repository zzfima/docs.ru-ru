---
title: Метод ICorDebugAppDomain2::GetArrayOrPointerType
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetArrayOrPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetArrayOrPointerType
helpviewer_keywords:
- GetArrayOrPointerType method [.NET Framework debugging]
- ICorDebugAppDomain2::GetArrayOrPointerType method [.NET Framework debugging]
ms.assetid: 97e493f5-3a62-4ec7-b42f-4af57bf71f57
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb3f0ca6d930b22f30fe9bbc5b5a04bf1e034f34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a>Метод ICorDebugAppDomain2::GetArrayOrPointerType
Возвращает массив указанного типа, указатель или ссылку на указанный тип.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `elementType`  
 [in] Значение CorElementType перечисление, указывающее базовый собственный тип (массив, указатель или ссылка) должен быть создан.  
  
 `nRank`  
 [in] Ранг (то есть число измерений) массива. Это значение должно быть 0, если `elementType` указывает тип указателя или ссылки.  
  
 `pTypeArg`  
 [in] Указатель на объект ICorDebugType, представляющий тип массива, указателя или ссылки должен быть создан.  
  
 `ppType`  
 [out] Указатель на адрес `ICorDebugType` тип, представляющий сконструированный массива, тип указателя или ссылки.  
  
## <a name="remarks"></a>Примечания  
 Значение *elementType* должен быть одним из следующих:  
  
-   ELEMENT_TYPE_PTR  
  
-   ELEMENT_TYPE_BYREF  
  
-   ELEMENT_TYPE_ARRAY или ELEMENT_TYPE_SZARRAY  
  
 Если значение *elementType* ELEMENT_TYPE_PTR или ELEMENT_TYPE_BYREF, *nRank* должен быть равен нулю.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
