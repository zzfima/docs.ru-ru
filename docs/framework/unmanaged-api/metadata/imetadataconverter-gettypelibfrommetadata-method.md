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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c0943971dc4858e2dce4d977f6f906b26f8ad51e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044393"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a>Метод IMetaDataConverter::GetTypeLibFromMetaData
Возвращает указатель на `ITypeLib` экземпляр, представляющий библиотеку типов, с заданными именами библиотеки и модуль.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,   
    [in]  BSTR     strTlbName,   
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `strModule`  
 [in] Имя модуля библиотеки типов.  
  
 `strTlbName`  
 [in] Имя библиотеки типов.  
  
 `ppITL`  
 [out] Указатель на расположение, которое получает адрес `ITypeLib` экземпляр, представляющий библиотеку типов.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataConverter](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)
