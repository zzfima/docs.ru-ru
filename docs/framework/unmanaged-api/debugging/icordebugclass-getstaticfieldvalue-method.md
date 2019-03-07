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
ms.openlocfilehash: 6b67f5ec233679461f61715d7562b47c2a195fb8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471632"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a>Метод ICorDebugClass::GetStaticFieldValue
Получает значение указанного статического поля.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
