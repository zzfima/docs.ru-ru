---
title: Метод ISymUnmanagedWriter4::GetDebugInfoWithPadding
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7cfa82ae8bbc87a884887f826d947c2d3f2c5341
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473530"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="bf3d5-102">Метод ISymUnmanagedWriter4::GetDebugInfoWithPadding</span><span class="sxs-lookup"><span data-stu-id="bf3d5-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="bf3d5-103">Работает так же, как [метод GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) за исключением того, что строка пути дополняется нулей, завершающий нуль-символ, чтобы сделать строковые данные фиксированный размер `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-103">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="bf3d5-104">Заполнение предоставляется только в том случае, если длина строки пути, сам меньше, чем `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="bf3d5-105">Это упрощает для записи этого файла различий PE средства.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf3d5-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf3d5-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf3d5-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="bf3d5-107">Parameters</span></span>  
  
|<span data-ttu-id="bf3d5-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="bf3d5-108">Parameter</span></span>|<span data-ttu-id="bf3d5-109">Описание</span><span class="sxs-lookup"><span data-stu-id="bf3d5-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="bf3d5-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bf3d5-110">Return Value</span></span>  
 <span data-ttu-id="bf3d5-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf3d5-112">Требования</span><span class="sxs-lookup"><span data-stu-id="bf3d5-112">Requirements</span></span>  
 <span data-ttu-id="bf3d5-113">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bf3d5-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf3d5-114">См. также</span><span class="sxs-lookup"><span data-stu-id="bf3d5-114">See also</span></span>
- [<span data-ttu-id="bf3d5-115">Интерфейс ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="bf3d5-115">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
