---
title: Метод IMetaDataEmit::SetHandler
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetHandler
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ac0e5db4a87b49d631bad4411f03fae8c1199aea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050029"
---
# <a name="imetadataemitsethandler-method"></a>Метод IMetaDataEmit::SetHandler
Задает метод, который ссылается заданный `IUnknown` указатель в виде обратного вызова уведомления для повторного сопоставления маркера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pUnk`  
 [in] Регистрируемый дескриптор.  
  
## <a name="remarks"></a>Примечания  
 Подсистема метаданных отправляет уведомление, используя метод, предоставляемый `SetHandler`, компилятору, который не создает записи оптимальным образом и который хотите оптимизировать сохраненных записей.  
  
 Если метод обратного вызова не предоставляется через `SetHandler`, будет выполняться без оптимизации на сохранить за исключением импортировать несколько областей, были объединены с помощью `IMapToken` на слияния для каждой области.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
