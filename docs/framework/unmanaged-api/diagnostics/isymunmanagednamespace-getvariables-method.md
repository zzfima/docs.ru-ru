---
title: "Метод ISymUnmanagedNamespace::GetVariables"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedNamespace.GetVariables
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedNamespace::GetVariables
helpviewer_keywords:
- ISymUnmanagedNamespace::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: ea7c1617-f3ce-4220-8288-f2b50eaf0f0f
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6f2de9f683a9ce667b4b72c94204d39082cdaee4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagednamespacegetvariables-method"></a><span data-ttu-id="a90bf-102">Метод ISymUnmanagedNamespace::GetVariables</span><span class="sxs-lookup"><span data-stu-id="a90bf-102">ISymUnmanagedNamespace::GetVariables Method</span></span>
<span data-ttu-id="a90bf-103">Возвращает все переменные, определенные в глобальной области видимости в пределах этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a90bf-103">Returns all variables defined at global scope within this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a90bf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a90bf-104">Syntax</span></span>  
  
```  
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a90bf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a90bf-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="a90bf-106">[in] Объект `ULONG32` указывает размер `pVars` массива.</span><span class="sxs-lookup"><span data-stu-id="a90bf-106">[in] A `ULONG32` that indicates the size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="a90bf-107">[out] Указатель на `ULONG32` , получающий размер буфера, необходимый для пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a90bf-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `pVars`  
 <span data-ttu-id="a90bf-108">[out] Указатель на буфер, который содержит пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a90bf-108">[out] A pointer to a buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a90bf-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a90bf-109">Return Value</span></span>  
 <span data-ttu-id="a90bf-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="a90bf-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a90bf-111">Требования</span><span class="sxs-lookup"><span data-stu-id="a90bf-111">Requirements</span></span>  
 <span data-ttu-id="a90bf-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a90bf-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a90bf-113">См. также</span><span class="sxs-lookup"><span data-stu-id="a90bf-113">See Also</span></span>  
 [<span data-ttu-id="a90bf-114">ISymUnmanagedNamespace-интерфейс</span><span class="sxs-lookup"><span data-stu-id="a90bf-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
