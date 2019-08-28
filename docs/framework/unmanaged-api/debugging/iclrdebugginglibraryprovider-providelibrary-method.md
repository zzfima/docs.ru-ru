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
ms.openlocfilehash: a1b02bb74a61e64a3ed9875fcf88e018de9f6317
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70041445"
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a>Метод ICLRDebuggingLibraryProvider::ProvideLibrary

Возвращает интерфейс обратного вызова поставщика библиотеки, который позволяет находить и загружать библиотеки отладки среды CLR для конкретной версии.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT ProvideLibrary(
     [in] const WCHAR* pwszFileName,
     [in] DWORD dwTimestamp,
     [in] DWORD dwSizeOfImage,
     [out] HMODULE* hModule);
```

## <a name="parameters"></a>Параметры

`pwszFilename` \
окне Имя запрашиваемого модуля.

`dwTimestamp` \
окне Метка даты и времени, хранящаяся в заголовке COFF файлов PE.

`pLibraryProvider` \
окне `SizeOfImage` Поле, хранящееся в необязательном заголовке файла PE файлов в формате COFF.

`hModule` \
заполняет Обработчик для запрошенного модуля.

## <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.

|HRESULT|Описание|
|-------------|-----------------|
|S_OK|Метод завершился успешно.|

## <a name="exceptions"></a>Исключения

## <a name="remarks"></a>Примечания

`ProvideLibrary`позволяет отладчику предоставлять модули, необходимые для отладки конкретных файлов среды CLR, таких как mscordbi. dll и мскордаквкс. dll. Дескрипторы модулей должны оставаться действительными до тех пор, пока вызов метода [ICLRDebugging:: CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) не указывает на то, что они могут быть освобождены, и на этом этапе вызывающая сторона обязана освободить дескрипторы.

Отладчик может использовать любые доступные средства для размещения или получения модуля отладки.

> [!IMPORTANT]
> Эта функция позволяет вызывающему API предоставлять модули, которые содержат исполняемый и, возможно, вредоносный код. В целях обеспечения безопасности вызывающий объект не должен использовать `ProvideLibrary` для распространения кода, который не готов к выполнению.
>
> При обнаружении серьезной проблемы безопасности в уже выпущенной библиотеке, такой как mscordbi. dll или мскордаквкс. dll, оболочка совместимости может быть исправлена для распознавания неправильных версий файлов. После этого оболочка совместимости может выдавать запросы на исправленные версии файлов и отклонять поврежденные версии, если они предоставляются в ответ на любой запрос. Это может произойти только в том случае, если пользователь установил исправление для новой версии оболочки совместимости. Неисправленные версии останутся уязвимыми.

## <a name="requirements"></a>Требования

**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок.** CorDebug. idl, CorDebug. h

**Библиотечная** Коргуидс. lib

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
