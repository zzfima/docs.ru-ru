---
title: Метод ICorPublishAppDomainEnum::Next
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum::Next
helpviewer_keywords:
- Next method, ICorPublishAppDomainEnum interface [.NET Framework debugging]
- ICorPublishAppDomainEnum::Next method [.NET Framework debugging]
ms.assetid: ad37cd10-0339-4d08-9b0e-4b3428bb4dc3
topic_type:
- apiref
ms.openlocfilehash: 6f7f400c51ded0b98c0c2286cb6f90bbd77e47d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178402"
---
# <a name="icorpublishappdomainenumnext-method"></a>Метод ICorPublishAppDomainEnum::Next
Получает указанное количество доменов приложений, которые в настоящее время существуют в процессе, начиная с текущей позиции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `celt`  
 (в) Количество элементов, которые необходимо получить.  
  
 `objects`  
 (ваут) Указатель на массив извлеченных объектов [ICorPublishAppDomain,](icorpublishappdomain-interface.md) каждый из которых представляет собой домен приложения.  
  
 `pceltFetched`  
 (ваут) Указатель на количество доменов приложений фактически вернулся. Это значение может `celt` быть нулевым, если он один.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorPub.idl, CorPub.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)
