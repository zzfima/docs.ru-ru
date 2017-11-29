---
title: "Метод ICLRDebuggingLibraryProvider::ProvideLibrary"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebuggingLibraryProvider.ProvideLibrary Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDebuggingLibraryProvider::ProvideLibrary
helpviewer_keywords:
- ProvideLibrary method [.NET Framework debugging]
- ICLRDebuggingLibraryProvider::ProvideLibrary method [.NET Framework debugging]
ms.assetid: 86f06245-9517-49be-8d8c-ca5deaf34c02
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d3a34579787e976022ffa8caf7c29d8a565a7c73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a>Метод ICLRDebuggingLibraryProvider::ProvideLibrary
Возвращает поставщика библиотеки интерфейс обратного вызова, который позволяет среде (CLR) от версии библиотеки отладки находить и загружать по требованию.  
  
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
 [in] Отметка времени даты, сохраненным в заголовке COFF файл PE-файлов.  
  
 `pLibraryProvider`  
 [in] `SizeOfImage` Поля, сохраненным в заголовке COFF необязательный файл PE-файлов.  
  
 `hModule`  
 [out] Дескриптор запрошенного модуля.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Примечания  
 `ProvideLibrary`позволяет отладчику предоставляют модули, которые необходимы для отладки конкретных файлы среды CLR, такие как mscordbi.dll и mscordacwks.dll. Дескрипторы модулей должны оставаться действительными до вызова [ICLRDebugging::CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) метод указывает, что их можно освободить, после чего он вызывающим для освобождения дескрипторов.  
  
 Отладчик может использовать любые доступные средства поиска или получения модуля отладки.  
  
> [!IMPORTANT]
>  Эта функция позволяет API вызывающему предоставлять модули, содержащие исполняемые и потенциально вредоносный код. По соображениям безопасности не следует использовать код, вызывающий `ProvideLibrary` для распределения любого кода, что он не желает выполняться самостоятельно.  
>   
>  Если обнаружено серьезную проблему безопасности в уже выпущенной библиотеке, например mscordbi.dll или mscordacwks.dll, оболочка может быть исправлена для распознавания плохих версий файлов. Оболочки можно выполнять запросы к обновленной версии файлов и отвергать плохие версии, если они предоставляются в ответ на запрос. Это может произойти только в том случае, если пользователь исправления до новой версии оболочки. Неисправленные версии останутся незащищенными.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
