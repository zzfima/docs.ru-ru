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
ms.openlocfilehash: da2906187c02bbc7a35c937663e3fc7db1ebda13
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433884"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="25db0-102">Метод ISymUnmanagedNamespace::GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="25db0-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="25db0-103">Возвращает дочерние элементы этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="25db0-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25db0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="25db0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25db0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="25db0-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="25db0-106">окне `ULONG32`, указывающий размер массива `namespaces`.</span><span class="sxs-lookup"><span data-stu-id="25db0-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="25db0-107">заполняет Указатель на `ULONG32`, который получает размер буфера (в символах), необходимого для хранения пространств имен.</span><span class="sxs-lookup"><span data-stu-id="25db0-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="25db0-108">заполняет Указатель на буфер, содержащий пространства имен.</span><span class="sxs-lookup"><span data-stu-id="25db0-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25db0-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="25db0-109">Return Value</span></span>  
 <span data-ttu-id="25db0-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="25db0-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25db0-111">Требования</span><span class="sxs-lookup"><span data-stu-id="25db0-111">Requirements</span></span>  
 <span data-ttu-id="25db0-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="25db0-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25db0-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="25db0-113">See also</span></span>

- [<span data-ttu-id="25db0-114">Интерфейс ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="25db0-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
