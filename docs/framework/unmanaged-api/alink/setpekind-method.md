---
title: Метод SetPEKind
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a48dbd38d357b668c2794ae6305ceb9cad3dcf4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787191"
---
# <a name="setpekind-method"></a><span data-ttu-id="4b162-102">Метод SetPEKind</span><span class="sxs-lookup"><span data-stu-id="4b162-102">SetPEKind Method</span></span>
<span data-ttu-id="4b162-103">Определяет тип переносимого исполняемого файла, который зависит от компьютера или компьютера.</span><span class="sxs-lookup"><span data-stu-id="4b162-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b162-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b162-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="4b162-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4b162-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="4b162-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="4b162-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="4b162-107">Токен файла, для которого задается тип PE.</span><span class="sxs-lookup"><span data-stu-id="4b162-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="4b162-108">Может иметь значение NULL `AssemblyID` , если не указывает на непривязанный netmodule.</span><span class="sxs-lookup"><span data-stu-id="4b162-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="4b162-109">Тип PE, как указано в [перечислении CorPEKind](../metadata/corpekind-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="4b162-109">The type of PE, as indicated by the [CorPEKind Enumeration](../metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="4b162-110">Архитектура целевого компьютера, как указано в заголовке NT.</span><span class="sxs-lookup"><span data-stu-id="4b162-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b162-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4b162-111">Return Value</span></span>  
 <span data-ttu-id="4b162-112">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="4b162-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b162-113">Требования</span><span class="sxs-lookup"><span data-stu-id="4b162-113">Requirements</span></span>  
 <span data-ttu-id="4b162-114">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="4b162-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b162-115">См. также</span><span class="sxs-lookup"><span data-stu-id="4b162-115">See also</span></span>

- [<span data-ttu-id="4b162-116">Метод GetPEKind</span><span class="sxs-lookup"><span data-stu-id="4b162-116">GetPEKind Method</span></span>](../metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="4b162-117">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="4b162-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="4b162-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="4b162-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="4b162-119">API ALink</span><span class="sxs-lookup"><span data-stu-id="4b162-119">ALink API</span></span>](index.md)
