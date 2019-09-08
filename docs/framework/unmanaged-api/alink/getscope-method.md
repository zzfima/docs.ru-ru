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
ms.openlocfilehash: b3a0e42e9ffb99896bdd09dbbab65eafb40cafff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777204"
---
# <a name="getscope-method"></a>Метод GetScope
Возвращает область импорта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  
 `AssemblyID`  
 Уникальный идентификатор сборки для импорта.  
  
 `FileToken`  
 Уникальный идентификатор файла для импорта.  
  
 `dwScope`  
 Отсчитываемая от нуля область для импорта.  
  
 `ppImportScope`  
 Получает интерфейс [интерфейса IMetaDataImport](../metadata/imetadataimport-interface.md) для области.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается с ошибкой, возвращает значение S_OK.  
  
## <a name="requirements"></a>Требования  
 Требуется ALink. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
