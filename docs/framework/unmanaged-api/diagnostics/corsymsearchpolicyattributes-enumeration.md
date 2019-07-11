---
title: Перечисление CorSymSearchPolicyAttributes
ms.date: 03/30/2017
api_name:
- CorSymSearchPolicyAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymSearchPolicyAttributes
helpviewer_keywords:
- CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 29766636cd151744d25cf66deb60cd2e066e1b32
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775778"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a>Перечисление CorSymSearchPolicyAttributes
Указывает политику, используемую при выполнении поиска для средства чтения символов. Эти константы используются [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) и [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) методы.  
  
> [!IMPORTANT]
>  Он представляет угрозу безопасности, чтобы открыть файл базы данных (PDB) программы из ненадежного источника.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`AllowRegistryAccess`|Запрашивает в реестре для пути поиска символов.|  
|`AllowSymbolServerAccess`|Обращается к серверу символов.|  
|`AllowOriginalPathAccess`|Выполняет поиск путь, указанный в каталоге отладки.|  
|`AllowReferencePathAccess`|Выполняет поиск PDB-ФАЙЛ в месте расположения файла .exe.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>См. также

- [Перечисления хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
