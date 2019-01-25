---
title: Метод ICorDebugModule::GetName
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ae9bc5925634f8bba71731a0c51eb19cf9eec04
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663957"
---
# <a name="icordebugmodulegetname-method"></a>Метод ICorDebugModule::GetName
Возвращает имя файла модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `cchname`  
 [in] Размер массива `szName`.  
  
 `pcchName`  
 [in] Указатель на длину возвращаемого имени.  
  
 `szName`  
 [out] Массив, в котором хранится возвращаемое имя.  
  
## <a name="remarks"></a>Примечания  
 `GetName` Метод возвращает значение S_OK HRESULT, если имя файла модуля соответствует имени на диске. `GetName` Возвращает значение HRESULT S_FALSE, если оно создано, например, модуль динамический или в памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также


