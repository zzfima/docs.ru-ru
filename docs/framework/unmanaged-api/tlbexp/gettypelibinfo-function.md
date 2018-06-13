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
ms.openlocfilehash: 56a9b97f37240e385dbd1788bafea62578d687a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457872"
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
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Вспомогательные функции Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [Функция LoadTypeLibEx](https://msdn.microsoft.com/library/ms221249\(v=vs.85\).aspx)
