---
title: Структура AXL_AUTHENTICODE_SIGNER_INFO
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c69be0de98e2996176e7360bae0bb0736c1a797
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038445"
---
# <a name="axl_authenticode_signer_info-structure"></a>Структура AXL_AUTHENTICODE_SIGNER_INFO
Определяет информацию о подписавшем Authenticode.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
|`pChainContext`|Контекст цепочки подписавшего. См. структуру [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) .|  
  
## <a name="see-also"></a>См. также

- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
