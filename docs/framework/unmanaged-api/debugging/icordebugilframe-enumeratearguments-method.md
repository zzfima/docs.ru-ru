---
title: Метод ICorDebugILFrame::EnumerateArguments
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateArguments
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49d7fb1de0b2ea63c1a766023b23acc42e027af8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995570"
---
# <a name="icordebugilframeenumeratearguments-method"></a>Метод ICorDebugILFrame::EnumerateArguments
Получает перечислитель для аргументов в кадре.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppValueEnum`  
 [out] Указатель на адрес объекта ICorDebugValueEnum, который является перечислителем для аргументов в кадре.  
  
## <a name="remarks"></a>Примечания  
 `EnumerateArguments` Возвращает перечислитель, который можно вывести список доступных в кадр вызова, который представлен этим объектом ICorDebugILFrame аргументов. В списке будут содержаться аргументы, которые являются [vararg](/cpp/windows/vararg) (то есть несколько переменных аргументов) а также аргументы, которые не являются `vararg`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
