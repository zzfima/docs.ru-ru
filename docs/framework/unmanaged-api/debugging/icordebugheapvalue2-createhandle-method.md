---
title: Метод ICorDebugHeapValue2::CreateHandle
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2.CreateHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type:
- apiref
ms.openlocfilehash: c7a1bf3cb10cbc8cdae2788b45e1badaf66a9dbd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178879"
---
# <a name="icordebugheapvalue2createhandle-method"></a>Метод ICorDebugHeapValue2::CreateHandle
Создает ручку указанного типа для значения кучи, представленного этим объектом ICorDebugHeapValue2.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `type`  
 (в) Значение перечисления CorDebugHandleType, которое определяет тип создаваемых рукояток.  
  
 `ppHandle`  
 (ваут) Указатель на адрес объекта ICorDebugHandleValue, который представляет новую ручку для этого значения кучи.  
  
## <a name="remarks"></a>Remarks  
 Ручка будет создана в домене приложения, связанном со значением кучи, и станет недействительной, если домен приложения будет разгружен.  
  
 Несколько вызовов к этой функции для одного и того же значения кучи создаст несколько рукояток. Поскольку ручки влияют на производительность сборщика мусора, отладчик должен ограничиваться относительно небольшим числом ручек (около 256), которые активны одновременно.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
