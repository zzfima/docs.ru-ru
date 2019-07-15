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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c455b5196ceafef924de59e9134b89ed62455520
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737225"
---
# <a name="imetadataemitsetclasslayout-method"></a>Метод IMetaDataEmit::SetClassLayout
Макет полей для класса, который был определен во время предыдущего вызова для завершения [метод DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).  
  
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
 [in] `mdTypeDef` Токен, который указывает класс располагаться.  
  
 `dwPackSize`  
 [in] Упаковочный размер: 1, 2, 4, 8 или 16 байт. Упаковочный размер равен число байтов между смежными полями.  
  
 `rFieldOffsets`  
 [in] Массив [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) структуры, каждый из которых указывает, что поля класса и смещение в пределах класса. Массива с `mdTokenNil`.  
  
 `ulClassSize`  
 [in] Размер в байтах, класса.  
  
## <a name="remarks"></a>Примечания  
 Класс изначально определяется путем вызова [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) метод и задавая один из трех структур поля класса: Авто, последовательный или явной. Как правило необходимо использование автоматической разметки и позволить среде выполнения выбрать лучший способ расположения полей.  
  
 Тем не менее может потребоваться поля, располагались в порядке их использования неуправляемым кодом. В этом случае выберите либо последовательный или явный макет и вызов `SetClassLayout` для завершения макета полей:  
  
- Последовательное размещение: Укажите размер пакета. Поле выравнивается в соответствии с его естественному размеру или упаковочный размер, что приводит меньшего размера смещение поля. Задайте `rFieldOffsets` и `ulClassSize` до нуля.  
  
- Явное размещение: Задайте смещение каждого поля или размер класса, а также размером уплотнения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
