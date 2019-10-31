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
ms.openlocfilehash: 166f6bb50849df8550871958d7034fdf2a841abb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73089114"
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a>Метод ICorDebugAppDomain2::GetArrayOrPointerType
Возвращает массив указанного типа или указатель или ссылку на указанный тип.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `elementType`  
 окне Значение перечисления Корелементтипе, которое указывает базовый собственный тип (массив, указатель или ссылка), который необходимо создать.  
  
 `nRank`  
 окне Ранг (то есть количество измерений) массива. Это значение должно быть равно 0, если `elementType` задает указатель или ссылочный тип.  
  
 `pTypeArg`  
 окне Указатель на объект ICorDebugType, представляющий тип создаваемого массива, указателя или ссылки.  
  
 `ppType`  
 заполняет Указатель на адрес объекта `ICorDebugType`, представляющего сконструированный массив, тип указателя или ссылочный тип.  
  
## <a name="remarks"></a>Заметки  
 Значение *ElementType* должно быть одним из следующих:  
  
- ELEMENT_TYPE_PTR  
  
- ELEMENT_TYPE_BYREF  
  
- ELEMENT_TYPE_ARRAY или ELEMENT_TYPE_SZARRAY  
  
 Если значение *ElementType* — ELEMENT_TYPE_PTR или ELEMENT_TYPE_BYREF, *нранк* должно быть равно нулю.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
