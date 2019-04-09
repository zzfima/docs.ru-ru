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
ms.openlocfilehash: 8a9b0f085820bac12638c0310ab23b2eafacb23b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186177"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="757e0-102">Перечисление CorSymSearchPolicyAttributes</span><span class="sxs-lookup"><span data-stu-id="757e0-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="757e0-103">Указывает политику, используемую при выполнении поиска для средства чтения символов.</span><span class="sxs-lookup"><span data-stu-id="757e0-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="757e0-104">Эти константы используются [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) и [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) методы.</span><span class="sxs-lookup"><span data-stu-id="757e0-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="757e0-105">Он представляет угрозу безопасности, чтобы открыть файл базы данных (PDB) программы из ненадежного источника.</span><span class="sxs-lookup"><span data-stu-id="757e0-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="757e0-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="757e0-106">Syntax</span></span>  
  
```  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="757e0-107">Участники</span><span class="sxs-lookup"><span data-stu-id="757e0-107">Members</span></span>  
  
|<span data-ttu-id="757e0-108">Член</span><span class="sxs-lookup"><span data-stu-id="757e0-108">Member</span></span>|<span data-ttu-id="757e0-109">Описание</span><span class="sxs-lookup"><span data-stu-id="757e0-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="757e0-110">Запрашивает в реестре для пути поиска символов.</span><span class="sxs-lookup"><span data-stu-id="757e0-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="757e0-111">Обращается к серверу символов.</span><span class="sxs-lookup"><span data-stu-id="757e0-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="757e0-112">Выполняет поиск путь, указанный в каталоге отладки.</span><span class="sxs-lookup"><span data-stu-id="757e0-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="757e0-113">Выполняет поиск PDB-ФАЙЛ в месте расположения файла .exe.</span><span class="sxs-lookup"><span data-stu-id="757e0-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="757e0-114">Требования</span><span class="sxs-lookup"><span data-stu-id="757e0-114">Requirements</span></span>  
 <span data-ttu-id="757e0-115">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="757e0-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="757e0-116">См. также</span><span class="sxs-lookup"><span data-stu-id="757e0-116">See also</span></span>

- [<span data-ttu-id="757e0-117">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="757e0-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
