---
title: Функция _CorDllMain
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
ms.openlocfilehash: f60f159ab4770023cee7123b39109040243e1ccd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136965"
---
# <a name="_cordllmain-function"></a>\_функция Кордллмаин

Инициализирует среду CLR, находит управляемую точку входа в заголовке CLR сборки DLL и начинает выполнение.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `hInst`  
 окне Экземпляр загруженного модуля.  
  
 `dwReason`  
 окне Указывает, почему вызывается функция точки входа DLL. Этот параметр может принимать одно из следующих значений: DLL\_PROCESS_ATTACH, DLL\_потока\_ATTACH, DLL\_потока\_ATTACH или DLL\_процесса\_DETACH. Описание этих значений см. в документации по `DllMain` в пакете Platform SDK.  
  
 `lpReserved`  
 окне Использующ.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает `true` для успешного выполнения и `false` при возникновении ошибки.  
  
## <a name="remarks"></a>Заметки  
 Эта функция вызывается загрузчиком операционной системы для сборок DLL. Для исполняемых сборок загрузчик вызывает функцию [\_корексемаин](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) .  
  
 Загрузчик операционной системы вызывает этот метод независимо от точки входа, указанной в файле DLL.  
  
Функция `_CorDllMain` вызывается непосредственно загрузчиком операционной системы.
  
 Дополнительные сведения см. в подразделе "Примечания" статьи [\_корвалидатеимаже](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
