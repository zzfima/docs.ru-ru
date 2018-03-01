---
title: "Функция GetTypeLibInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4f6b1ad18809b46b7a2b38137231028f696d51b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="gettypelibinfo-function"></a>Функция GetTypeLibInfo
Возвращает сведения об указанной библиотеки типов с помощью проверки его [TLIBATTR](https://msdn.microsoft.com/library/ms221376\(v=vs.85\).aspx) структуры.  
  
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
 [out] Идентификатор GUID для библиотеки типов.  
  
 `pTypeLibLCID`  
 [out] Локализация идентификатор библиотеки типов.  
  
 `pTypeLibPlatform`  
 [out] Объект [SYSKIND](https://msdn.microsoft.com/library/ms221272\(v=vs.85\).aspx) флаг, определяющий целевую операционную систему для библиотеки типов. Общие значения: SYS_WIN32 и SYS_WIN64.  
  
 `pTypeLibMajorVer`  
 [out] Основной номер версии библиотеки типов. Например, для версии *x.y*, основной номер версии — *x*.  
  
 `pTypeLibMinorVer`  
 [out] Дополнительный номер версии библиотеки типов. Например, для версии *x.y*, дополнительный номер версии — *y*.  
  
## <a name="remarks"></a>Примечания  
 `GetTypeLibInfo` Функция вызывается функцией [Tlbexp.exe (программа экспорта библиотек типов)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md). Это средство создает библиотеку типов, описывающую типы в сборке среды CLR.  
  
 Если какой-либо параметр имеет значение null, функция возвращает `HRESULT` из `E_POINTER`. В противном случае возвращает значение `S_OK`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** TlbRef.h  
  
 **Библиотека:** TlbRef.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Вспомогательные функции Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [Функция LoadTypeLibEx](https://msdn.microsoft.com/library/ms221249\(v=vs.85\).aspx)
