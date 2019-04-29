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
ms.openlocfilehash: 58a39771bd89fc9c4947f80a3c87b4d340b5461c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934931"
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a>Метод ICorDebugAppDomain2::GetArrayOrPointerType
Получает массив указанного типа, указатель или ссылка на указанный тип.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `elementType`  
 [in] Значение CorElementType перечисления, указывающее базовый собственный тип (массив, указатель или ссылка) должен быть создан.  
  
 `nRank`  
 [in] Ранг (то есть число измерений) массива. Это значение должно быть 0, если `elementType` указывает тип указателя или ссылки.  
  
 `pTypeArg`  
 [in] Указатель на интерфейс ICorDebugType объект, представляющий тип массива, указателя или ссылки должен быть создан.  
  
 `ppType`  
 [out] Указатель на адрес `ICorDebugType` тип, представляющий сконструированный массива, тип указателя или ссылки.  
  
## <a name="remarks"></a>Примечания  
 Значение *elementType* должно быть одно из следующих:  
  
- ELEMENT_TYPE_PTR  
  
- ELEMENT_TYPE_BYREF  
  
- ELEMENT_TYPE_ARRAY или ELEMENT_TYPE_SZARRAY  
  
 Если значение *elementType* ELEMENT_TYPE_PTR или ELEMENT_TYPE_BYREF, *nRank* должно быть равно нулю.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
