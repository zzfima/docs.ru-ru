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
ms.openlocfilehash: cc5093a5ba0afcccaf960e9b8776f93a061cc2f5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785668"
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
 окне Задайте значение 0 или SOS_STACKTRACE_SHOWADDRESSES (0x01) для отображения регистра EBP и указателя ввода стека (ESP) перед каждой строкой `module!functionname`.  
  
## <a name="remarks"></a>Заметки  
 Структура `_EFN_StackTrace` может быть вызвана из программного интерфейса WinDbg. Параметры используются следующим образом.  
  
- Если `wszTextOut` имеет значение NULL и `puiTextLength` не равно null, функция возвращает длину строки в `puiTextLength`.  
  
- Если `wszTextOut` не равно null, функция сохраняет текст в `wszTextOut` вплоть до расположения, указанного в `puiTextLength`. Он возвращает значение, если в буфере достаточно места, или возвращает E_OUTOFMEMORY, если буфер недостаточно длинный.  
  
- Переходная часть функции пропускается, если `pTransitionContexts` и `puiTransitionContextCount` равны NULL. В этом случае функция предоставляет вызывающим объектам текстовые выходные данные только имен функций.  
  
- Если `pTransitionContexts` имеет значение NULL и `puiTransitionContextCount` не равно null, функция возвращает необходимое число контекстных записей в `puiTransitionContextCount`.  
  
- Если `pTransitionContexts` не равно null, функция обрабатывает ее как массив структур `puiTransitionContextCount`длины. Размер структуры задается `uiSizeOfContext`и должен быть размером [симплеконтекст](stacktrace-simplecontext-structure.md) или `CONTEXT` для архитектуры.  
  
- `wszTextOut` записывается в следующем формате:  
  
    ```output  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- Если смещение в шестнадцатеричном формате имеет значение 0x0, смещение не записывается.  
  
- Если в текущем потоке нет управляемого кода, функция возвращает SOS_E_NOMANAGEDCODE.  
  
- Параметр `Flags` имеет значение 0 или SOS_STACKTRACE_SHOWADDRESSES, чтобы видеть EBP и ESP перед каждой строкой `module!functionname`. По умолчанию это 0.  
  
    ```cpp  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** SOS_Stacktrace. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Глобальные статические функции отладки](debugging-global-static-functions.md)
