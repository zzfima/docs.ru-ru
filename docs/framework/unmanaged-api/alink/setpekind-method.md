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
ms.openlocfilehash: 5a8442b1f0869e1592a05dfeeb0f5e6d583f3ea8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179392"
---
# <a name="setpekind-method"></a><span data-ttu-id="ba046-102">Метод SetPEKind</span><span class="sxs-lookup"><span data-stu-id="ba046-102">SetPEKind Method</span></span>
<span data-ttu-id="ba046-103">Определяет портативный исполняемый тип, либо машинно-специфический, либо машинно-агностик.</span><span class="sxs-lookup"><span data-stu-id="ba046-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba046-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba046-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="ba046-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ba046-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ba046-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="ba046-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="ba046-107">Токен файла, для которого должен быть установлен тип PE.</span><span class="sxs-lookup"><span data-stu-id="ba046-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="ba046-108">Может быть `AssemblyID` NULL, если не указывается несвязанный нетмодуль.</span><span class="sxs-lookup"><span data-stu-id="ba046-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="ba046-109">Тип PE, как указано [в CorPEKind Enumeration](../metadata/corpekind-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="ba046-109">The type of PE, as indicated by the [CorPEKind Enumeration](../metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="ba046-110">Архитектура целевой машины, как указано в заголовке NT.</span><span class="sxs-lookup"><span data-stu-id="ba046-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba046-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ba046-111">Return Value</span></span>  
 <span data-ttu-id="ba046-112">Возвращает S_OK, если метод успешно.</span><span class="sxs-lookup"><span data-stu-id="ba046-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba046-113">Требования</span><span class="sxs-lookup"><span data-stu-id="ba046-113">Requirements</span></span>  
 <span data-ttu-id="ba046-114">Требуетa alink.h.</span><span class="sxs-lookup"><span data-stu-id="ba046-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba046-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ba046-115">See also</span></span>

- [<span data-ttu-id="ba046-116">Метод GetPEKind</span><span class="sxs-lookup"><span data-stu-id="ba046-116">GetPEKind Method</span></span>](../metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="ba046-117">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="ba046-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="ba046-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="ba046-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="ba046-119">API ALink</span><span class="sxs-lookup"><span data-stu-id="ba046-119">ALink API</span></span>](index.md)
