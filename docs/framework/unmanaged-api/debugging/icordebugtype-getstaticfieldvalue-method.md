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
ms.openlocfilehash: 2b136f30b0c1ce9f83228f340ac5e147cc02002b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a>Метод ICorDebugType::GetStaticFieldValue
Получает указатель интерфейса на объект ICorDebugValue, содержащий значение статического поля, который ссылается указанное поле токена в указанном кадре стека.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `fieldDef`  
 [in] `mdFieldDef` Маркер, который указывает статического поля.  
  
 `pFrame`  
 [in] Указатель ICorDebugFrame, который представляет кадр стека.  
  
 `ppValue`  
 [out] Указатель на адрес `ICorDebugValue` , содержащий значение статического поля.  
  
## <a name="remarks"></a>Примечания  
 `GetStaticFieldValue` Метод может использоваться только в том случае, если тип является ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE, как указано в [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) метод.  
  
 Для типов неуниверсальных выполнить операцию по `GetStaticFieldValue` совпадает с вызовом метода [ICorDebugClass::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) ICorDebugClass объекта, который возвращается методом [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).  
  
 Для универсальных типов значение статического поля будет относительно определенного процесса создания экземпляров. Кроме того Если статическое поле может определяться относительно потока, контекста или домена приложения, кадр стека помогает отладчику определить правильное значение.  
  
## <a name="remarks"></a>Примечания  
 `GetStaticFieldValue` можно использовать только при вызове `ICorDebugType::GetType` возвращает значение ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
