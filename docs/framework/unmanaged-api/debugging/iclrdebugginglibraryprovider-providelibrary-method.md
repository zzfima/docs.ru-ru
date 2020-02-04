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
ms.openlocfilehash: d0c283232ff8eca1af9f3ff4448fb7f4c81d554f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789032"
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
окне Поле `SizeOfImage`, хранящееся в необязательном заголовке файла PE файлов в формате COFF.

`hModule` \
заполняет Обработчик для запрошенного модуля.

## <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.

|HRESULT|Описание|
|-------------|-----------------|
|S_OK|Метод завершился успешно.|

## <a name="exceptions"></a>Исключения

## <a name="remarks"></a>Заметки

`ProvideLibrary` позволяет отладчику предоставлять модули, необходимые для отладки конкретных файлов среды CLR, таких как mscordbi. dll и мскордаквкс. dll. Дескрипторы модулей должны оставаться действительными до тех пор, пока вызов метода [ICLRDebugging:: CanUnloadNow](iclrdebugging-canunloadnow-method.md) не указывает на то, что они могут быть освобождены, и на этом этапе вызывающая сторона обязана освободить дескрипторы.

Отладчик может использовать любые доступные средства для размещения или получения модуля отладки.

> [!IMPORTANT]
> Эта функция позволяет вызывающему API предоставлять модули, которые содержат исполняемый и, возможно, вредоносный код. В целях обеспечения безопасности вызывающий объект не должен использовать `ProvideLibrary` для распространения кода, который не готов к выполнению.
>
> При обнаружении серьезной проблемы безопасности в уже выпущенной библиотеке, такой как mscordbi. dll или мскордаквкс. dll, оболочка совместимости может быть исправлена для распознавания неправильных версий файлов. После этого оболочка совместимости может выдавать запросы на исправленные версии файлов и отклонять поврежденные версии, если они предоставляются в ответ на любой запрос. Это может произойти только в том случае, если пользователь установил исправление для новой версии оболочки совместимости. Неисправленные версии останутся уязвимыми.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок:** CorDebug.idl, CorDebug.h

**Библиотека:** CorGuids.lib

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]

## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
