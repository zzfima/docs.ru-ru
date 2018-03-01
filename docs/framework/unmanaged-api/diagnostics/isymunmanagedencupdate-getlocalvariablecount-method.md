---
title: "Метод ISymUnmanagedENCUpdate::GetLocalVariableCount"
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
- ISymUnmanagedENCUpdate.GetLocalVariableCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount method [.NET Framework debugging]
- GetLocalVariableCount method [.NET Framework debugging]
ms.assetid: 9777d8bb-4abc-4be8-aa7c-34f853eceb9c
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7c86b2988d414d091bc23d29bd79f518a756d688
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="73252-102">Метод ISymUnmanagedENCUpdate::GetLocalVariableCount</span><span class="sxs-lookup"><span data-stu-id="73252-102">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>
<span data-ttu-id="73252-103">Возвращает количество локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="73252-103">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73252-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73252-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="73252-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="73252-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="73252-106">[in] Токен метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="73252-106">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="73252-107">[out] Указатель на `ULONG32` , получающий размер в символах, буфера, должны содержать количество локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="73252-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73252-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="73252-108">Return Value</span></span>  
 <span data-ttu-id="73252-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="73252-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73252-110">Требования</span><span class="sxs-lookup"><span data-stu-id="73252-110">Requirements</span></span>  
 <span data-ttu-id="73252-111">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="73252-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73252-112">См. также</span><span class="sxs-lookup"><span data-stu-id="73252-112">See Also</span></span>  
 [<span data-ttu-id="73252-113">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="73252-113">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
