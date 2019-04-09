---
title: Метод ISymUnmanagedScope::GetEndOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e28a351b6d47d14f171b9e760b2fa2c6755e3f8b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158591"
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="baf0f-102">Метод ISymUnmanagedScope::GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="baf0f-102">ISymUnmanagedScope::GetEndOffset Method</span></span>
<span data-ttu-id="baf0f-103">Возвращает конечное смещение для этой области.</span><span class="sxs-lookup"><span data-stu-id="baf0f-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baf0f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="baf0f-104">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="baf0f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="baf0f-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="baf0f-106">[out] Указатель на `ULONG32` , который получает конечное смещение.</span><span class="sxs-lookup"><span data-stu-id="baf0f-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="baf0f-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="baf0f-107">Return Value</span></span>  
 <span data-ttu-id="baf0f-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="baf0f-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baf0f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="baf0f-109">Requirements</span></span>  
 <span data-ttu-id="baf0f-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="baf0f-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baf0f-111">См. также</span><span class="sxs-lookup"><span data-stu-id="baf0f-111">See also</span></span>

- [<span data-ttu-id="baf0f-112">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="baf0f-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="baf0f-113">Метод GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="baf0f-113">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)
