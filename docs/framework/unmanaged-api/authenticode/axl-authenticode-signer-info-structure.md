---
title: Структура AXL_AUTHENTICODE_SIGNER_INFO
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b9f54c7c57d122ac1214b9f31cc4e1d1cddd71c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44184331"
---
# <a name="axlauthenticodesignerinfo-structure"></a>Структура AXL_AUTHENTICODE_SIGNER_INFO
Определяет информацию о подписавшем Authenticode.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    LPCWSTR pwszHash  
    LPCWSTR pwszDescription;  
    LPCWSTR pwszDescriptionUrl;  
    PCCERT_CHAIN_CONTEXT pChainContext  
} AXL_AUTHENTICODE_SIGNER_INFO, * PAXL_AUTHENTICODE_SIGNER_INFO;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`cbSize`|Размер этой структуры.|  
|`dwError`|Код ошибки.|  
|`algHash`|Хэш-алгоритм.|  
|`pwszHash`|Хэш.|  
|`pwszDescription`|Описание.|  
|`pwszDescriptionUrl`|URL-адрес описания.|  
|`pChainContext`|Контекст цепочки подписавшего. См. в разделе [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) структуры.|  
  
## <a name="see-also"></a>См. также  
 [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
