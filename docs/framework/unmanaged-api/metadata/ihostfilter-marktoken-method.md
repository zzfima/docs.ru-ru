---
title: Метод IHostFilter::MarkToken
ms.date: 03/30/2017
api_name:
- IHostFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type:
- apiref
ms.openlocfilehash: 6f8df824ed36b7793d5f07e5b5cf51f65f9c8e24
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432242"
---
# <a name="ihostfiltermarktoken-method"></a>Метод IHostFilter::MarkToken
Указывает, что заданный маркер метаданных будет обработан.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `tk`  
 окне Токен метаданных для обработки.  
  
## <a name="remarks"></a>Заметки  
 Как правило, требуется обработка маркера, если он находится в области действия метаданных. Метод `MarkToken` передается в обработчик метаданных с помощью метода [IMetaDataEmit:: сесандлер](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [Интерфейс IHostFilter](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)
