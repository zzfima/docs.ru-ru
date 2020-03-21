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
ms.openlocfilehash: 786e53d43ecde0bc3a97fadb77184d25d41430bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178346"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="3b55a-102">Перечисление CorSymSearchPolicyAttributes</span><span class="sxs-lookup"><span data-stu-id="3b55a-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="3b55a-103">Определяет политику, которая будет использоваться при поиске считывателя символов.</span><span class="sxs-lookup"><span data-stu-id="3b55a-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="3b55a-104">Эти константы используются методами [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) и [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) методы.</span><span class="sxs-lookup"><span data-stu-id="3b55a-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3b55a-105">Открытие файла базы данных программы (PDB) из недоверчивого источника представляет собой риск для обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="3b55a-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b55a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b55a-106">Syntax</span></span>  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="3b55a-107">Члены</span><span class="sxs-lookup"><span data-stu-id="3b55a-107">Members</span></span>  
  
|<span data-ttu-id="3b55a-108">Участник</span><span class="sxs-lookup"><span data-stu-id="3b55a-108">Member</span></span>|<span data-ttu-id="3b55a-109">Описание</span><span class="sxs-lookup"><span data-stu-id="3b55a-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="3b55a-110">Запрашивает реестр путей поиска символов.</span><span class="sxs-lookup"><span data-stu-id="3b55a-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="3b55a-111">Доступ к серверу символов.</span><span class="sxs-lookup"><span data-stu-id="3b55a-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="3b55a-112">Поиск пути, указанного в каталоге Debug.</span><span class="sxs-lookup"><span data-stu-id="3b55a-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="3b55a-113">Поиск PDB в месте, где находится файл .exe.</span><span class="sxs-lookup"><span data-stu-id="3b55a-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3b55a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="3b55a-114">Requirements</span></span>  
 <span data-ttu-id="3b55a-115">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3b55a-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b55a-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3b55a-116">See also</span></span>

- [<span data-ttu-id="3b55a-117">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="3b55a-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
