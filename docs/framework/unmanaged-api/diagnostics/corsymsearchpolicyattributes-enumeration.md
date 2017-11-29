---
title: "Перечисление CorSymSearchPolicyAttributes"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSymSearchPolicyAttributes
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSymSearchPolicyAttributes
helpviewer_keywords: CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 016378de8d4ba4b6f16f7e7b91b6427f73c9687d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="1f7fa-102">Перечисление CorSymSearchPolicyAttributes</span><span class="sxs-lookup"><span data-stu-id="1f7fa-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="1f7fa-103">Определяет политику для использования при выполнении поиска для средства чтения символов.</span><span class="sxs-lookup"><span data-stu-id="1f7fa-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="1f7fa-104">Эти константы используются [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) и [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) методы.</span><span class="sxs-lookup"><span data-stu-id="1f7fa-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1f7fa-105">Он представляет угрозу безопасности, чтобы открыть файл программы (PDB) из ненадежного источника.</span><span class="sxs-lookup"><span data-stu-id="1f7fa-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f7fa-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f7fa-106">Syntax</span></span>  
  
```  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="1f7fa-107">Члены</span><span class="sxs-lookup"><span data-stu-id="1f7fa-107">Members</span></span>  
  
|<span data-ttu-id="1f7fa-108">Член</span><span class="sxs-lookup"><span data-stu-id="1f7fa-108">Member</span></span>|<span data-ttu-id="1f7fa-109">Описание</span><span class="sxs-lookup"><span data-stu-id="1f7fa-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="1f7fa-110">Запрашивает в реестре для пути поиска символов.</span><span class="sxs-lookup"><span data-stu-id="1f7fa-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="1f7fa-111">Обращается к серверу символов.</span><span class="sxs-lookup"><span data-stu-id="1f7fa-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="1f7fa-112">Выполняет поиск путь, указанный в каталоге отладки.</span><span class="sxs-lookup"><span data-stu-id="1f7fa-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="1f7fa-113">Ищет PDB-ФАЙЛ в месте расположения файла .exe.</span><span class="sxs-lookup"><span data-stu-id="1f7fa-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1f7fa-114">Требования</span><span class="sxs-lookup"><span data-stu-id="1f7fa-114">Requirements</span></span>  
 <span data-ttu-id="1f7fa-115">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1f7fa-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f7fa-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1f7fa-116">See Also</span></span>  
 [<span data-ttu-id="1f7fa-117">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="1f7fa-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
