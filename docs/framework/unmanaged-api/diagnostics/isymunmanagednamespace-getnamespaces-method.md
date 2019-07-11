---
title: Метод ISymUnmanagedNamespace::GetNamespaces
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedNamespace::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 0ea9d9af-8709-4a46-872b-f54d9e840088
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2e11886917964134a2530ae8484dba3cde5e7b61
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759369"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="b57e2-102">Метод ISymUnmanagedNamespace::GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="b57e2-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="b57e2-103">Возвращает дочерние элементы этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="b57e2-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b57e2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b57e2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b57e2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b57e2-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="b57e2-106">[in] Объект `ULONG32` указывает размер `namespaces` массива.</span><span class="sxs-lookup"><span data-stu-id="b57e2-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="b57e2-107">[out] Указатель на `ULONG32` размер, который получает в символах, буфера, требуемого для хранения пространства имен.</span><span class="sxs-lookup"><span data-stu-id="b57e2-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="b57e2-108">[out] Указатель на буфер, содержащий пространства имен.</span><span class="sxs-lookup"><span data-stu-id="b57e2-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b57e2-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b57e2-109">Return Value</span></span>  
 <span data-ttu-id="b57e2-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="b57e2-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b57e2-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b57e2-111">Requirements</span></span>  
 <span data-ttu-id="b57e2-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b57e2-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b57e2-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b57e2-113">See also</span></span>

- [<span data-ttu-id="b57e2-114">Интерфейс ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="b57e2-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
