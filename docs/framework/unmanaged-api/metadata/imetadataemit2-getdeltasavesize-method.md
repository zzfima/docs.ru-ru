---
title: Метод IMetaDataEmit2::GetDeltaSaveSize
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.GetDeltaSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::GetDeltaSaveSize
helpviewer_keywords:
- IMetaDataEmit2::GetDeltaSaveSize method [.NET Framework metadata]
- GetDeltaSaveSize method [.NET Framework metadata]
ms.assetid: 036db5e7-8211-4645-9a34-03d1a89be955
topic_type:
- apiref
ms.openlocfilehash: 219d3196e3b2125033a23623b7e77e31c6f1ff03
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440488"
---
# <a name="imetadataemit2getdeltasavesize-method"></a>Метод IMetaDataEmit2::GetDeltaSaveSize
Возвращает значение, указывающее на изменение размера метаданных, полученное в результате текущего сеанса "изменить и продолжить".  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `fSave`  
 окне Одно из значений [корсавесизе](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) , указывающее требуемый уровень точности. Для .NET Framework версии 2,0 этот параметр игнорируется.  
  
 `pdwSaveSize`  
 заполняет Изменение размера метаданных.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
