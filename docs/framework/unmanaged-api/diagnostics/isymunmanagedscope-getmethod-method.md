---
title: "Метод ISymUnmanagedScope::GetMethod"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope.GetMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetMethod method [.NET Framework debugging]
ms.assetid: a61866ee-221a-45b9-a1b7-395825b77872
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bb062ad7ab485a1631a9cbe15f904b21226cb502
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="00ecf-102">Метод ISymUnmanagedScope::GetMethod</span><span class="sxs-lookup"><span data-stu-id="00ecf-102">ISymUnmanagedScope::GetMethod Method</span></span>
<span data-ttu-id="00ecf-103">Возвращает метод, содержащий эту область.</span><span class="sxs-lookup"><span data-stu-id="00ecf-103">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00ecf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00ecf-104">Syntax</span></span>  
  
```  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="00ecf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="00ecf-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="00ecf-106">[out] Указатель на возвращаемый [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="00ecf-106">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00ecf-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="00ecf-107">Return Value</span></span>  
 <span data-ttu-id="00ecf-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="00ecf-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00ecf-109">Требования</span><span class="sxs-lookup"><span data-stu-id="00ecf-109">Requirements</span></span>  
 <span data-ttu-id="00ecf-110">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="00ecf-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00ecf-111">См. также</span><span class="sxs-lookup"><span data-stu-id="00ecf-111">See Also</span></span>  
 [<span data-ttu-id="00ecf-112">ISymUnmanagedScope-интерфейс</span><span class="sxs-lookup"><span data-stu-id="00ecf-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
