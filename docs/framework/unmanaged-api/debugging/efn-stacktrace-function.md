---
title: Функция _EFN_StackTrace
ms.date: 03/30/2017
api_name:
- _EFN_StackTrace
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_StackTrace
helpviewer_keywords:
- _EFN_StackTrace function [.NET Framework debugging]
ms.assetid: caea7754-867c-4360-a65c-5ced4408fd9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9035d9a53c4b0c8822b79e641aef092b4a48c418
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895044"
---
# <a name="_efn_stacktrace-function"></a>\_ЕФН\_StackTrace, функция
Предоставляет текстовое представление трассировки управляемого стека и массив записей `CONTEXT`, по одной для каждого перехода между неуправляемым и управляемым кодом.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CALLBACK _EFN_StackTrace(  
    [in]  PDEBUG_CLIENT  Client,  
    [out] WCHAR          wszTextOut[],  
    [out] size_t         *puiTextLength,  
    [out] LPVOID         pTransitionContexts,  
    [out] size_t         *puiTransitionContextCount,  
    [in]  size_t         uiSizeOfContext,  
    [in]  DWORD          Flags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `Client`  
 окне Отлаживаемый клиент.  
  
 `wszTextOut`  
 заполняет Текстовое представление трассировки стека.  
  
 `puiTextLength`  
 заполняет Указатель на число символов в `wszTextOut`.  
  
 `pTransitionContexts`  
 заполняет Массив контекстов перехода.  
  
 `puiTransitionContextCount`  
 заполняет Указатель на число контекстов перехода в массиве.  
  
 `uiSizeOfContext`  
 окне Размер структуры контекста.  
  
 `Flags`  
 окне Задайте значение 0 или SOS_STACKTRACE_SHOWADDRESSES (0x01), чтобы отобразить регистр ebp и указатель ввода стека (ESP) перед каждой `module!functionname` строкой.  
  
## <a name="remarks"></a>Примечания  
 `_EFN_StackTrace` Структуру можно вызвать из программного интерфейса WinDbg. Параметры используются следующим образом.  
  
- Если `wszTextOut` значение равно NULL `puiTextLength` и не равно null, функция возвращает длину строки в `puiTextLength`.  
  
- Если `wszTextOut` параметр не равен null, функция сохраняет текст в `wszTextOut` расположении, указанном параметром `puiTextLength`. Он возвращает значение, если в буфере достаточно места, или значение E_OUTOFMEMORY, если буфер недостаточно длинный.  
  
- Часть перехода функции игнорируется, если `pTransitionContexts` и `puiTransitionContextCount` равны NULL. В этом случае функция предоставляет вызывающим объектам текстовые выходные данные только имен функций.  
  
- Если `pTransitionContexts` параметр имеет значение `puiTransitionContextCount` NULL и не равен null, функция возвращает необходимое число контекстных записей в `puiTransitionContextCount`.  
  
- Если `pTransitionContexts` параметр не равен null, функция обрабатывает ее как массив структур с длиной `puiTransitionContextCount`. Размер структуры определяется параметром `uiSizeOfContext`и должен быть размером [симплеконтекст](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) или `CONTEXT` для архитектуры.  
  
- `wszTextOut`записывается в следующем формате:  
  
    ```output  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- Если смещение в шестнадцатеричном формате имеет значение 0x0, смещение не записывается.  
  
- Если в текущем потоке нет управляемого кода, функция возвращает SOS_E_NOMANAGEDCODE.  
  
- Параметр имеет значение 0 или SOS_STACKTRACE_SHOWADDRESSES, чтобы видеть ebp и ESP в начале каждой `module!functionname` строки. `Flags` По умолчанию это 0.  
  
    ```cpp  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** SOS_Stacktrace. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
