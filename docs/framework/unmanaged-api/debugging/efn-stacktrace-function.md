---
title: "Функция _EFN_StackTrace"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _EFN_StackTrace
api_location: mscordbi.dll
api_type: COM
f1_keywords: _EFN_StackTrace
helpviewer_keywords: _EFN_StackTrace function [.NET Framework debugging]
ms.assetid: caea7754-867c-4360-a65c-5ced4408fd9d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 905a44ee3187bc920d9342b043383a1500c28985
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="efnstacktrace-function"></a>Функция _EFN_StackTrace
Предоставляет текстовое представление трассировки управляемого стека и массив записей `CONTEXT`, по одной для каждого перехода между неуправляемым и управляемым кодом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
#### <a name="parameters"></a>Параметры  
 `Client`  
 [in] Клиент которого выполняется отладка.  
  
 `wszTextOut`  
 [out] Текстовое представление трассировки стека.  
  
 `puiTextLength`  
 [out] Указатель на число символов в `wszTextOut`.  
  
 `pTransitionContexts`  
 [out] Массив контексты перехода.  
  
 `puiTransitionContextCount`  
 [out] Указатель на число контекстов перехода в массиве.  
  
 `uiSizeOfContext`  
 [in] Размер структуры контекста.  
  
 `Flags`  
 [in] Значение 0 или SOS_STACKTRACE_SHOWADDRESSES (0x01) для отображения регистр EBP и указатель стека ввод (ESP) перед каждой `module!functionname` строки.  
  
## <a name="remarks"></a>Примечания  
 `_EFN_StackTrace` Структуру может вызываться из программный интерфейс WinDbg. Параметры используются следующим образом:  
  
-   Если `wszTextOut` имеет значение null и `puiTextLength` — не null, функция возвращает длину строки в `puiTextLength`.  
  
-   Если `wszTextOut` — не null, функция сохраняет текст в `wszTextOut` до местоположения, указанного параметром `puiTextLength`. Он возвращает успешно, если было достаточно места в буфере или возвращает значение E_OUTOFMEMORY, если буфер недостаточно длинный.  
  
-   Переход части функции учитывается, если `pTransitionContexts` и `puiTransitionContextCount` оба имеют значение null. В этом случае функция предоставляет вызывающим объектам с помощью текстовых выходных данных только имена функций.  
  
-   Если `pTransitionContexts` имеет значение null и `puiTransitionContextCount` — не null, функция возвращает необходимое количество записей контекста в `puiTransitionContextCount`.  
  
-   Если `pTransitionContexts` — не null, функция воспринимает его как массив структур длины `puiTransitionContextCount`. Размер структуры определяется `uiSizeOfContext`, и должен быть размер [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) или `CONTEXT` для архитектуры.  
  
-   `wszTextOut`записывается в следующем формате:  
  
    ```  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
-   Если в шестнадцатеричном формате смещение равно 0x0, смещения не записывается.  
  
-   Если нет управляемого кода в потоке в данный момент в контексте, функция возвращает значение SOS_E_NOMANAGEDCODE.  
  
-   `Flags` Параметр имеет значение 0 или SOS_STACKTRACE_SHOWADDRESSES для просмотра EBP и ESP перед каждой `module!functionname` строки. По умолчанию — 0.  
  
    ```  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** SOS_Stacktrace.h  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Глобальные статические функции отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
