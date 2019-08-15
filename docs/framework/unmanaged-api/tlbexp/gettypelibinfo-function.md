---
title: Функция GetTypeLibInfo
ms.date: 03/30/2017
api_name:
- GetTypeLibInfo
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- GetTypeLibInfo
helpviewer_keywords:
- GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7da0986269189ba5c2dfa0f10d509bf51deb446d
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040206"
---
# <a name="gettypelibinfo-function"></a>Функция GetTypeLibInfo
Возвращает сведения о указанной библиотеке типов, изучая ее структуру [тлибаттр](https://docs.microsoft.com/windows/win32/api/oaidl/ns-oaidl-tlibattr) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `szFile`  
 окне Имя файла библиотеки типов.  
  
 `pTypeLibID`  
 заполняет Идентификатор GUID библиотеки типов.  
  
 `pTypeLibLCID`  
 заполняет ИДЕНТИФИКАТОР локализации библиотеки типов.  
  
 `pTypeLibPlatform`  
 заполняет Флаг [Сискинд](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind) , определяющий целевую операционную систему для библиотеки типов. Распространенные значения — SYS_WIN32 и SYS_WIN64.  
  
 `pTypeLibMajorVer`  
 заполняет Основной номер версии библиотеки типов. Например, для версии *x. y*основной номер версии — *x*.  
  
 `pTypeLibMinorVer`  
 заполняет Дополнительный номер версии библиотеки типов. Например, для версии *x. y*дополнительный номер версии — *y*.  
  
## <a name="remarks"></a>Примечания  
 Функция вызывается программой [Tlbexp. exe (программа экспорта библиотек типов).](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) `GetTypeLibInfo` Это средство создает библиотеку типов, описывающую типы в сборке среды CLR.  
  
 Если какой-либо из параметров имеет значение null, `HRESULT` функция `E_POINTER`возвращает объект. В противном случае она возвращает `S_OK`.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Тлбреф. h  
  
 **Библиотечная** Тлбреф. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Вспомогательные функции Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [Функция Лоадтипелибекс](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
