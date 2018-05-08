---
title: Метод SetPEKind
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4b985aeb97621e552e9e97581e67cae029d019ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="setpekind-method"></a>Метод SetPEKind
Определяет переносимый исполняемый тип, зависящий от компьютера или конкретного компьютера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
#### <a name="parameters"></a>Параметры  
 `AssemblyID`  
 Идентификатор сборки.  
  
 `FileToken`  
 Маркер файла, для которого требуется задать тип PE. Может иметь значение NULL, если `AssemblyID` не указывает на несвязанный NETMODULE-файл.  
  
 `dwPEKind`  
 Тип среды предустановки, как указано в [перечисление CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).  
  
 `dwMachine`  
 Архитектуры конечного компьютера, как указано в заголовке NT.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK, если метод выполнен успешно.  
  
## <a name="requirements"></a>Требования  
 Требуется alink.h.  
  
## <a name="see-also"></a>См. также  
 [Метод GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)  
 [Интерфейс IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [Интерфейс IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [API ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
