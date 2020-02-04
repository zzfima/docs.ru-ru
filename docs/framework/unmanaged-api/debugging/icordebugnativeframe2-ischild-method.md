---
title: Метод ICorDebugNativeFrame2::IsChild
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.IsChild Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsChild
helpviewer_keywords:
- IsChild method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsChild method [.NET Framework debugging]
ms.assetid: 9e2aae09-49cb-4fbd-81e5-e29cd864a88b
topic_type:
- apiref
ms.openlocfilehash: 22722e4d602bdb9df9877b2199b4d4271a4d3105
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792722"
---
# <a name="icordebugnativeframe2ischild-method"></a>Метод ICorDebugNativeFrame2::IsChild
Определяет, является ли текущий кадр дочерним кадром.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
## <a name="parameters"></a>Параметры  
 `pIsChild`  
 заполняет Логическое значение, указывающее, является ли текущий кадр дочерним кадром.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Состояние дочернего элемента успешно возвращено.|  
|E_FAIL|Не удалось вернуть состояние дочернего элемента.|  
|E_INVALIDARG|Параметр `pIsChild` имеет значение NULL.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Заметки  
 Метод `IsChild` возвращает `true`, если объект Frame, для которого вызывается метод, является дочерним для другого кадра. В этом случае используйте метод [IsMatchingParentFrame](icordebugnativeframe2-ismatchingparentframe-method.md) , чтобы проверить, является ли кадр родительским.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
