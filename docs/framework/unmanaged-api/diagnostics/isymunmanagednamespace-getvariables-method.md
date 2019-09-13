---
title: Метод ISymUnmanagedNamespace::GetVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetVariables
helpviewer_keywords:
- ISymUnmanagedNamespace::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: ea7c1617-f3ce-4220-8288-f2b50eaf0f0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 813f57377c1885b09190ada3c73f4391a3f2d931
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895049"
---
# <a name="isymunmanagednamespacegetvariables-method"></a><span data-ttu-id="eacee-102">Метод ISymUnmanagedNamespace::GetVariables</span><span class="sxs-lookup"><span data-stu-id="eacee-102">ISymUnmanagedNamespace::GetVariables Method</span></span>
<span data-ttu-id="eacee-103">Возвращает все переменные, определенные в глобальной области видимости в этом пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="eacee-103">Returns all variables defined at global scope within this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eacee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eacee-104">Syntax</span></span>  
  
```cpp
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eacee-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eacee-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="eacee-106">окне Значение `ULONG32` типа, указывающее размер `pVars` массива.</span><span class="sxs-lookup"><span data-stu-id="eacee-106">[in] A `ULONG32` that indicates the size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="eacee-107">заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения пространств имен.</span><span class="sxs-lookup"><span data-stu-id="eacee-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `pVars`  
 <span data-ttu-id="eacee-108">заполняет Указатель на буфер, содержащий пространства имен.</span><span class="sxs-lookup"><span data-stu-id="eacee-108">[out] A pointer to a buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eacee-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="eacee-109">Return Value</span></span>  
 <span data-ttu-id="eacee-110">Значение S_OK, если метод выполнен. в противном случае — E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="eacee-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eacee-111">Требования</span><span class="sxs-lookup"><span data-stu-id="eacee-111">Requirements</span></span>  
 <span data-ttu-id="eacee-112">**Заголовок.** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="eacee-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eacee-113">См. также</span><span class="sxs-lookup"><span data-stu-id="eacee-113">See also</span></span>

- [<span data-ttu-id="eacee-114">Интерфейс ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="eacee-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
