---
title: Метод IMetaDataEmit::SetClassLayout
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetClassLayout
helpviewer_keywords:
- IMetaDataEmit::SetClassLayout method [.NET Framework metadata]
- SetClassLayout method [.NET Framework metadata]
ms.assetid: 2576c449-388d-4434-a0e1-9f53991e11b6
topic_type:
- apiref
ms.openlocfilehash: e855868d18fc6cffdd5d92cfa401606caf45b76c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177561"
---
# <a name="imetadataemitsetclasslayout-method"></a>Метод IMetaDataEmit::SetClassLayout
Завершает расположение полей для класса, определяемого предыдущим вызовом в [метод DefineTypeDef.](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,
    [in]  DWORD               dwPackSize,
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],
    [in]  ULONG               ulClassSize
);  
```  
  
## <a name="parameters"></a>Параметры  
 `td`  
 (в) Токен, `mdTypeDef` опоедающие класс, который должен быть выложен.  
  
 `dwPackSize`  
 (в) Размер упаковки: 1, 2, 4, 8 или 16 байтов. Размер упаковки — это количество байтов между смежными полями.  
  
 `rFieldOffsets`  
 (в) Массив [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) структур, каждая из которых определяет поле класса и смещение поля в классе. Упраздните `mdTokenNil`массив с помощью .  
  
 `ulClassSize`  
 (в) Размер, в байтах, класса.  
  
## <a name="remarks"></a>Remarks  
 Класс первоначально определяется путем вызова метода [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) и указания одного из трех макетов для полей класса: автоматического, последовательного или явного. Как правило, вы будете использовать автоматический макет и позволить времени выполнения выбрать лучший способ выложить поля.  
  
 Однако, возможно, вы захотите, чтобы поля были выложены в соответствии с расположением, которое использует неуправляемый код. В этом случае выберите либо последовательный, либо `SetClassLayout` явный макет и позвоните для завершения макета полей:  
  
- Последовательная компоновка: Укажите размер упаковки. Поле выравнивается либо в зависимости от его естественного размера или размера упаковки, в зависимости от того, что приводит к меньшему смещению поля. `rFieldOffsets` Установить `ulClassSize` и к нулю.  
  
- Явная компоновка: либо укажите смещение каждого поля, либо укажите размер класса и размер упаковки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
