---
title: Интерфейс ISymUnmanagedReader2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2
helpviewer_keywords:
- ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type:
- apiref
ms.openlocfilehash: a07c75e14244fb5bdf72ff2b0d344ae27672ef89
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448265"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="8aa74-102">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="8aa74-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="8aa74-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span><span class="sxs-lookup"><span data-stu-id="8aa74-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="8aa74-104">This interface extends the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="8aa74-104">This interface extends the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8aa74-105">Методы</span><span class="sxs-lookup"><span data-stu-id="8aa74-105">Methods</span></span>  
  
|<span data-ttu-id="8aa74-106">Метод</span><span class="sxs-lookup"><span data-stu-id="8aa74-106">Method</span></span>|<span data-ttu-id="8aa74-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8aa74-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8aa74-108">Метод GetMethodByVersionPreRemap</span><span class="sxs-lookup"><span data-stu-id="8aa74-108">GetMethodByVersionPreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="8aa74-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span><span class="sxs-lookup"><span data-stu-id="8aa74-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="8aa74-110">Метод GetMethodsInDocument</span><span class="sxs-lookup"><span data-stu-id="8aa74-110">GetMethodsInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="8aa74-111">Gets every method that has line information in the provided document.</span><span class="sxs-lookup"><span data-stu-id="8aa74-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="8aa74-112">Метод GetSymAttributePreRemap</span><span class="sxs-lookup"><span data-stu-id="8aa74-112">GetSymAttributePreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="8aa74-113">Gets a custom attribute based upon its name.</span><span class="sxs-lookup"><span data-stu-id="8aa74-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8aa74-114">Требования</span><span class="sxs-lookup"><span data-stu-id="8aa74-114">Requirements</span></span>  
 <span data-ttu-id="8aa74-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8aa74-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aa74-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8aa74-116">See also</span></span>

- [<span data-ttu-id="8aa74-117">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="8aa74-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="8aa74-118">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="8aa74-118">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
