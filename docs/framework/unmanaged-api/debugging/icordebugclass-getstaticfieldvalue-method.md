---
title: Метод ICorDebugClass::GetStaticFieldValue
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 56e718b4-fabd-418b-a5b3-3cc33c745683
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7649d91ca2b654952d1d5ab0d45f7903d3c46a32
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745542"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a>Метод ICorDebugClass::GetStaticFieldValue
Получает значение указанного статического поля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `fieldDef`  
 [in] Поле `Def` маркер, который ссылается на поля для извлечения.  
  
 `pFrame`  
 [in] Указатель на интерфейс ICorDebugFrame объект, представляющий кадр и использоваться для однозначного определения потока, контекста или статических элементов домена приложения.  
  
 Если поле является статическим относительно потока, контекста или домена приложения, кадр определит соответствующее значение.  
  
 `ppValue`  
 [out] Указатель на адрес ICorDebugValue объект, представляющий значение статического поля.  
  
## <a name="remarks"></a>Примечания  
 Для параметризованных типов значение статического поля задается относительно определенного процесса создания экземпляров. Таким образом Если конструктор классов принимает параметры типа <xref:System.Type>, вызовите [ICorDebugType::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) вместо `ICorDebugClass::GetStaticFieldValue`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
