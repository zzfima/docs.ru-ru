---
title: "Метод ISymUnmanagedWriter::OpenNamespace"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedWriter.OpenNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::OpenNamespace method [.NET Framework debugging]
- OpenNamespace method [.NET Framework debugging]
ms.assetid: 426f4e4f-e60d-4ad1-b546-a10e3c55c283
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 77d50f6bac87d5a110b53a69044f96f547c51904
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="61cb8-102">Метод ISymUnmanagedWriter::OpenNamespace</span><span class="sxs-lookup"><span data-stu-id="61cb8-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="61cb8-103">Открывает новое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="61cb8-103">Opens a new namespace.</span></span> <span data-ttu-id="61cb8-104">Этот метод следует вызывайте перед определением методов или переменных, расположенных в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="61cb8-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="61cb8-105">Пространства имен могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="61cb8-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61cb8-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61cb8-106">Syntax</span></span>  
  
```  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61cb8-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="61cb8-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="61cb8-108">[in] Указатель на имя нового пространства имен.</span><span class="sxs-lookup"><span data-stu-id="61cb8-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61cb8-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="61cb8-109">Return Value</span></span>  
 <span data-ttu-id="61cb8-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="61cb8-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61cb8-111">Требования</span><span class="sxs-lookup"><span data-stu-id="61cb8-111">Requirements</span></span>  
 <span data-ttu-id="61cb8-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="61cb8-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61cb8-113">См. также</span><span class="sxs-lookup"><span data-stu-id="61cb8-113">See Also</span></span>  
 [<span data-ttu-id="61cb8-114">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="61cb8-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="61cb8-115">Метод CloseNamespace</span><span class="sxs-lookup"><span data-stu-id="61cb8-115">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)
