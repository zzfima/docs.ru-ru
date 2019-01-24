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
ms.openlocfilehash: dbd7cd2d5ec515c529905ad524cedf257155b7e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569366"
---
# <a name="gettypelibinfo-function"></a>Функция GetTypeLibInfo
Возвращает сведения об указанной библиотеки типов с помощью проверки его [TLIBATTR](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagtlibattr) структуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `szFile`  
 [in] Имя файла библиотеки типов.  
  
 `pTypeLibID`  
 [out] Идентификатор GUID библиотеки типов.  
  
 `pTypeLibLCID`  
 [out] Идентификатор локализации библиотеки типов.  
  
 `pTypeLibPlatform`  
 [out] Объект [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) флаг, определяющий, Целевая операционная система для библиотеки типов. Обычные значения: SYS_WIN32 и SYS_WIN64.  
  
 `pTypeLibMajorVer`  
 [out] Основной номер версии библиотеки типов. Например, для версии *x.y*, основной номер версии — *x*.  
  
 `pTypeLibMinorVer`  
 [out] Дополнительный номер версии библиотеки типов. Например, для версии *x.y*, дополнительный номер версии — *y*.  
  
## <a name="remarks"></a>Примечания  
 `GetTypeLibInfo` Функция вызывается из [Tlbexp.exe (программа экспорта библиотек типов)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md). Это средство создает библиотеку типов, описывающую типы в сборке среды CLR.  
  
 Если какой-либо параметр имеет значение null, функция возвращает `HRESULT` из `E_POINTER`. В противном случае возвращает значение `S_OK`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** TlbRef.h  
  
 **Библиотека:** TlbRef.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Вспомогательные функции Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [Функция LoadTypeLibEx](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
