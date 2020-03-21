---
title: Метод IMapToken::Map
ms.date: 03/30/2017
api_name:
- IMapToken.Map
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type:
- apiref
ms.openlocfilehash: 428b022ed560648f59798154d5987d382938c280
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176075"
---
# <a name="imaptokenmap-method"></a>Метод IMapToken::Map
Отображает связь между сборками с помощью подписей метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `tkImp`  
 (в) Токен метаданных, представляющий объект импортированного кода.  
  
 `tkEmit`  
 (в) Токен метаданных, представляющий испускаемый объект кода.  
  
## <a name="remarks"></a>Remarks  
 Когда повторная карта токенов происходит во время слияния, исходный маркер приобщен в области метаданных импортируемых (источников), а новый маркер — в области испускаемых (целевых) метаданных.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
