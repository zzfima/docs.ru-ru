---
title: Метод ISymUnmanagedWriter4::GetDebugInfoWithPadding
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
ms.openlocfilehash: 274bf79175bda9e880b1ef3cf8f125a017ad0734
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121660"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="ed4bc-102">Метод ISymUnmanagedWriter4::GetDebugInfoWithPadding</span><span class="sxs-lookup"><span data-stu-id="ed4bc-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="ed4bc-103">Функция аналогична [методу GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) , за исключением того, что строка пути дополнена нулями после завершающего нуль-символа, чтобы сделать строку фиксированным размером `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="ed4bc-103">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="ed4bc-104">Заполнение задается только в том случае, если длина строки пути меньше `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="ed4bc-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="ed4bc-105">Это упрощает написание средств, которые отличаются от PE файлов.</span><span class="sxs-lookup"><span data-stu-id="ed4bc-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed4bc-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed4bc-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed4bc-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="ed4bc-107">Parameters</span></span>  
  
|<span data-ttu-id="ed4bc-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="ed4bc-108">Parameter</span></span>|<span data-ttu-id="ed4bc-109">Описание</span><span class="sxs-lookup"><span data-stu-id="ed4bc-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="ed4bc-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ed4bc-110">Return Value</span></span>  
 <span data-ttu-id="ed4bc-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="ed4bc-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed4bc-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ed4bc-112">Requirements</span></span>  
 <span data-ttu-id="ed4bc-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="ed4bc-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed4bc-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ed4bc-114">See also</span></span>

- [<span data-ttu-id="ed4bc-115">Интерфейс ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="ed4bc-115">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
