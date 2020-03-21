---
title: Метод ICorPublishAppDomain::GetName
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetName
helpviewer_keywords:
- GetName method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetName method [.NET Framework debugging]
ms.assetid: 6ef8ac9b-9803-4b65-8b13-25f3e0b1bc6b
topic_type:
- apiref
ms.openlocfilehash: 762c637696fdf79ccab6702918b5bf962ea55903
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178407"
---
# <a name="icorpublishappdomaingetname-method"></a>Метод ICorPublishAppDomain::GetName
Получает название домена приложения, который представлен этим [ICorPublishAppDomain](icorpublishappdomain-interface.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `cchName`  
 [in] Размер массива `szName`.  
  
 `pcchName`  
 (ваут) Указатель на количество широких символов, включая нулевой `szName` символ, вернулся в массив.  
  
 `szName`  
 (ваут) Массив, в котором можно хранить имя.  
  
## <a name="remarks"></a>Remarks  
 Если `szName` `GetName` метод не является нулевым, `cchName` метод копирует символы (включая `szName`терминатор null) в . Если не-недействительной `pcchName`возвращается в , фактическое число символов в имени (в том `szName` числе нулевой терминатор) хранится в массиве.  
  
 Метод `GetName` возвращает S_OK HRESULT независимо от того, сколько символов было скопировано.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorPub.idl, CorPub.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorPublishAppDomain](icorpublishappdomain-interface.md)
