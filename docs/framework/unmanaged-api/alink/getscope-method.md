---
title: Метод GetScope
ms.date: 03/30/2017
api_name:
- IALink.GetScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope
helpviewer_keywords:
- GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c8de6c745b1d32c3d98f1b54e822ab084f0574b2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486203"
---
# <a name="getscope-method"></a>Метод GetScope
Получает область импортирования.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  
 `AssemblyID`  
 Уникальный идентификатор импортируемой сборки.  
  
 `FileToken`  
 Уникальный идентификатор файла для импорта.  
  
 `dwScope`  
 Отсчитываемый от нуля область для импорта.  
  
 `ppImportScope`  
 Получает [интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) интерфейс для области.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK, если метод выполнен успешно.  
  
## <a name="requirements"></a>Требования  
 Требуется alink.h  
  
## <a name="see-also"></a>См. также
- [Интерфейс IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Интерфейс IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [API ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
