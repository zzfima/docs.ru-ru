---
title: "Метод ISymUnmanagedVariable::GetEndOffset"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetEndOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedVariable::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: e5d777c5-d450-4c0f-999c-b3953ee22cfb
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b7a2dac8425cd852c6c17ee1674710f6798d3b1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="3d5bf-102">Метод ISymUnmanagedVariable::GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="3d5bf-102">ISymUnmanagedVariable::GetEndOffset Method</span></span>
<span data-ttu-id="3d5bf-103">Возвращает конечное смещение переменной в его родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="3d5bf-103">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="3d5bf-104">Если это локальную переменную в пределах области, конечное смещение попадают в границах смещений, заданных для данной области.</span><span class="sxs-lookup"><span data-stu-id="3d5bf-104">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d5bf-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d5bf-105">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d5bf-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3d5bf-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="3d5bf-107">[out] Указатель на `ULONG32` , получающий конечное смещение.</span><span class="sxs-lookup"><span data-stu-id="3d5bf-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d5bf-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3d5bf-108">Return Value</span></span>  
 <span data-ttu-id="3d5bf-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="3d5bf-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d5bf-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3d5bf-110">Requirements</span></span>  
 <span data-ttu-id="3d5bf-111">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3d5bf-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d5bf-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3d5bf-112">See Also</span></span>  
 [<span data-ttu-id="3d5bf-113">ISymUnmanagedVariable-интерфейс</span><span class="sxs-lookup"><span data-stu-id="3d5bf-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="3d5bf-114">Метод GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="3d5bf-114">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)
