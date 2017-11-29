---
title: "Метод ISymUnmanagedVariable::GetStartOffset"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetStartOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetStartOffset method [.NET Framework debugging]
ms.assetid: 63021fc1-9c2d-4788-811f-fe8ca077206a
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5b7fd3a64202224ef5a7cc348ee8e9974a664d09
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="0a8cc-102">Метод ISymUnmanagedVariable::GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="0a8cc-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>
<span data-ttu-id="0a8cc-103">Возвращает начальное смещение переменной в его родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="0a8cc-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="0a8cc-104">В случае локальной переменной в области, начальное смещение попадают в границах смещений, заданных для данной области.</span><span class="sxs-lookup"><span data-stu-id="0a8cc-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a8cc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a8cc-105">Syntax</span></span>  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a8cc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0a8cc-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="0a8cc-107">[out] Указатель на `ULONG32` , который получает начальное смещение.</span><span class="sxs-lookup"><span data-stu-id="0a8cc-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a8cc-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0a8cc-108">Return Value</span></span>  
 <span data-ttu-id="0a8cc-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="0a8cc-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a8cc-110">Требования</span><span class="sxs-lookup"><span data-stu-id="0a8cc-110">Requirements</span></span>  
 <span data-ttu-id="0a8cc-111">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0a8cc-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a8cc-112">См. также</span><span class="sxs-lookup"><span data-stu-id="0a8cc-112">See Also</span></span>  
 [<span data-ttu-id="0a8cc-113">ISymUnmanagedVariable-интерфейс</span><span class="sxs-lookup"><span data-stu-id="0a8cc-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="0a8cc-114">Метод GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="0a8cc-114">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)
