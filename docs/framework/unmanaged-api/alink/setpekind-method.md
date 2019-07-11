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
ms.openlocfilehash: 8fc581904351443f4368a68a653fd39b3548999a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741428"
---
# <a name="setpekind-method"></a><span data-ttu-id="fe356-102">Метод SetPEKind</span><span class="sxs-lookup"><span data-stu-id="fe356-102">SetPEKind Method</span></span>
<span data-ttu-id="fe356-103">Определяет переносимый исполняемый тип, независимый от компьютера или конкретного компьютера.</span><span class="sxs-lookup"><span data-stu-id="fe356-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe356-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe356-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="fe356-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fe356-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="fe356-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="fe356-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="fe356-107">Маркер файла, для которого будет устанавливаться тип PE.</span><span class="sxs-lookup"><span data-stu-id="fe356-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="fe356-108">Может иметь значение NULL, если `AssemblyID` не обеспечивает несвязанный NETMODULE-файл.</span><span class="sxs-lookup"><span data-stu-id="fe356-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="fe356-109">Тип PE, обозначенный [перечисление CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="fe356-109">The type of PE, as indicated by the [CorPEKind Enumeration](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="fe356-110">Архитектуры конечного компьютера, как указано в заголовке NT.</span><span class="sxs-lookup"><span data-stu-id="fe356-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe356-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fe356-111">Return Value</span></span>  
 <span data-ttu-id="fe356-112">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="fe356-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe356-113">Требования</span><span class="sxs-lookup"><span data-stu-id="fe356-113">Requirements</span></span>  
 <span data-ttu-id="fe356-114">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="fe356-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe356-115">См. также</span><span class="sxs-lookup"><span data-stu-id="fe356-115">See also</span></span>

- [<span data-ttu-id="fe356-116">Метод GetPEKind</span><span class="sxs-lookup"><span data-stu-id="fe356-116">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="fe356-117">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="fe356-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="fe356-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="fe356-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="fe356-119">API ALink</span><span class="sxs-lookup"><span data-stu-id="fe356-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
