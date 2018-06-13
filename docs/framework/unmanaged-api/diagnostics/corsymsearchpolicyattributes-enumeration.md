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
ms.openlocfilehash: a4c3aedea4cc8ce2d8fb8c0c0bf3fead727dcf64
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425864"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="bfcee-102">Перечисление CorSymSearchPolicyAttributes</span><span class="sxs-lookup"><span data-stu-id="bfcee-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="bfcee-103">Определяет политику для использования при выполнении поиска для средства чтения символов.</span><span class="sxs-lookup"><span data-stu-id="bfcee-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="bfcee-104">Эти константы используются [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) и [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) методы.</span><span class="sxs-lookup"><span data-stu-id="bfcee-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bfcee-105">Он представляет угрозу безопасности, чтобы открыть файл программы (PDB) из ненадежного источника.</span><span class="sxs-lookup"><span data-stu-id="bfcee-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfcee-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bfcee-106">Syntax</span></span>  
  
```  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="bfcee-107">Участники</span><span class="sxs-lookup"><span data-stu-id="bfcee-107">Members</span></span>  
  
|<span data-ttu-id="bfcee-108">Член</span><span class="sxs-lookup"><span data-stu-id="bfcee-108">Member</span></span>|<span data-ttu-id="bfcee-109">Описание</span><span class="sxs-lookup"><span data-stu-id="bfcee-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="bfcee-110">Запрашивает в реестре для пути поиска символов.</span><span class="sxs-lookup"><span data-stu-id="bfcee-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="bfcee-111">Обращается к серверу символов.</span><span class="sxs-lookup"><span data-stu-id="bfcee-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="bfcee-112">Выполняет поиск путь, указанный в каталоге отладки.</span><span class="sxs-lookup"><span data-stu-id="bfcee-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="bfcee-113">Ищет PDB-ФАЙЛ в месте расположения файла .exe.</span><span class="sxs-lookup"><span data-stu-id="bfcee-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bfcee-114">Требования</span><span class="sxs-lookup"><span data-stu-id="bfcee-114">Requirements</span></span>  
 <span data-ttu-id="bfcee-115">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bfcee-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfcee-116">См. также</span><span class="sxs-lookup"><span data-stu-id="bfcee-116">See Also</span></span>  
 [<span data-ttu-id="bfcee-117">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="bfcee-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
