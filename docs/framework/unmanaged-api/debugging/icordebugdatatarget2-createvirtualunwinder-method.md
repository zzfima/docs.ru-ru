---
title: Метод ICorDebugDataTarget2::CreateVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92dd0a4ad8128f7ce300ca5da1e5022b944d91e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417645"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a>Метод ICorDebugDataTarget2::CreateVirtualUnwinder
Создает новый элемент очистки стека, запускающий операцию очистки, начиная с исходного контекста (который не обязательно является концом потока).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
#### <a name="parameters"></a>Параметры  
 nativeThreadID  
 [входной] Идентификатор собственного потока, стек которого должен быть очищен.  
  
 contextFlags  
 [входной] Флаги, указывающие, какие части контекста определены в `initialContext`.  
  
 cbContext  
 [входной] Размер `initialContext`.  
  
 initialContext  
 [входной] Данные в контексте.  
  
 ppUnwinder  
 [выходной] Указатель на адрес объекта интерфейса ICorDebugVirtualUnwinder.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK` в случае успешного выполнения. Любое другое значение `HRESULT` указывает на ошибку. Любое ошибочное `HRESULT` полученное процессом mscordbi считается неустранимым и приводит [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) методы для возврата `CORDBG_E_DATA_TARGET_ERROR`.  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugDataTarget2](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
