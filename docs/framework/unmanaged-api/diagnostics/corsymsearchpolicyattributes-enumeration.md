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
ms.openlocfilehash: 5ed868febb5eb82cf73cfc5b0633d86bf4e1315c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561625"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="b76e3-102">Перечисление CorSymSearchPolicyAttributes</span><span class="sxs-lookup"><span data-stu-id="b76e3-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="b76e3-103">Указывает политику, используемую при выполнении поиска для средства чтения символов.</span><span class="sxs-lookup"><span data-stu-id="b76e3-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="b76e3-104">Эти константы используются [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) и [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) методы.</span><span class="sxs-lookup"><span data-stu-id="b76e3-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b76e3-105">Он представляет угрозу безопасности, чтобы открыть файл базы данных (PDB) программы из ненадежного источника.</span><span class="sxs-lookup"><span data-stu-id="b76e3-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b76e3-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b76e3-106">Syntax</span></span>  
  
```  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="b76e3-107">Участники</span><span class="sxs-lookup"><span data-stu-id="b76e3-107">Members</span></span>  
  
|<span data-ttu-id="b76e3-108">Член</span><span class="sxs-lookup"><span data-stu-id="b76e3-108">Member</span></span>|<span data-ttu-id="b76e3-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b76e3-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="b76e3-110">Запрашивает в реестре для пути поиска символов.</span><span class="sxs-lookup"><span data-stu-id="b76e3-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="b76e3-111">Обращается к серверу символов.</span><span class="sxs-lookup"><span data-stu-id="b76e3-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="b76e3-112">Выполняет поиск путь, указанный в каталоге отладки.</span><span class="sxs-lookup"><span data-stu-id="b76e3-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="b76e3-113">Выполняет поиск PDB-ФАЙЛ в месте расположения файла .exe.</span><span class="sxs-lookup"><span data-stu-id="b76e3-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b76e3-114">Требования</span><span class="sxs-lookup"><span data-stu-id="b76e3-114">Requirements</span></span>  
 <span data-ttu-id="b76e3-115">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b76e3-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b76e3-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b76e3-116">See also</span></span>
- [<span data-ttu-id="b76e3-117">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="b76e3-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
