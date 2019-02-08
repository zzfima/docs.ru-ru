---
title: Метод ICLRDebuggingLibraryProvider::ProvideLibrary
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider.ProvideLibrary Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider::ProvideLibrary
helpviewer_keywords:
- ProvideLibrary method [.NET Framework debugging]
- ICLRDebuggingLibraryProvider::ProvideLibrary method [.NET Framework debugging]
ms.assetid: 86f06245-9517-49be-8d8c-ca5deaf34c02
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5f66d91434fd92ff80bb17e04bf38bb0b631e819
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825505"
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a>Метод ICLRDebuggingLibraryProvider::ProvideLibrary
Получает поставщика библиотеки интерфейс обратного вызова, который позволяет среде выполнения (CLR) версии библиотеки отладки находить и загружать по требованию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ProvideLibrary(  
     [in] const WCHAR* pwszFileName,  
     [in] DWORD dwTimestamp,  
     [in] DWORD dwSizeOfImage,  
     [out] HMODULE* hModule);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pwszFilename`  
 [in] Имя запрашиваемого модуля.  
  
 `dwTimestamp`  
 [in] Отметку даты и времени в заголовке COFF файл PE-файлов.  
  
 `pLibraryProvider`  
 [in] `SizeOfImage` Поля в заголовке COFF необязательный файл PE-файлов.  
  
 `hModule`  
 [out] Дескриптор запрошенного модуля.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Примечания  
 `ProvideLibrary` позволяет отладчику содержит модули, которые необходимы для отладки определенные файлы среды CLR, такие как mscordbi.dll и mscordacwks.dll. Дескрипторы модулей должны оставаться действительными до вызова [ICLRDebugging::CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) метод указывает, что их можно освободить, после чего это обязанность вызывающего для освобождения дескрипторов.  
  
 Отладчик может использовать любые доступные средства поиска или получения модуля отладки.  
  
> [!IMPORTANT]
>  Эта функция позволяет API вызывающего объекта предоставить модули, содержащие исполняемый файл и потенциально вредоносный код. По соображениям безопасности вызывающего объекта не следует использовать `ProvideLibrary` для распределения любого кода, что он не желает выполняться самостоятельно.  
>   
>  Если обнаружена серьезная угроза безопасности в уже выпущенной библиотеке, например mscordbi.dll или mscordacwks.dll, оболочка может быть исправлена для распознавания плохих версий файлов. Оболочки можно выполнять запросы к исправленных версий файлов и отвергать плохие версии, если они указаны в ответ на любой запрос. Это может произойти только в том случае, если пользователь обновить до новой версии оболочки. Неисправленные версии будет оставаться уязвимыми.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
