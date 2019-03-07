---
title: Метод ICorDebugType::GetStaticFieldValue
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c6b86c5ce3cc246af600d9b65d2fe12a0427f9f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485399"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a>Метод ICorDebugType::GetStaticFieldValue
Получает указатель интерфейса на объект, содержащий значение статического поля, который ссылается указанное поле ICorDebugValue токена в указанном кадре стека.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `fieldDef`  
 [in] `mdFieldDef` Токен, который указывает статического поля.  
  
 `pFrame`  
 [in] Указатель на ICorDebugFrame, который представляет кадр стека.  
  
 `ppValue`  
 [out] Указатель на адрес `ICorDebugValue` , содержащий значение статического поля.  
  
## <a name="remarks"></a>Примечания  
 `GetStaticFieldValue` Метод может использоваться только в том случае, если тип является ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE, обозначенный [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) метод.  
  
 Для неуниверсальных типов, операция выполнена пользователем `GetStaticFieldValue` совпадает с вызовом метода [ICorDebugClass::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) ICorDebugClass объекта, возвращенного [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).  
  
 Для универсальных типов значение статического поля будет относительно определенного процесса создания экземпляров. Кроме того Если статическое поле может определяться относительно потока, контекста или домена приложения, кадр стека поможет определить значение отладчик.  
  
## <a name="remarks"></a>Примечания  
 `GetStaticFieldValue` может использоваться только при вызове `ICorDebugType::GetType` возвращает значение ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
