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
ms.openlocfilehash: 3d7ac84971f7d0e97f7ccd26710151d1aeefe729
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207218"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="db2fa-102">Метод ISymUnmanagedNamespace::GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="db2fa-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="db2fa-103">Возвращает дочерние элементы этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="db2fa-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db2fa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="db2fa-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db2fa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="db2fa-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="db2fa-106">[in] Объект `ULONG32` указывает размер `namespaces` массива.</span><span class="sxs-lookup"><span data-stu-id="db2fa-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="db2fa-107">[out] Указатель на `ULONG32` размер, который получает в символах, буфера, требуемого для хранения пространства имен.</span><span class="sxs-lookup"><span data-stu-id="db2fa-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="db2fa-108">[out] Указатель на буфер, содержащий пространства имен.</span><span class="sxs-lookup"><span data-stu-id="db2fa-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db2fa-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="db2fa-109">Return Value</span></span>  
 <span data-ttu-id="db2fa-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="db2fa-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db2fa-111">Требования</span><span class="sxs-lookup"><span data-stu-id="db2fa-111">Requirements</span></span>  
 <span data-ttu-id="db2fa-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="db2fa-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db2fa-113">См. также</span><span class="sxs-lookup"><span data-stu-id="db2fa-113">See also</span></span>

- [<span data-ttu-id="db2fa-114">Интерфейс ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="db2fa-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
