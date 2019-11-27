---
title: Метод IMetaDataConverter::GetTypeLibFromMetaData
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetTypeLibFromMetaData
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetTypeLibFromMetaData
helpviewer_keywords:
- GetTypeLibFromMetaData method [.NET Framework metadata]
- IMetaDataConverter::GetTypeLibFromMetaData method [.NET Framework metadata]
ms.assetid: 90eab7b3-1fae-4af4-8bce-f7bc0e188a99
topic_type:
- apiref
ms.openlocfilehash: 9da4e34fa948db2fc73cbde813bac9b3430605ca
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436260"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a>Метод IMetaDataConverter::GetTypeLibFromMetaData
Возвращает указатель на экземпляр `ITypeLib`, представляющий библиотеку типов с указанными именами библиотеки и модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,   
    [in]  BSTR     strTlbName,   
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `strModule`  
 окне Имя модуля библиотеки типов.  
  
 `strTlbName`  
 окне Имя библиотеки типов.  
  
 `ppITL`  
 заполняет Указатель на расположение, которое получает адрес экземпляра `ITypeLib`, представляющего библиотеку типов.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataConverter](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)
